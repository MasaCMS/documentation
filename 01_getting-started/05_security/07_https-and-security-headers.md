---
layout: default
title: HTTPS and security headers
nav_order: 7
grand_parent: Getting started
parent: Security
last_modified_date: 23-10-2026 12:00
permalink: /getting-started/security/https-and-security-headers/
---

# HTTPS and security headers

Serve every site and the admin over HTTPS only, and send HTTP headers that tell browsers to apply extra protections.

{: .important}
The configurations below are examples. Review and test them for your own setup.

## Redirect HTTP to HTTPS

Redirect all plain HTTP requests to HTTPS in the web server.

{: .note}
If HTTPS is handled by a load balancer or proxy in front of the web server, the web server receives plain HTTP and these rules cause a redirect loop. In that case, redirect at the load balancer, or check the `X-Forwarded-Proto` header instead.

### Apache

In the `<VirtualHost *:80>` of your site:

```apache
RewriteEngine On
RewriteRule ^ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```

### IIS

At the top of `<rewrite><rules>` in your `web.config`:

```xml
<rule name="Redirect to HTTPS" stopProcessing="true">
  <match url="(.*)" />
  <conditions>
    <add input="{HTTPS}" pattern="^OFF$" />
  </conditions>
  <action type="Redirect" url="https://{HTTP_HOST}/{R:1}" redirectType="Permanent" />
</rule>
```

### Nginx

```nginx
server {
    listen 80;
    server_name www.example.com;
    return 301 https://$host$request_uri;
}
```

## HTTP Strict Transport Security (HSTS)

HSTS tells browsers to only connect to your site over HTTPS for a set period, even when a user types `http://`.

Masa CMS sends this header itself, controlled by the `hstsmaxage` setting in `/config/settings.ini.cfm`. The value is in seconds. The default of `1200` (20 minutes) is very short. Once HTTPS works correctly on all your sites, raise it to one year:

```ini
hstsmaxage=31536000
```

Masa CMS only adds this header to responses it generates itself, not to static files served directly by the web server. If you want the header on every response, or want to add `includeSubDomains`, set it in the web server instead and set `hstsmaxage=0` to avoid sending the header twice.

{: .warning}
Only raise the HSTS duration when you are sure HTTPS works on all domains. Browsers remember the setting: if HTTPS breaks, visitors cannot reach the site until the period ends.

## Security headers

These headers are safe for most Masa CMS sites:

| Header | Value | Purpose |
|--------|-------|---------|
| `X-Content-Type-Options` | `nosniff` | Stops browsers from guessing file types, for example running an uploaded file as a script |
| `Referrer-Policy` | `strict-origin-when-cross-origin` | Limits which URL information is shared with other sites |
| `X-Frame-Options` | `SAMEORIGIN` | Stops other sites from showing your pages in a frame (clickjacking) |
| `Permissions-Policy` | `camera=(), microphone=(), geolocation=()` | Disables browser features your site does not use |

{: .note}
If the admin runs on a different domain than the site (see `admindomain` in [Lock down the admin](/getting-started/security/lock-down-admin/)), test the front-end editing tools after adding `X-Frame-Options`.

### Content Security Policy

A `Content-Security-Policy` header gives the strongest protection against cross-site scripting, but it must be tailored to your site: themes, modules, analytics and embedded content all load resources from different places. The Masa CMS admin and front-end editing tools also rely on inline scripts. Start with a `Content-Security-Policy-Report-Only` header, review the reported violations, and only switch to enforcing the policy when nothing legitimate is blocked anymore.

### Hide version information

Masa CMS sends a `Generator` header containing its version number. Version information helps attackers find installations that are missing security updates. Remove it, together with headers such as `X-Powered-By`, in the web server.

### Apache

```apache
<IfModule mod_headers.c>
    Header always set X-Content-Type-Options "nosniff"
    Header always set Referrer-Policy "strict-origin-when-cross-origin"
    Header always set X-Frame-Options "SAMEORIGIN"
    Header always set Permissions-Policy "camera=(), microphone=(), geolocation=()"

    Header unset Generator
    Header always unset Generator
    Header unset X-Powered-By
    Header always unset X-Powered-By
</IfModule>
```

### IIS

Inside `<system.webServer>` in your `web.config`:

```xml
<httpProtocol>
  <customHeaders>
    <add name="X-Content-Type-Options" value="nosniff" />
    <add name="Referrer-Policy" value="strict-origin-when-cross-origin" />
    <add name="X-Frame-Options" value="SAMEORIGIN" />
    <add name="Permissions-Policy" value="camera=(), microphone=(), geolocation=()" />
    <remove name="X-Powered-By" />
  </customHeaders>
</httpProtocol>
```

The `Generator` header is added by Masa CMS, so IIS cannot remove it with `customHeaders`. Use an outbound rule in `<rewrite>` to clear it:

```xml
<outboundRules>
  <rule name="Clear Generator header">
    <match serverVariable="RESPONSE_Generator" pattern=".+" />
    <action type="Rewrite" value="" />
  </rule>
</outboundRules>
```

### Nginx

In the `server` block of your site:

```nginx
add_header X-Content-Type-Options "nosniff" always;
add_header Referrer-Policy "strict-origin-when-cross-origin" always;
add_header X-Frame-Options "SAMEORIGIN" always;
add_header Permissions-Policy "camera=(), microphone=(), geolocation=()" always;

proxy_hide_header Generator;
proxy_hide_header X-Powered-By;
```

Nginx only inherits `add_header` directives from the `server` block when a `location` block has no `add_header` of its own. If a `location` adds a header, repeat the security headers there.

## Test your configuration

Check the response headers of your site with the developer tools of your browser, or with `curl -I https://www.example.com/`. Online scanners can also check your HTTPS configuration and headers.
