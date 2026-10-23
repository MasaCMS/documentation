---
layout: default
title: Secure upload folders
nav_order: 3
grand_parent: Getting started
parent: Security
last_modified_date: 23-10-2026 12:00
permalink: /getting-started/security/secure-upload-folders/
---

# Secure upload folders

Folders that contain uploaded files must never run server-side code. This is one of the most effective lockdown measures: if an attacker ever manages to place a script in an upload folder, these rules stop it from running.

## Where Masa CMS stores uploads

| Folder | Contains |
|--------|----------|
| `/sites/{siteid}/assets/` | Files uploaded through the file browser and the rich text editor |
| `/sites/{siteid}/cache/file/` | File content items, Associated Images, and files uploaded through forms on the public site |

Both folders are inside the webroot and are written to by Masa CMS.

## What Masa CMS already does

Masa CMS checks the extension of every uploaded file against an allow-list:

- `fmallowedextensions`: extensions editors may upload in the admin.
- `fmpublicallowedextensions`: extensions visitors may upload on the public site, for example through a form.
- `deniedbundleassetextensions`: executable extensions that are rejected when a content bundle is deployed into the asset or file folders.

These settings are described in the [Configuration file](/getting-started/configuration/configuration-file/) documentation.

## Why the web server should block scripts too

The extension checks are your first line of defense. The web server is your second. A script can still end up in an upload folder, for example through a vulnerability in a plugin, a misconfigured setting, a compromised editor account, or a file copied there by hand. If the web server passes that file to the CFML engine, it runs with the full permissions of Masa CMS.

Block requests for executable file types in the upload folders, so that such a file can never run.

{: .important}
The configurations below are examples. Review and test them for your own setup.

The examples block CFML, Java, PHP, ASP.NET and common script extensions in the `assets` and `cache` folders of every site. The pattern also catches requests with extra path information, such as `/file.cfm/extra`, which some CFML engines would still run.

### Apache

Add the following to the `<VirtualHost>` of your site. Use the virtual host rather than `.htaccess`: when CFML requests are passed to the CFML engine with `ProxyPass` or `ProxyPassMatch`, rules in `.htaccess` are not applied to those requests.

```apache
# Never run scripts from upload folders
<LocationMatch "(?i)^/sites/[^/]+/(assets|cache)/.*\.(cfm|cfml|cfc|cfr|cfs|jsp|jspx|php[0-9]?|phtml|phar|asp|aspx|ashx|asmx|pl|py|rb|sh|cgi)([/;]|$)">
    Require all denied
</LocationMatch>
```

### IIS

This requires the [IIS URL Rewrite module](https://www.iis.net/downloads/microsoft/url-rewrite). Add the following rule at the top of `<rewrite><rules>` in your `web.config`:

```xml
<rule name="Never run scripts from upload folders" stopProcessing="true">
  <match url="^sites/[^/]+/(assets|cache)/.*\.(cfm|cfml|cfc|cfr|cfs|jsp|jspx|php[0-9]?|phtml|phar|asp|aspx|ashx|asmx|pl|py|rb|sh|cgi)([/;]|$)" ignoreCase="true" />
  <action type="CustomResponse" statusCode="403" statusReason="Forbidden" statusDescription="Access denied" />
</rule>
```

As an extra measure on IIS, you can remove script and execute permissions from the upload folders, so that IIS only serves them as static files:

```xml
<location path="sites/default/assets">
  <system.webServer>
    <handlers accessPolicy="Read" />
  </system.webServer>
</location>
```

Add a `<location>` block for the `assets` and `cache` folder of each site.

### Nginx

Add the following to the `server` block of your site, **before** the `location` block that passes `.cfm` and `.cfc` requests to the CFML engine. Nginx uses the first regex location that matches.

```nginx
# Never run scripts from upload folders
location ~* ^/sites/[^/]+/(assets|cache)/.*\.(cfm|cfml|cfc|cfr|cfs|jsp|jspx|php\d?|phtml|phar|asp|aspx|ashx|asmx|pl|py|rb|sh|cgi)([/;]|$) {
    return 403;
}
```

## Limit the allowed upload types

Review the allowed extensions in `/config/settings.ini.cfm` and remove what your sites don't need. Be strict with `fmpublicallowedextensions`, because anyone visiting the site can use those uploads.

Pay special attention to:

- **`svg`**: SVG files can contain JavaScript. An uploaded SVG opened directly in the browser runs that script on your domain (stored cross-site scripting). Remove `svg` from `fmpublicallowedextensions`, and only allow it in `fmallowedextensions` if you trust all editors.
- **`xml`, `json`, `swf`**: rarely needed for public uploads.

For example, for a site where forms only accept documents and images:

```ini
fmpublicallowedextensions=pdf,doc,docx,xls,xlsx,odt,ods,jpg,jpeg,png,gif
```

## Test your configuration

1. Place a test file named `test.cfm` containing `<cfoutput>#now()#</cfoutput>` in `/sites/{siteid}/assets/`.
2. Request `https://www.example.com/sites/{siteid}/assets/test.cfm`. You should get a `403 Forbidden` response, not the current date and time.
3. Request `https://www.example.com/sites/{siteid}/assets/test.cfm/extra`. This should also return `403 Forbidden`.
4. Delete the test file.
5. Check that images and documents in the `assets` and `cache` folders still load.
