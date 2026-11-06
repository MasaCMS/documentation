---
layout: default
title: Sessions and cookies
nav_order: 6
grand_parent: Getting started
parent: Security
last_modified_date: 23-10-2026 12:00
permalink: /getting-started/security/sessions-and-cookies/
---

# Sessions and cookies

After logging in, a user is identified by a session cookie. Anyone who gets hold of that cookie can act as the user. The settings on this page make session cookies harder to steal and limit how long a stolen cookie is useful.

All `settings.ini.cfm` settings below go in `/config/settings.ini.cfm` and take effect after reloading Masa CMS.

## Only send cookies over HTTPS

```ini
securecookies=true
```

With this setting, browsers only send Masa CMS cookies over HTTPS connections, so they cannot be read on an unencrypted connection. It is disabled by default. Enable it as soon as your site and admin are only available over HTTPS. See [HTTPS and security headers](/getting-started/security/https-and-security-headers/).

## Expire cookies when the browser closes

```ini
sessioncookiesexpires=session only
```

By default (`never`), the session cookies are stored permanently in the browser. With `session only`, they are removed when the browser is closed. This is especially useful when people use shared computers.

## Session timeout

```ini
sessiontimeout=180
```

The number of minutes of inactivity after which a session ends. The default is `180` (3 hours). A shorter timeout reduces how long a forgotten or stolen session can be used. Choose a value that balances security with how long your editors work without saving.

## Cookie domain and path

```ini
cookiedomain=
cookiepath=
```

Leave `cookiedomain` empty unless you need to share the login between subdomains. A value such as `.example.com` sends the session cookie to **every** subdomain of `example.com`, including ones that are not part of Masa CMS. If one of those is compromised, it can read your Masa CMS sessions.

## HttpOnly

Masa CMS sets its cookies as `HttpOnly` by default, which means JavaScript in the browser cannot read them. This limits the damage of a cross-site scripting attack. No configuration is needed.

## SameSite

The `SameSite` attribute tells browsers not to send the cookie with requests that come from other sites. This helps against cross-site request forgery. Masa CMS does not set this attribute itself. Configure it for the session cookies of your CFML engine, for example in `/config/cfapplication.cfm`, which Masa CMS includes in its `Application.cfc`:

```cfml
<cfset this.sessioncookie.samesite = "Lax">
```

This requires a recent version of Lucee or Adobe ColdFusion. You can also set it in the administrator of your CFML engine. Use `Lax` rather than `Strict`: with `Strict`, users who follow a link to your site from another site, such as an email, appear to be logged out.

## Leave session management to Masa CMS

```ini
managesessioncookies=true
```

This default lets Masa CMS set the session cookies itself, so the settings on this page are applied. Keep it enabled.
