---
layout: default
title: Security
nav_order: 5
parent: Getting started
has_children: true
last_modified_date: 23-10-2026 12:00
permalink: /getting-started/security/
---

# Security & server lockdown

A default Masa CMS installation is set up to get you started quickly, not to be as secure as possible. Before you put a site into production, take extra measures to harden Masa CMS, your web server and the application server it runs on.

This section collects those security and lockdown measures. Each page describes one measure: what risk it addresses, when it applies to your setup, and how to configure it. Some measures apply to every installation. Others only matter when you use a specific feature.

{: .important}
Configuration snippets in this section are examples. Every server setup is different, so review and test them before using them in production. The system administrator is responsible for the final configuration of the server and for verifying that it works as intended.

## Measures

Start with the [Production checklist](/getting-started/security/production-checklist/), which brings all measures together.

- [Restrict access to the cache folder](/getting-started/security/restrict-cache-folder-access/): block direct web access to uploaded files, so that content restrictions (extranet) cannot be bypassed.
- [Protect internal folders and files](/getting-started/security/protect-internal-files/): keep configuration, tooling, logs and source control files out of reach.
- [Secure upload folders](/getting-started/security/secure-upload-folders/): never run server-side scripts from folders that contain uploaded files.
- [Lock down the admin](/getting-started/security/lock-down-admin/): limit who can reach the Masa CMS admin and the CFML engine administrator.
- [Login and passwords](/getting-started/security/login-and-passwords/): multi-factor authentication, account lockout and password rules.
- [Sessions and cookies](/getting-started/security/sessions-and-cookies/): make session cookies harder to steal and shorten how long they are valid.
- [HTTPS and security headers](/getting-started/security/https-and-security-headers/): enforce HTTPS and let browsers apply extra protections.
- [Production checklist](/getting-started/security/production-checklist/): everything to check before going live.

## CFML engine lockdown guides

Masa CMS runs on a CFML engine, which needs to be locked down as well. Both vendors publish a lockdown guide:

- [Lucee Lockdown Guide](https://docs.lucee.org/guides/deploying-lucee-server-apps/lockdown-guide.html)
- [Adobe ColdFusion 2025 Lockdown Guide](https://www.adobe.com/cc-shared/assets/pdf/products/coldfusion-family/coldfusion-2025-lockdown-guide-1-1.pdf) (PDF)
