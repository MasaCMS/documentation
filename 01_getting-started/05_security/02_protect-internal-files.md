---
layout: default
title: Protect internal folders and files
nav_order: 2
grand_parent: Getting started
parent: Security
last_modified_date: 23-10-2026 12:00
permalink: /getting-started/security/protect-internal-files/
---

# Protect internal folders and files

A Masa CMS installation contains folders and files that are never meant to be requested by a browser: configuration with database credentials, development and test tooling, package manifests and log files. Block them at the web server level.

## Why this is needed

Masa CMS places an `Application.cfc` in folders such as `/config`, `/core`, `/sites` and `/themes` that stops direct requests to CFML files. This is a useful safety net, but it has limits:

- It only applies to requests that reach the CFML engine. Static files such as `.log`, `.json`, `.md` or `.sql` files, and folders such as `.git`, are served by the web server directly.
- If the connection between the web server and the CFML engine is misconfigured, CFML files such as `/config/settings.ini.cfm` can be served as plain text, including the database password.
- Some tooling is intentionally reachable, for example the test runner in `/core/tests`.

## Remove what you don't need

The most reliable protection is to not have the files on a production server at all. Depending on how you installed Masa CMS, consider removing:

- `/core/tests` (the test suite and test runner)
- `.git`, `.github` and other dot-files and folders
- `node_modules`, `package.json`, `package-lock.json` and `gulpfile.js`

The ForgeBox package already leaves out the tests. A Git checkout contains everything.

## Block what remains

Even when you remove files, add web server rules as a second line of defense. The examples below block:

| What | Why |
|------|-----|
| `/config/` | Contains `settings.ini.cfm` with datasource and mail credentials |
| `/WEB-INF/` | CFML engine configuration |
| `/core/tests/` | Test tooling |
| `/core/setup/` | The installation wizard. Only block this **after** installation is complete |
| `/node_modules/` | Front-end build dependencies |
| Hidden files and folders (`.git`, `.env`, ...) | Source code history and secrets. `/.well-known/` stays reachable for certificate validation |
| `*.log`, `*.sql`, `*.bak`, `*.old`, `*.swp`, `*.ini` | Logs, database dumps and backup copies |
| `box.json`, `package.json`, `README.md`, `htaccess.txt`, ... in the webroot | Reveal versions and setup details |

{: .important}
The configurations below are examples. Review and test them for your own setup. After applying them, check that both the public site and the Masa CMS admin still work.

### Apache

Add the following to the `<VirtualHost>` of your site. Use the virtual host rather than `.htaccess`: when CFML requests are passed to the CFML engine with `ProxyPass` or `ProxyPassMatch`, rules in `.htaccess` are not applied to those requests.

```apache
# Internal folders
<LocationMatch "(?i)^/(config|WEB-INF|core/(tests|setup)|node_modules)(/|$)">
    Require all denied
</LocationMatch>

# Hidden files and folders, except /.well-known/
<LocationMatch "/\.(?!well-known/)">
    Require all denied
</LocationMatch>

# Logs, dumps, backups and files in the webroot that reveal setup details
<LocationMatch "(?i)(\.(log|sql|bak|old|swp|ini|md)$|^/(box\.json|package(-lock)?\.json|gulpfile\.js|Installation\.txt|htaccess\.txt|web\.config\.txt|license\.txt|COPYING)$)">
    Require all denied
</LocationMatch>
```

### IIS

This requires the [IIS URL Rewrite module](https://www.iis.net/downloads/microsoft/url-rewrite). Add the following rules at the top of `<rewrite><rules>` in your `web.config`:

```xml
<rule name="Block internal folders" stopProcessing="true">
  <match url="^(config|WEB-INF|core/(tests|setup)|node_modules)(/|$)" ignoreCase="true" />
  <action type="CustomResponse" statusCode="403" statusReason="Forbidden" statusDescription="Access denied" />
</rule>
<rule name="Block hidden files and folders" stopProcessing="true">
  <match url="(^|/)\.(?!well-known/)" />
  <action type="CustomResponse" statusCode="403" statusReason="Forbidden" statusDescription="Access denied" />
</rule>
<rule name="Block internal files" stopProcessing="true">
  <match url="(\.(log|sql|bak|old|swp|ini|md)$|^(box\.json|package(-lock)?\.json|gulpfile\.js|Installation\.txt|htaccess\.txt|web\.config\.txt|license\.txt|COPYING)$)" ignoreCase="true" />
  <action type="CustomResponse" statusCode="403" statusReason="Forbidden" statusDescription="Access denied" />
</rule>
```

### Nginx

Add the following to the `server` block of your site, **before** other regex `location` blocks (such as the one that passes `.cfm` requests to the CFML engine). Nginx uses the first regex location that matches.

```nginx
# Internal folders
location ~* ^/(config|WEB-INF|core/(tests|setup)|node_modules)(/|$) {
    return 403;
}

# Hidden files and folders, except /.well-known/
location ~ /\.(?!well-known/) {
    return 403;
}

# Logs, dumps, backups and files in the webroot that reveal setup details
location ~* (\.(log|sql|bak|old|swp|ini|md)$|^/(box\.json|package(-lock)?\.json|gulpfile\.js|Installation\.txt|htaccess\.txt|web\.config\.txt|license\.txt|COPYING)$) {
    return 403;
}
```

## Test your configuration

In a private browser window, or with `curl -I`, request a few of the blocked paths and check that you get a `403 Forbidden` (or `404 Not Found`) response:

- `https://www.example.com/config/settings.ini.cfm`
- `https://www.example.com/core/tests/runner.cfm`
- `https://www.example.com/box.json`
- `https://www.example.com/.git/HEAD`

Then check that the public site, the admin and the front-end editing tools still work.
