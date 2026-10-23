---
layout: default
title: Production checklist
nav_order: 8
grand_parent: Getting started
parent: Security
last_modified_date: 23-10-2026 12:00
permalink: /getting-started/security/production-checklist/
---

# Production checklist

Go through this checklist before putting a Masa CMS installation into production, and again after major changes to the server. Settings go in `/config/settings.ini.cfm` and take effect after reloading Masa CMS.

## Masa CMS settings

- [ ] **Turn off debugging.** `debuggingenabled` is `true` by default, which shows CFML errors, including file paths and code, in the browser. Set `debuggingenabled=false`.
- [ ] **Use a custom error page.** With debugging off, the page in `errortemplate` is shown when an error occurs. Point it to a page that matches your site and reveals no technical details.
- [ ] **Change the reload key.** Anyone who adds `?appreload` to a URL reloads the whole application, which is slow and uses a lot of server resources. Set `appreloadkey` to a long, random value and keep it private.
- [ ] **Set an encryption key.** The default `encryptionkey` is derived from the installation path. Set it to a long, random value.
- [ ] **Only set `remoteipheader` behind a trusted proxy.** Masa CMS uses this header as the visitor's IP address without further checks. If the server is not behind a proxy or load balancer that always overwrites the header, visitors can fake their IP address. Also make sure the server cannot be reached directly, bypassing the proxy.

## Accounts and access

- [ ] [Lock down the admin](/getting-started/security/lock-down-admin/), including the administrator of your CFML engine.
- [ ] [Enable multi-factor authentication, account lockout and strong passwords](/getting-started/security/login-and-passwords/).
- [ ] Make sure no account uses default credentials, and remove accounts that are no longer used.
- [ ] Consider a [separate authoring and public environment](/getting-started/installation/separate-authoring-public/), so the admin is not reachable from the internet at all.

## Web server

- [ ] [Redirect to HTTPS and add security headers](/getting-started/security/https-and-security-headers/).
- [ ] [Protect internal folders and files](/getting-started/security/protect-internal-files/), and remove development and test files from the server.
- [ ] [Never run scripts from upload folders](/getting-started/security/secure-upload-folders/).
- [ ] [Restrict access to the cache folder](/getting-started/security/restrict-cache-folder-access/) if you use restricted content.
- [ ] [Secure session cookies](/getting-started/security/sessions-and-cookies/).
- [ ] Disable directory listings. The `htaccess.txt` file shipped with Masa CMS does this for Apache with `Options -Indexes`.

## CFML engine and server

- [ ] Follow the lockdown guide for your CFML engine: the [Lucee Lockdown Guide](https://docs.lucee.org/guides/deploying-lucee-server-apps/lockdown-guide.html) or the [Adobe ColdFusion 2025 Lockdown Guide](https://www.adobe.com/cc-shared/assets/pdf/products/coldfusion-family/coldfusion-2025-lockdown-guide-1-1.pdf) (PDF).
- [ ] Turn off detailed error output and debugging in the CFML engine administrator.
- [ ] Run the CFML engine as a dedicated user without administrator rights. Only give it write access to the folders Masa CMS needs to write to, such as the `assets` and `cache` folders of each site and the `plugins` folder.
- [ ] Use a dedicated database user for Masa CMS with only the permissions it needs, and make sure the database server is not reachable from the internet.

## Keep it up to date

- [ ] Install Masa CMS updates promptly. Security fixes are announced in the [security advisories](https://github.com/MasaCMS/MasaCMS/security/advisories) on GitHub.
- [ ] Keep the CFML engine, Java, the web server and the operating system up to date.
- [ ] Only install plugins and modules from sources you trust, and keep them updated too.
- [ ] Make regular backups of the database and the files, and test restoring them.
