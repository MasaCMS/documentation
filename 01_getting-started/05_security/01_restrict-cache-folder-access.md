---
layout: default
title: Restrict access to the cache folder
nav_order: 1
grand_parent: Getting started
parent: Security
last_modified_date: 23-10-2026 12:00
permalink: /getting-started/security/restrict-cache-folder-access/
---

# Restrict access to the cache folder

{: .warning}
If you use the extranet functionality (content restricted to logged-in users or groups), you **must** block direct web access to the file cache folder. Otherwise, restricted files can be downloaded by anyone who knows their URL.

## Why this is needed

When you upload a file to Masa CMS (for example a File content item, or the Associated Image of a content item), it is stored on disk in the site's cache folder:

```
{webroot}/sites/{siteid}/cache/file/{fileid}.{ext}
```

When a visitor opens a restricted File content item through its regular URL (for example `https://www.example.com/members/annual-report/`), Masa CMS checks whether the visitor is logged in and has access before it sends the file.

The file itself, however, still sits inside the webroot. By default, the web server serves anything in that folder directly, without passing the request to Masa CMS. Anyone who knows the direct URL, for example:

```
https://www.example.com/sites/default/cache/file/2D1F3C4A-....pdf
```

can download the file without logging in. The file IDs are hard to guess, but direct URLs leak easily: through shared links, browser history, proxy logs, or search engines that indexed the file while it was still public.

Block direct access to this folder in your web server so that files are only delivered through Masa CMS.

## Keep images working

By default, Masa CMS links images directly to the cache folder (for example `/sites/default/cache/file/{fileid}_large.jpg`) for performance. If you block the whole folder, images on your site stop working.

The rules on this page therefore block everything in `cache/file/` **except** image files. Documents such as PDF, Word, Excel and ZIP files can then only be downloaded through Masa CMS, which enforces the access permissions.

{: .note}
With these rules, images that are part of restricted content are still reachable through their direct URL. If those images are sensitive as well, see [Also protecting images](#also-protecting-images).

## Web server configuration

The examples below allow `jpg`, `jpeg`, `png`, `gif`, `webp`, `avif` and `svg` files and return `403 Forbidden` for everything else in any site's `cache/file/` folder. Adjust the list of extensions to the image types your sites use.

{: .important}
The configurations below are examples. Every server setup is different, so review and test them before using them in production. The system administrator is responsible for the final web server configuration and for verifying that it blocks access as intended.

### Apache

Add the following rules to the `.htaccess` file in the root of your Masa CMS instance (see `htaccess.txt`), inside the `<IfModule mod_rewrite.c>` block, directly after `RewriteBase /` and **before** the Masa CMS rewrite rules:

```apache
# Block direct access to non-image files in the file cache
RewriteCond %{REQUEST_URI} ^/sites/[^/]+/cache/file/ [NC]
RewriteCond %{REQUEST_URI} !\.(jpe?g|png|gif|webp|avif|svg)$ [NC]
RewriteRule ^ - [F]
```

If you configure Apache in a virtual host instead of `.htaccess`, the same rules work in the `<VirtualHost>` block.

### IIS

This requires the [IIS URL Rewrite module](https://www.iis.net/downloads/microsoft/url-rewrite). Add the following rule to the `web.config` file in the root of your Masa CMS instance (see `web.config.txt`), as the **first** rule inside `<rewrite><rules>`:

```xml
<rule name="Block direct access to non-image files in the file cache" stopProcessing="true">
  <match url="^sites/[^/]+/cache/file/" ignoreCase="true" />
  <conditions>
    <add input="{URL}" pattern="\.(jpe?g|png|gif|webp|avif|svg)$" ignoreCase="true" negate="true" />
  </conditions>
  <action type="CustomResponse" statusCode="403" statusReason="Forbidden" statusDescription="Access denied" />
</rule>
```

### Nginx

Add the following `location` block to the `server` block of your site, **before** any other regex `location` blocks (for example blocks that serve static files such as `.pdf`). Nginx uses the first regex location that matches.

```nginx
# Block direct access to non-image files in the file cache
location ~* ^/sites/[^/]+/cache/file/(?!.*\.(jpe?g|png|gif|webp|avif|svg)$) {
    return 403;
}
```

### Other web servers

For other web servers or proxies (for example Tomcat or CommandBox), add an equivalent rule: deny requests to `/sites/{any siteid}/cache/file/` unless the path ends in an allowed image extension.

## Custom file locations

The path above is the default. Adjust the rules if your setup differs:

- **`filedir` setting**: if `filedir` in `/config/settings.ini.cfm` points to another location inside the webroot, use that path instead of `/sites`. See [Configuration file](/getting-started/configuration/configuration-file/).
- **Shared file pool**: when a site uses the file pool of another site, its files are stored under the other site's ID. The `[^/]+` in the rules above covers all site IDs.
- **Context path**: if Masa CMS runs in a subfolder (for example `/masa/`), add that prefix to the paths in the rules.
- **Amazon S3**: if files are stored in S3, the web server rules do not apply. Make sure the bucket does not allow public access to restricted files.

## Also protecting images

If images in restricted content must be protected too, you can tell Masa CMS to deliver images through Masa CMS instead of linking to the cache folder directly. Add the following to the `contentRenderer.cfc` of your site or theme:

```cfml
this.directImages = false;
```

Images are then served through `/index.cfm/_api/render/...` URLs. After reloading the application, you can remove the image exception and block the complete `cache/file/` folder. For Apache, for example:

```apache
RewriteRule ^sites/[^/]+/cache/file/ - [F,NC]
```

This costs some performance, because every image request is handled by Masa CMS instead of directly by the web server.

## The assets folder is always public

Files uploaded through the file browser or the rich text editor are stored in `/sites/{siteid}/assets/`. These files are **not** linked to content permissions and are always publicly available. Never upload confidential documents through the file browser. Use a File content item inside a restricted section instead.

## Test your configuration

1. Upload a PDF as a File content item in a restricted section of your site.
2. Find its file ID, for example in the `tfiles` table of the database.
3. In a private browser window (not logged in), open `https://www.example.com/sites/{siteid}/cache/file/{fileid}.pdf`. You should get a `403 Forbidden` response.
4. Open the regular URL of the File content item. You should be asked to log in, and after logging in with an account that has access, the file should download.
5. Check that images on your public pages still load.
