---
layout: default
title: Lock down the admin
nav_order: 4
grand_parent: Getting started
parent: Security
last_modified_date: 23-10-2026 12:00
permalink: /getting-started/security/lock-down-admin/
---

# Lock down the admin

The Masa CMS admin gives full control over your sites. By default it is available at `/admin` on every domain of your installation. Reduce who can reach it.

## Restrict access by IP address

The strongest measure is to only allow the admin from trusted networks, such as your office network or a VPN. Requests from anywhere else are refused by the web server before they reach Masa CMS.

{: .important}
The configurations below are examples. Review and test them for your own setup. Replace `203.0.113.0/24` with your own trusted IP addresses or ranges.

{: .note}
Editors who use the front-end editing tools on the public site also need access to the admin. Make sure they connect from an allowed network.

### Apache

Add the following to the `<VirtualHost>` of your site:

```apache
<LocationMatch "(?i)^/admin(/|$)">
    Require ip 203.0.113.0/24
</LocationMatch>
```

### IIS

This requires the **IP and Domain Restrictions** role service. Add the following to the `web.config` in the root of your Masa CMS instance, as a sibling of the main `<system.webServer>` element:

```xml
<location path="admin">
  <system.webServer>
    <security>
      <ipSecurity allowUnlisted="false">
        <add ipAddress="203.0.113.0" subnetMask="255.255.255.0" allowed="true" />
      </ipSecurity>
    </security>
  </system.webServer>
</location>
```

If IIS reports that this section is locked, unlock `ipSecurity` at the server level first.

### Nginx

Add the following to the `server` block of your site. Because `^~` stops Nginx from checking regex locations, repeat the directives that pass CFML requests to the CFML engine inside this block.

```nginx
location ^~ /admin/ {
    allow 203.0.113.0/24;
    deny all;

    # Your existing directives that pass requests to the CFML engine
}
```

### Behind a proxy or load balancer

If a proxy, load balancer or CDN sits in front of your web server, the web server sees the IP address of the proxy instead of the visitor. Configure the web server to read the real client IP from the proxy's header (for example `mod_remoteip` for Apache or `real_ip` for Nginx), and only trust that header from your proxy's addresses. Otherwise, either everyone or no one gets access.

## Use a separate admin domain

With the `admindomain` setting in `/config/settings.ini.cfm`, the admin is only available on the domain you specify. Masa CMS refuses admin requests on all other domains, including the domains of your sites, and handles them as a regular page request for that path, which normally shows the 404 page.

```ini
admindomain=admin.example.com
```

A separate admin domain has several advantages:

- **Extra protection for the admin only.** You can put IP restrictions, a VPN, a web application firewall or a single sign-on proxy in front of the admin domain, without affecting visitors of the public sites.
- **Separate certificates and web server configuration.** The admin domain can have its own virtual host with stricter rules than the public sites.
- **Less exposure.** Automated scanners that try `/admin` on your public domains no longer find a login page.

### Multiple admin domains

Updated in 7.6.0
{: .label .label-orange }

`admindomain` accepts a comma-separated list of domains. This is needed when your installation runs sites on different domains, for example `site-a.com` and `site-b.com`. Give each site its own admin domain under the same domain name:

```ini
admindomain=admin.site-a.com,admin.site-b.com
```

The admin is then available on each domain in the list, and refused on every other domain. Links to the admin, such as those used by the front-end editing tools, use the admin domain the current request came in on.

### Set up the admin domain

1. Point the DNS of each admin domain to your Masa CMS server.
2. Add the admin domains to your web server configuration, and make sure a valid certificate covers them. The admin requires HTTPS by default (`forceadminssl=true`).
3. Add the domains to `admindomain` in `/config/settings.ini.cfm`.
4. Reload Masa CMS.
5. Check that the admin works on each admin domain, and that `/admin` on your site domains no longer shows the admin login.

{: .note}
Don't list the domains of your sites in `admindomain`. The admin would then be available on those domains again, which removes the benefit of a separate admin domain.

## Disable the admin on public servers

If you run Masa CMS in a cluster where editors work on a separate, internal authoring server, you can switch off the admin completely on the servers that serve the public sites:

```ini
disableadmin=true
```

On a server with this setting, requests to the admin are handled as a regular page request for that path, which normally shows the 404 page. The front-end editing tools are not available either, because they rely on the admin. Masa CMS must be reloaded for this change to take effect. See [Configuration file](/getting-started/configuration/configuration-file/).

For a complete setup, see [Separate authoring and public environment](/getting-started/installation/separate-authoring-public/).

## Change the admin folder

The `admindir` setting moves the admin to another path than `/admin`:

```ini
admindir=/backoffice
```

This reduces noise from automated scanners that look for `/admin`, but it is not a security measure on its own: the path is easy to discover. Use it together with the measures above. Masa CMS must be reloaded from the webroot for this change to take effect.

## Always use HTTPS

The `forceadminssl` setting redirects the admin to `https://`. It is enabled by default. Keep it enabled, and make sure a valid certificate is installed. See [HTTPS and security headers](/getting-started/security/https-and-security-headers/).

## Protect the CFML engine administrator

The administrator of your CFML engine is at least as powerful as the Masa CMS admin. Make sure it is not reachable from the internet:

- Lucee: `/lucee/` (including `/lucee/admin/`)
- Adobe ColdFusion: `/CFIDE/` (including `/CFIDE/administrator/`)

Block these paths in the web server, or only allow them from trusted IP addresses, in the same way as the Masa CMS admin above.
