---
layout: default
title: Login and passwords
nav_order: 5
grand_parent: Getting started
parent: Security
last_modified_date: 23-10-2026 12:00
permalink: /getting-started/security/login-and-passwords/
---

# Login and passwords

Stolen or guessed passwords are one of the most common ways into a CMS. Masa CMS has several settings to make accounts harder to take over. All settings on this page go in `/config/settings.ini.cfm` and take effect after reloading Masa CMS.

## Multi-factor authentication

Multi-factor authentication (MFA) asks users for an authorization code after they enter their password. A stolen password alone is then no longer enough to log in. MFA applies to both the admin login and the login on your sites.

```ini
mfa=true
```

### Codes by email

With only `mfa=true`, Masa CMS generates a code at every login and sends it to the user's email address (`mfasendauthcode=true`, the default). Make sure every user has a valid email address and that Masa CMS can send email before you enable this.

### Codes from an authenticator app

The [MasaAuthenticator](https://github.com/MasaCMS/MasaAuthenticator) module replaces the email codes with codes from an authenticator app on the user's phone. This is more secure, because a compromised mailbox is then not enough to log in.

1. Place the module in a `modules` directory, for example `{MasaRoot}/modules/MasaAuthenticator`.
2. In `/config/settings.ini.cfm`, set `mfa=true` and `mfasendauthcode=false`, so users don't also receive codes by email.
3. Reload Masa CMS.
4. The next time users log in, they are asked to set up an authenticator app.

Users who lose their device and have no backup codes left need an administrator to reset their access. Agree on a procedure for this before enabling MFA.

### Trusted devices

```ini
mfaperdevice=true
```

With this setting, users can mark a device as trusted after entering a code. Later logins from that device only ask for a username and password. This is more convenient, but also weaker: anyone with access to a trusted device only needs the password. Don't use it if your editors work on shared computers.

## Lock accounts after failed logins

```ini
loginstrikes=4
```

After this number of failed login attempts, the account is locked for 10 minutes. The default is `4`.

The lock applies to a username, not to an IP address. It slows down attacks on a single account, but not an attacker who tries one common password against many usernames. To also stop that, limit the number of login requests per IP address in your web server, web application firewall or a tool such as fail2ban.

## Enforce strong passwords

```ini
strongpasswords=true
```

When enabled, new passwords must match the regular expression in `strongpasswordregex`. It is disabled by default.

The default expression requires 7 to 15 characters with at least one letter and one digit. Current guidance favours longer passwords over complex ones, so consider requiring a longer minimum and removing the maximum, for example at least 12 characters:

```ini
strongpasswordregex=(?=^.{12,}$)(?=.*\d)(?=.*[a-zA-Z]).*$
```

Update the password hint shown to users so it matches your rule.

## Password storage

```ini
encryptpasswords=true
bcryptpasswords=true
```

Both are enabled by default: passwords are stored as BCrypt hashes. Keep these settings enabled.

## Single sign-on

If users log in through single sign-on, limit who gets an account:

- `alloweddomain`: only users with an email address in these domains can log in. Other users are created, but set to inactive.
- `allowedadmindomain`: users with an email address in these domains become **system users** with access to the admin. Keep this list as short as possible.

## Default and unused accounts

- Make sure no account uses default or shared credentials, such as the `admin`/`admin` account of a local development setup.
- Give every editor a personal account, so that actions can be traced and access can be revoked per person.
- Remove or deactivate accounts of people who no longer need access.
- Give users only the permissions they need. See [Permissions](/managing-masa/permissions/).
