---
layout: default
title: Release notes
nav_order: 7
last_modified_date: 08-12-2025 10:00
permalink: /release-notes/
---

# Release notes
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

- TOC
{:toc}

## 7.6

### What's Changed

#### New features

* Allow for setting 'admindomain' to be a list

#### Bug fixes

* Set correct oderNo when inserting content with topOrBottom set to "bottom" by @boris-schwarz in https://github.com/MasaCMS/MasaCMS/pull/415
* 449 content type templates from global modules are never found settingsbeancfc property typo by @guustnieuwenhuis in https://github.com/MasaCMS/MasaCMS/pull/450
* Shared file pool ur ls generate incorrect paths causing 404 errors by @guustnieuwenhuis in https://github.com/MasaCMS/MasaCMS/pull/452
* Enhance sanitizeHref function to improve security and handle edge cases for URL sanitization
* Additional tests for sanitizehref by @guustnieuwenhuis in https://github.com/MasaCMS/MasaCMS/pull/453

Thank you @jindalvinay and @lbojko81 for your help with the bug fixes.

**Full Changelog**: https://github.com/MasaCMS/MasaCMS/compare/7.5.5...7.6.0


## 8.0.0-alpha.2

{: .warning }
This is an alpha release. It is not intended for production use. Breaking changes are expected.

### Overview
{: .no_toc }

This release brings the 8.0 alpha line up to date with the security fixes shipped in Masa CMS 7.5.5. It contains no additional features on top of 8.0.0-alpha.1.

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }

The multiple critical, high and moderate vulnerabilities fixed in Masa CMS 7.5.5 also affected the 8.0.0-alpha.1 codebase.

#### What is fixed ?
{: .no_toc }

* The vulnerabilities fixed in 7.5.5 have been merged into the 8.0 alpha line.

#### What versions are affected?
{: .no_toc }

Masa CMS 8.0.0-alpha.1 is affected.

#### What should you upgrade ?
{: .no_toc }

* If you're evaluating Masa CMS 8.0.0-alpha.1, you should upgrade to 8.0.0-alpha.2.

### What's Changed
{: .no_toc }

* Expression Evaluation improvements
* Privilege escalation improvements
* SSRF improvements
* SQL injection protection improvements
* Redirect improvements

Full Changelog: [8.0.0-alpha.1...8.0.0-alpha.2](https://github.com/MasaCMS/MasaCMS/compare/8.0.0-alpha.1...8.0.0-alpha.2)


## 7.5.5

## Security Vulnerability Fix
{: .no_toc }

### What was the issue ?
{: .no_toc }

We've been informed multiple critical, high and moderate vulnerabilities in Masa CMS.

### What is fixed ?
{: .no_toc }

* The mentioned vulnerabilities have been fixed.

### What versions are affected?
{: .no_toc }

Masa CMS versions 7.2, 7.3, 7.4 and 7.5 are affected.

### What should you upgrade ?
{: .no_toc }

* If you’re on Masa CMS 7.5, you should update to version 7.5.5 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
* If you’re on Masa CMS 7.4, you should update to version 7.4.12 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.3, you should update to version 7.3.17 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.2, you should update to version 7.2.12 immediately. This can be done by applying a manual update.

If an immediate upgrade is not possible, review the workarounds in the security advisories.

## What's Changed
{: .no_toc }

* Expression Evaluation improvements
* Privilege escalation improvements
* SSRF improvements
* SQL injection protection improvements
* Redirect improvements

Full Changelog: [7.5.4...7.5.5](https://github.com/MasaCMS/MasaCMS/compare/7.5.4...7.5.5)


## 7.4.12

## Security Vulnerability Fix
{: .no_toc }

### What was the issue ?
{: .no_toc }

We've been informed multiple critical, high and moderate vulnerabilities in Masa CMS.

### What is fixed ?
{: .no_toc }

* The mentioned vulnerabilities have been fixed.

### What versions are affected?
{: .no_toc }

Masa CMS versions 7.2, 7.3, 7.4 and 7.5 are affected.

### What should you upgrade ?
{: .no_toc }

* If you’re on Masa CMS 7.5, you should update to version 7.5.5 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
* If you’re on Masa CMS 7.4, you should update to version 7.4.12 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.3, you should update to version 7.3.17 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.2, you should update to version 7.2.12 immediately. This can be done by applying a manual update.

If an immediate upgrade is not possible, review the workarounds in the security advisories.

## What's Changed
{: .no_toc }

* Expression Evaluation improvements
* Privilege escalation improvements
* SSRF improvements
* SQL injection protection improvements
* Redirect improvements

Full Changelog: [7.4.11...7.4.12](https://github.com/MasaCMS/MasaCMS/compare/7.4.11...7.4.12)


## 7.3.17

## Security Vulnerability Fix
{: .no_toc }

### What was the issue ?
{: .no_toc }

We've been informed multiple critical, high and moderate vulnerabilities in Masa CMS.

### What is fixed ?
{: .no_toc }

* The mentioned vulnerabilities have been fixed.

### What versions are affected?
{: .no_toc }

Masa CMS versions 7.2, 7.3, 7.4 and 7.5 are affected.

### What should you upgrade ?
{: .no_toc }

* If you’re on Masa CMS 7.5, you should update to version 7.5.5 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
* If you’re on Masa CMS 7.4, you should update to version 7.4.12 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.3, you should update to version 7.3.17 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.2, you should update to version 7.2.12 immediately. This can be done by applying a manual update.

If an immediate upgrade is not possible, review the workarounds in the security advisories.

## What's Changed
{: .no_toc }

* Expression Evaluation improvements
* Privilege escalation improvements
* SSRF improvements
* SQL injection protection improvements
* Redirect improvements

Full Changelog: [7.3.16...7.3.17](https://github.com/MasaCMS/MasaCMS/compare/7.3.16...7.3.17)


## 7.2.12

## Security Vulnerability Fix
{: .no_toc }

### What was the issue ?
{: .no_toc }

We've been informed multiple critical, high and moderate vulnerabilities in Masa CMS.

### What is fixed ?
{: .no_toc }

* The mentioned vulnerabilities have been fixed.

### What versions are affected?
{: .no_toc }

Masa CMS versions 7.2, 7.3, 7.4 and 7.5 are affected.

### What should you upgrade ?
{: .no_toc }

* If you’re on Masa CMS 7.5, you should update to version 7.5.5 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
* If you’re on Masa CMS 7.4, you should update to version 7.4.12 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.3, you should update to version 7.3.17 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.2, you should update to version 7.2.12 immediately. This can be done by applying a manual update.

If an immediate upgrade is not possible, review the workarounds in the security advisories.

## What's Changed
{: .no_toc }

* Expression Evaluation improvements
* Privilege escalation improvements
* SSRF improvements
* SQL injection protection improvements
* Redirect improvements

Full Changelog: [7.2.11...7.2.12](https://github.com/MasaCMS/MasaCMS/compare/7.2.11...7.2.12)


## 8.0.0-alpha.1

{: .warning }
This is an alpha release. It is not intended for production use. Breaking changes are expected.

### Overview
{: .no_toc }

Masa CMS 8.0 is a major release focused on **expanded engine support**, **security hardening**, and **removal of deprecated features**. This alpha release marks the first milestone of the 8.0 series and adds support for Adobe ColdFusion 2025, Lucee 7, and BoxLang, alongside significant clean-up of legacy code.

### New: Supported CFML Engines
{: .no_toc }

Masa CMS 8.0 expands the list of supported CFML engines:

- **Adobe ColdFusion 2025** — now officially supported
- **Lucee 7** — now officially supported
- **BoxLang** — now officially supported

### BoxLang Compatibility
{: .no_toc }

Masa CMS 8.0 introduces broad compatibility with BoxLang. Extensive changes have been made across the codebase to ensure Masa CMS runs correctly on the BoxLang engine.

{: .important }
**Database creation is not supported in the BoxLang installation wizard.** When installing Masa CMS on BoxLang, the database must be created manually before running the setup.

### Security Improvements
{: .no_toc }

- BCrypt log rounds increased from 10 to 12 for stronger password hashing
- **Encryption default changed to SHA-256** — the default hash algorithm is now SHA-256 (previously MD5)
- **All passwords are now hashed with BCrypt** — the `encryptPasswords` Java-enabled setting has been removed; BCrypt is always used
- CSRF token generation hardened

### Dropped Engine Support
{: .no_toc }

{: .important }
Masa CMS 8.0 drops support for older CFML engines. Please upgrade your engine before migrating to 8.0.

The following CFML engines are **no longer supported** as of 8.0:

- **Adobe ColdFusion 2021 and earlier** — Adobe ColdFusion 2023 or 2025 is required
- **Lucee 5.4 and earlier** — Lucee 6 or 7 is required

### Breaking Changes & Removals
{: .no_toc }

The following features and settings have been **removed** in 8.0:

- **Legacy Sessions removed** — the `UseLegacySessions` setting has been removed. This was deprecated in 7.5. Only modern session management is supported going forward.
- **AWS S3 ACL support removed** — the `storeSetACL` setting and S3 ACL handling have been removed from application settings.
- **Razuna integration removed** — the Razuna file manager integration and its CKEditor plugin have been fully removed.
- **Non-BCrypt password functionality removed** — the `bCryptPassword` setting and the Java-enabled `encryptPasswords` option have been removed. BCrypt is now the only supported password hashing method.
- **Unsupported locales** removed
- Outdated Docker setup files removed

### Testing
{: .no_toc }

- TestBox dependency updated to version 6.5.0
- Test runner (`runner.cfm`) enhanced with detailed coverage options
- New unit tests added for `utility.cfc` date helper functions
- `contentIntervals.cfc` test coverage significantly expanded (including `alignToWeekday` and `GetNthDayOfMonth`)
- Unit tests added for blockfactor validation

Full Changelog: [7.5.4...8.0.0-alpha.1](https://github.com/MasaCMS/MasaCMS/compare/7.5.4...8.0.0-alpha.1)


## 7.5.4

### What's Changed
{: .no_toc }

- Allow dots in field names for sorting validation by [@guustnieuwenhuis](https://github.com/guustnieuwenhuis) in [#424](https://github.com/MasaCMS/MasaCMS/pull/424)

Full Changelog: [7.5.3...7.5.4](https://github.com/MasaCMS/MasaCMS/compare/7.5.3...7.5.4)


## 7.4.11

### What's Changed
{: .no_toc }

- Allow dots in field names for sorting validation by [@guustnieuwenhuis](https://github.com/guustnieuwenhuis) in [#424](https://github.com/MasaCMS/MasaCMS/pull/424)

Full Changelog: [7.4.11...7.4.10](https://github.com/MasaCMS/MasaCMS/compare/7.4.11...7.4.10)


## 7.3.16

### What's Changed
{: .no_toc }

- Allow dots in field names for sorting validation by [@guustnieuwenhuis](https://github.com/guustnieuwenhuis) in [#424](https://github.com/MasaCMS/MasaCMS/pull/424)

Full Changelog: [7.3.16...7.3.15](https://github.com/MasaCMS/MasaCMS/compare/7.3.16...7.3.15)


## 7.2.11

### What's Changed
{: .no_toc }

- Allow dots in field names for sorting validation by [@guustnieuwenhuis](https://github.com/guustnieuwenhuis) in [#424](https://github.com/MasaCMS/MasaCMS/pull/424)

Full Changelog: [7.2.11...7.2.10](https://github.com/MasaCMS/MasaCMS/compare/7.2.11...7.2.10)


## 7.5.3

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }
We've been informed multiple critical, high and moderate vulnerabilities in Masa CMS.

#### What is fixed ?
{: .no_toc }
The mentioned vulnerabilities have been fixed.

#### What versions are affected?
{: .no_toc }
Masa CMS versions 7.2, 7.3, 7.4 and 7.5 are affected.

#### What should you upgrade ?
{: .no_toc }
- If you’re on Masa CMS 7.5, you should update to version 7.5.3 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
- If you’re on Masa CMS 7.4, you should update to version 7.4.10 immediately. This can be done by applying a manual update.
- If you’re on Masa CMS 7.3, you should update to version 7.3.15 immediately. This can be done by applying a manual update.
- If you’re on Masa CMS 7.2, you should update to version 7.2.10 immediately. This can be done by applying a manual update.

If an immediate upgrade is not possible, review the workarounds in the security advisories.

### What's Changed
{: .no_toc }
- Npm audit fixes
- CSRF improvements
- SQL injection protection improvements
- Redirect improvements

Full Changelog: [7.5.2...7.5.3](https://github.com/MasaCMS/MasaCMS/compare/7.5.2...7.5.3)


## 7.4.10

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }
We've been informed multiple critical, high and moderate vulnerabilities in Masa CMS.

#### What is fixed ?
{: .no_toc }
The mentioned vulnerabilities have been fixed.

#### What versions are affected?
{: .no_toc }
Masa CMS versions 7.2, 7.3, 7.4 and 7.5 are affected.

#### What should you upgrade ?
{: .no_toc }
- If you’re on Masa CMS 7.5, you should update to version 7.5.3 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
- If you’re on Masa CMS 7.4, you should update to version 7.4.10 immediately. This can be done by applying a manual update.
- If you’re on Masa CMS 7.3, you should update to version 7.3.15 immediately. This can be done by applying a manual update.
- If you’re on Masa CMS 7.2, you should update to version 7.2.10 immediately. This can be done by applying a manual update.

If an immediate upgrade is not possible, review the workarounds in the security advisories.

### What's Changed
{: .no_toc }
- CSRF improvements
- SQL injection protection improvements
- Redirect improvements

Full Changelog: [7.4.9...7.4.10](https://github.com/MasaCMS/MasaCMS/compare/7.4.9...7.4.10)


## 7.3.15

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }
We've been informed multiple critical, high and moderate vulnerabilities in Masa CMS.

#### What is fixed ?
{: .no_toc }
The mentioned vulnerabilities have been fixed.

#### What versions are affected?
{: .no_toc }
Masa CMS versions 7.2, 7.3, 7.4 and 7.5 are affected.

#### What should you upgrade ?
{: .no_toc }
- If you’re on Masa CMS 7.5, you should update to version 7.5.3 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
- If you’re on Masa CMS 7.4, you should update to version 7.4.10 immediately. This can be done by applying a manual update.
- If you’re on Masa CMS 7.3, you should update to version 7.3.15 immediately. This can be done by applying a manual update.
- If you’re on Masa CMS 7.2, you should update to version 7.2.10 immediately. This can be done by applying a manual update.

If an immediate upgrade is not possible, review the workarounds in the security advisories.

### What's Changed
{: .no_toc }
- CSRF improvements
- SQL injection protection improvements
- Redirect improvements

Full Changelog: [7.3.14...7.3.15](https://github.com/MasaCMS/MasaCMS/compare/7.3.14...7.3.15)


## 7.2.10

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }
We've been informed multiple critical, high and moderate vulnerabilities in Masa CMS.

#### What is fixed ?
{: .no_toc }
The mentioned vulnerabilities have been fixed.

#### What versions are affected?
{: .no_toc }
Masa CMS versions 7.2, 7.3, 7.4 and 7.5 are affected.

#### What should you upgrade ?
{: .no_toc }
- If you’re on Masa CMS 7.5, you should update to version 7.5.3 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
- If you’re on Masa CMS 7.4, you should update to version 7.4.10 immediately. This can be done by applying a manual update.
- If you’re on Masa CMS 7.3, you should update to version 7.3.15 immediately. This can be done by applying a manual update.
- If you’re on Masa CMS 7.2, you should update to version 7.2.10 immediately. This can be done by applying a manual update.

If an immediate upgrade is not possible, review the workarounds in the security advisories.

### What's Changed
{: .no_toc }
- CSRF improvements
- SQL injection protection improvements
- Redirect improvements

Full Changelog: [7.2.9...7.2.10](https://github.com/MasaCMS/MasaCMS/compare/7.2.9...7.2.10)


## 7.5.2

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }
We've been informed about a high vulnerability in Masa CMS.

#### What is fixed ?
{: .no_toc }
The mentioned vulnerability has been fixed. A few bugs are fixed as well

#### What versions are affected?
{: .no_toc }
Masa CMS versions 7.2, 7.3, 7.4 and 7.5 are affected.

#### What should you upgrade ?
{: .no_toc }
- If you’re on Masa CMS 7.5, you should update to version 7.5.2 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
- If you’re on Masa CMS 7.4, you should update to version 7.4.9 immediately. This can be done by applying a manual update.
- If you’re on Masa CMS 7.3, you should update to version 7.3.14 immediately. This can be done by applying a manual update.
- If you’re on Masa CMS 7.2, you should update to version 7.2.9 immediately. This can be done by applying a manual update.

### What's Changed
{: .no_toc }
- Fixes Bug [#395](https://github.com/MasaCMS/MasaCMS/issues/395) key [columns] doesn't exist (beanFeed) by [@kb3hcg](https://github.com/kb3hcg) in [#396](https://github.com/MasaCMS/MasaCMS/pull/396)
- Add default parameters for objectParams by [@titiscan](https://github.com/titiscan) in [#400](https://github.com/MasaCMS/MasaCMS/pull/400)
- Skip empty styles in content rendering by [@titiscan](https://github.com/titiscan) in [#399](https://github.com/MasaCMS/MasaCMS/pull/399)
- Fix Shadowbox styling and functionality issues by [@titiscan](https://github.com/titiscan) in [#402](https://github.com/MasaCMS/MasaCMS/pull/402)


### New Contributors
{: .no_toc }
- [@kb3hcg](https://github.com/kb3hcg) made their first contribution in [#396](https://github.com/MasaCMS/MasaCMS/pull/396)

Full Changelog: [7.5.1...7.5.2](https://github.com/MasaCMS/MasaCMS/compare/7.5.1...7.5.2)

## 7.4.9

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }
We've been informed about a high vulnerability in Masa CMS.

#### What is fixed ?
{: .no_toc }
The mentioned vulnerability has been fixed. 

#### What versions are affected?
{: .no_toc }
Masa CMS versions 7.2, 7.3, 7.4 and 7.5 are affected.

#### What should you upgrade ?
{: .no_toc }
- If you’re on Masa CMS 7.5, you should update to version 7.5.2 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
- If you’re on Masa CMS 7.4, you should update to version 7.4.9 immediately. This can be done by applying a manual update.
- If you’re on Masa CMS 7.3, you should update to version 7.3.14 immediately. This can be done by applying a manual update.
- If you’re on Masa CMS 7.2, you should update to version 7.2.9 immediately. This can be done by applying a manual update.

Full Changelog: [7.4.8...7.4.9](https://github.com/MasaCMS/MasaCMS/compare/7.4.8...7.4.9)

## 7.3.14

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }
We've been informed about a high vulnerability in Masa CMS.

#### What is fixed ?
{: .no_toc }
The mentioned vulnerability has been fixed. 

#### What versions are affected?
{: .no_toc }
Masa CMS versions 7.2, 7.3, 7.4 and 7.5 are affected.

#### What should you upgrade ?
{: .no_toc }
- If you’re on Masa CMS 7.5, you should update to version 7.5.2 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
- If you’re on Masa CMS 7.4, you should update to version 7.4.9 immediately. This can be done by applying a manual update.
- If you’re on Masa CMS 7.3, you should update to version 7.3.14 immediately. This can be done by applying a manual update.
- If you’re on Masa CMS 7.2, you should update to version 7.2.9 immediately. This can be done by applying a manual update.

Full Changelog: [7.3.13..7.3.14](https://github.com/MasaCMS/MasaCMS/compare/7.3.13...7.3.14)

## 7.2.9

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }
We've been informed about a high vulnerability in Masa CMS.

#### What is fixed ?
{: .no_toc }
The mentioned vulnerability has been fixed. 

#### What versions are affected?
{: .no_toc }
Masa CMS versions 7.2, 7.3, 7.4 and 7.5 are affected.

#### What should you upgrade ?
{: .no_toc }
- If you’re on Masa CMS 7.5, you should update to version 7.5.2 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
- If you’re on Masa CMS 7.4, you should update to version 7.4.9 immediately. This can be done by applying a manual update.
- If you’re on Masa CMS 7.3, you should update to version 7.3.14 immediately. This can be done by applying a manual update.
- If you’re on Masa CMS 7.2, you should update to version 7.2.9 immediately. This can be done by applying a manual update.

Full Changelog: [7.2.8...7.2.9](https://github.com/MasaCMS/MasaCMS/compare/7.2.8...7.2.9)


## 7.5.1

### What's Changed
{: .no_toc }

- Fixed ACF Remote Functions for userBean.cfc by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) 
- Fixed ACF Remote Functions for filebrowser.cfc by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu)
- Fixed a very smal JS bug on an emai by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#364](https://github.com/MasaCMS/MasaCMS/pull/364)
- Use correct variable for deferred module by [@boris-schwarz](https://github.com/boris-schwarz) in [#382](https://github.com/MasaCMS/MasaCMS/pull/382)
- replace configbean usage in setup process by [@guustnieuwenhuis](https://github.com/guustnieuwenhuis) in [#386](https://github.com/MasaCMS/MasaCMS/pull/386)

### New Contributors
{: .no_toc }

* [@boris-schwarz](https://github.com/boris-schwarz) made their first contribution in [#382](https://github.com/MasaCMS/MasaCMS/pull/382)

Full Changelog: [7.5.0...7.5.1](https://github.com/MasaCMS/MasaCMS/compare/7.5.0...7.5.1)

## 7.5.0

### What's Changed
{: .no_toc }

- Azure multitenant ad by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#351](https://github.com/MasaCMS/MasaCMS/pull/351)
- Defer module.js to avoid blocking page rendering by [@nolanerck](https://github.com/nolanerck) in [#352](https://github.com/MasaCMS/MasaCMS/pull/352)
- Fix incorrect syntax by [@guustnieuwenhuis](https://github.com/guustnieuwenhuis) in [#355](https://github.com/MasaCMS/MasaCMS/pull/355)
- Fix filebrowser path for browsing files with CKEditor by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#356](https://github.com/MasaCMS/MasaCMS/pull/356)
- Add context to jquery.min.js path by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#362](https://github.com/MasaCMS/MasaCMS/pull/362)
- Upgrade 7.4.8 error by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#359](https://github.com/MasaCMS/MasaCMS/pull/359)
- Implement indexfileinapi setting correctly by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#363](https://github.com/MasaCMS/MasaCMS/pull/363)
- Update dependancies by [@plimpens](https://github.com/plimpens) in [#360](https://github.com/MasaCMS/MasaCMS/pull/360)
- Add 'UseLegacySessions' setting to deprecation warnings by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#368](https://github.com/MasaCMS/MasaCMS/pull/368)
- Set size of the password field in tusers table to 100 instead of 50. by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#371](https://github.com/MasaCMS/MasaCMS/pull/371)
- Add 'NonBCryptPasswords' setting to deprecation warnings by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#369](https://github.com/MasaCMS/MasaCMS/pull/369)
- Deprecate setstoreacl by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#370](https://github.com/MasaCMS/MasaCMS/pull/370)
- Update hash encrypt encode v2 by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#364](https://github.com/MasaCMS/MasaCMS/pull/364)
- Fix saving the canonical url by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#373](https://github.com/MasaCMS/MasaCMS/pull/373)


### New Contributors
{: .no_toc }

* [@plimpens](https://github.com/plimpens) made their first contribution in [#360](https://github.com/MasaCMS/MasaCMS/pull/360)

Full Changelog: [7.4.8...7.5.0](https://github.com/MasaCMS/MasaCMS/compare/7.4.8...7.5.0)


## 7.4.8

### What's Changed
{: .no_toc }

- Unsupported deprecated locales by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#332](https://github.com/MasaCMS/MasaCMS/pull/332)
- Bugfix filebrowser by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#336](https://github.com/MasaCMS/MasaCMS/pull/336)
- Upgrade fw1 update servicelist by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#331](https://github.com/MasaCMS/MasaCMS/pull/331)
- Add deprecation warning for 'UnSupportedLocale' by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#334](https://github.com/MasaCMS/MasaCMS/pull/334)
- Try / Catch reading the fileinfo for an alleged image. by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#337](https://github.com/MasaCMS/MasaCMS/pull/337)
- Add support for "open in new window" option within folder grid layout by [@titiscan](https://github.com/titiscan) in [#338](https://github.com/MasaCMS/MasaCMS/pull/338)
- Update ConfigBean to set a default on mfadayslinkvalid by [@wtconsulting](https://github.com/wtconsulting) in [#329](https://github.com/MasaCMS/MasaCMS/pull/329)
- Update filebrowser.js by [@wtconsulting](https://github.com/wtconsulting) in [#328](https://github.com/MasaCMS/MasaCMS/pull/328)

### New Contributors
{: .no_toc }

* [@titiscan](https://github.com/titiscan) made their first contribution in [#310](https://github.com/MasaCMS/MasaCMS/pull/338)

Full Changelog: [7.4.7...7.4.8](https://github.com/MasaCMS/MasaCMS/compare/7.4.7...7.4.8)

## 7.4.7

### What's Changed
{: .no_toc }

- Fix: site bundle files query invalid syntax by [@ryan-carmody](https://github.com/ryan-carmody) in [#310](https://github.com/MasaCMS/MasaCMS/pull/310)
- Fix the enableDynamicContent setting by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#303](https://github.com/MasaCMS/MasaCMS/pull/303)
- Typo fix in filemanager by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#309](https://github.com/MasaCMS/MasaCMS/pull/309)
- Create a complete admin path returnURL to redirect too. by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#318](https://github.com/MasaCMS/MasaCMS/pull/318)
- ApiUtility - component not found on upgrade. Needs to be uppercase A by [@ptutty](https://github.com/ptutty) in [#281](https://github.com/MasaCMS/MasaCMS/pull/281)
- Add '"swiss german (switzerland)"' to resourceBundleFactory by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#312](https://github.com/MasaCMS/MasaCMS/pull/312)
- Remove unneeded 'Browse Assets' button. by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#300](https://github.com/MasaCMS/MasaCMS/pull/300)
- Fix issue in imagedetails.cfm by [@bdavieswbs](https://github.com/bdavieswbs) in [#295](https://github.com/MasaCMS/MasaCMS/pull/295)
- File Browser Update by [@wtconsulting](https://github.com/wtconsulting) in [#311](https://github.com/MasaCMS/MasaCMS/pull/311)


### New Contributors
{: .no_toc }

* [@ryan-carmody](https://github.com/ryan-carmody) made their first contribution in [#310](https://github.com/MasaCMS/MasaCMS/pull/310)
* [@ptutty](https://github.com/ptutty) made their first contribution in [#281](<(https://github.com/MasaCMS/MasaCMS/pull/281)>)
* [@bdavieswbs](https://github.com/bdavieswbs) made their first contribution in [#295](https://github.com/MasaCMS/MasaCMS/pull/295)
* [@wtconsulting](https://github.com/wtconsulting) made their first contribution in [#311](https://github.com/MasaCMS/MasaCMS/pull/311)

Full Changelog: [7.4.6...7.4.7](https://github.com/MasaCMS/MasaCMS/compare/7.4.6...7.4.7)


## 7.4.6

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }
We've been informed about multiple high and critical vulnerabilities in Masa CMS.

#### What is fixed ?
{: .no_toc }
* The mentioned vulnerabilities have been fixed.
* Additional security improvements have been made.

#### What versions are affected?
{: .no_toc }
Masa CMS versions 7.2, 7.3 and 7.4 are affected.

#### What should you upgrade ?
{: .no_toc }

* If you’re on Masa CMS 7.4, you should update to version 7.4.6 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
* If you’re on Masa CMS 7.3, you should update to version 7.3.13 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.2, you should update to version 7.2.8 immediately. This can be done by applying a manual update.

### What's Changed
{: .no_toc }

* Sections can act as fieldsets by [@grantshepert](https://github.com/grantshepert)
* Disable enableMuraTag, enableDynamicContent and sharableRemoteSessions by default
* Additional security improvements have been made

Full Changelog: [7.4.5...7.4.6](https://github.com/MasaCMS/MasaCMS/compare/7.4.5...7.4.6)

## 7.3.13

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }
We've been informed about multiple high and critical vulnerabilities in Masa CMS.

#### What is fixed ?
{: .no_toc }
* The mentioned vulnerabilities have been fixed.

#### What versions are affected?
{: .no_toc }
Masa CMS versions 7.2, 7.3 and 7.4 are affected.

#### What should you upgrade ?
{: .no_toc }

* If you’re on Masa CMS 7.4, you should update to version 7.4.6 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
* If you’re on Masa CMS 7.3, you should update to version 7.3.13 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.2, you should update to version 7.2.8 immediately. This can be done by applying a manual update.

### What's Changed
{: .no_toc }

* Disable enableMuraTag, enableDynamicContent and sharableRemoteSessions by default
* Additional security improvements have been made

Full Changelog: [7.3.12...7.3.13](https://github.com/MasaCMS/MasaCMS/compare/7.3.12...7.3.13)

## 7.2.8

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }
We've been informed about multiple high and critical vulnerabilities in Masa CMS.

#### What is fixed ?
{: .no_toc }
* The mentioned vulnerabilities have been fixed.

#### What versions are affected?
{: .no_toc }
Masa CMS versions 7.2, 7.3 and 7.4 are affected.

#### What should you upgrade ?
{: .no_toc }

* If you’re on Masa CMS 7.4, you should update to version 7.4.6 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
* If you’re on Masa CMS 7.3, you should update to version 7.3.13 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.2, you should update to version 7.2.8 immediately. This can be done by applying a manual update.

### What's Changed
{: .no_toc }

* Disable enableMuraTag, enableDynamicContent and sharableRemoteSessions by default
* Additional security improvements have been made

Full Changelog: [7.2.7...7.2.8](https://github.com/MasaCMS/MasaCMS/compare/7.2.7...7.2.8)

## 7.4.5

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }
We've been informed about a critical vulnerability in Masa CMS.

#### What is fixed ?
{: .no_toc }
* The mentioned vulnerability has been fixed.
* Additional security improvements have been made.

#### What versions are affected?
{: .no_toc }
Masa CMS versions 7.2, 7.3 and 7.4 are affected.

#### What should you upgrade ?
{: .no_toc }

* If you’re on Masa CMS 7.4, you should update to version 7.4.5 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
* If you’re on Masa CMS 7.3, you should update to version 7.3.12 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.2, you should update to version 7.2.7 immediately. This can be done by applying a manual update.

### What's Changed
{: .no_toc }

* Also include content that is excluded from site search in the related… by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#241](https://github.com/MasaCMS/MasaCMS/pull/241)
* Add jQuery for a11y checker plugin in CKEditor. We cannot alway rely … by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#243](https://github.com/MasaCMS/MasaCMS/pull/243)
* Destroy CKEditor instances when closeing the modal. by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#250](https://github.com/MasaCMS/MasaCMS/pull/250)
* Bugfix/code improvements by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in  [#267](https://github.com/MasaCMS/MasaCMS/pull/267)
* Added an extra check if the javaLoader is actually available to load … by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#266](https://github.com/MasaCMS/MasaCMS/pull/266)
* Update all jQuery v3.7.0 files to jQuery v3.7.1 files. by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#265](https://github.com/MasaCMS/MasaCMS/pull/265)
*  Issue 235: object become unclickable by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#257](https://github.com/MasaCMS/MasaCMS/pull/257)
* Put a maxlength on 'displayIntervalEvery'. by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#253](https://github.com/MasaCMS/MasaCMS/pull/253)
* Added general improvments by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#264](https://github.com/MasaCMS/MasaCMS/pull/264)
* Issue 261: lucee6 fixes by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#262](https://github.com/MasaCMS/MasaCMS/pull/262)
* replaced sanitizeValue() call and updated sanitizedValue() by [@OriCat101](https://github.com/OriCat101) in [#259](https://github.com/MasaCMS/MasaCMS/pull/259)
* Bugfix/rendering assets by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#268](https://github.com/MasaCMS/MasaCMS/pull/268)

### New Contributors
{: .no_toc }
*   [@OriCat101](https://github.com/OriCat101) made their first contribution in [#259](https://github.com/MasaCMS/MasaCMS/pull/259)

Full Changelog: [7.4.4...7.4.5](https://github.com/MasaCMS/MasaCMS/compare/7.4.4...7.4.5)

## 7.3.12
### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }
We've been informed about a critical vulnerability in Masa CMS.

#### What is fixed ?
{: .no_toc }
* The mentioned vulnerability has been fixed.
* Additional security improvements have been made.

#### What versions are affected?
{: .no_toc }
Masa CMS versions 7.2, 7.3 and 7.4 are affected.

#### What should you upgrade ?
{: .no_toc }

* If you’re on Masa CMS 7.4, you should update to version 7.4.5 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
* If you’re on Masa CMS 7.3, you should update to version 7.3.12 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.2, you should update to version 7.2.7 immediately. This can be done by applying a manual update.

Full Changelog: [7.3.11...7.3.12](https://github.com/MasaCMS/MasaCMS/compare/7.3.11...7.3.12)

## 7.2.7
### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }
We've been informed about a critical vulnerability in Masa CMS.

#### What is fixed ?
{: .no_toc }
* The mentioned vulnerability has been fixed.
* Additional security improvements have been made.

#### What versions are affected?
{: .no_toc }
Masa CMS versions 7.2, 7.3 and 7.4 are affected.

#### What should you upgrade ?
{: .no_toc }

* If you’re on Masa CMS 7.4, you should update to version 7.4.5 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
* If you’re on Masa CMS 7.3, you should update to version 7.3.12 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.2, you should update to version 7.2.7 immediately. This can be done by applying a manual update.

Full Changelog: [7.2.6...7.2.7](https://github.com/MasaCMS/MasaCMS/compare/7.2.6...7.2.7)

## 7.4.4
### What's Changed
{: .no_toc }

* fix issue with validation of properties in inline edit by [@guustnieuwenhuis](https://github.com/guustnieuwenhuis) in [#204](https://github.com/MasaCMS/MasaCMS/pull/204)
* Add a PGP key for confidential vulnerability reprts. by [@jochemd](https://github.com/jochemd) in [#228](https://github.com/MasaCMS/MasaCMS/pull/228)
* #161 wordfilter setting portcullis by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#227](https://github.com/MasaCMS/MasaCMS/pull/227)
* Security improvements by [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) in [#235](https://github.com/MasaCMS/MasaCMS/pull/235)
* Update filebrowser.cfc by [@jimblesphere](https://github.com/jimblesphere) in [#226](https://github.com/MasaCMS/MasaCMS/pull/226)
* Fixed #230 Related Content Advanced Search by [@no3rdw](https://github.com/no3rdw) in [#231](https://github.com/MasaCMS/MasaCMS/pull/231)
* Allow for custom objectconfigurator position options by [@no3rdw](https://github.com/no3rdw) in [#233](https://github.com/MasaCMS/MasaCMS/pull/233)

### New Contributors
{: .no_toc }
* [@jeroenweareorangeeu](https://github.com/jeroenweareorangeeu) made their first contribution in [#227](https://github.com/MasaCMS/MasaCMS/pull/227)

Full Changelog: [7.4.3...7.4.4](https://github.com/MasaCMS/MasaCMS/compare/7.4.3...7.4.4)

## 7.4.3
### What's Changed
{: .no_toc }

* fix issue with validation of properties in inline edit by [@guustnieuwenhuis](https://github.com/guustnieuwenhuis) in [#204](https://github.com/MasaCMS/MasaCMS/pull/204)
* Update catnav.cfc to fix null pointer exception by [@no3rdw](https://github.com/no3rdw) in [#201](https://github.com/MasaCMS/MasaCMS/pull/201)
* fixed keepMetaKeywords conditional by [@no3rdw](https://github.com/no3rdw) in [#199](https://github.com/MasaCMS/MasaCMS/pull/199)
* #212 fix layout issue with managing categories when editing content node by [@guustnieuwenhuis](https://github.com/guustnieuwenhuis) in [#213](https://github.com/MasaCMS/MasaCMS/pull/213)
* #209 include inherited class extensions in condition to show or hide … by [@guustnieuwenhuis](https://github.com/guustnieuwenhuis) in [#211](https://github.com/MasaCMS/MasaCMS/pull/211)
* #208 fixing styling on notifyEditor by [@guustnieuwenhuis](https://github.com/guustnieuwenhuis) in [#210](https://github.com/MasaCMS/MasaCMS/pull/210)
* Added Category Name to Local Index Advanced Filter Field List by [@no3rdw](https://github.com/no3rdw) in [#215](https://github.com/MasaCMS/MasaCMS/pull/215)
* improve condition to check if razuna is enabled before throwing a dep… by [@guustnieuwenhuis](https://github.com/guustnieuwenhuis) in [#221](https://github.com/MasaCMS/MasaCMS/pull/221)
* improve entityname sanitization by [@guustnieuwenhuis](https://github.com/guustnieuwenhuis) in [#219](https://github.com/MasaCMS/MasaCMS/pull/219)
* Feature/216 azure ad support for sso by [@guustnieuwenhuis](https://github.com/guustnieuwenhuis) in [#217](https://github.com/MasaCMS/MasaCMS/pull/217)

### New Contributors
{: .no_toc }
* [@no3rdw](https://github.com/no3rdw) made their first contribution in [#201](https://github.com/MasaCMS/MasaCMS/pull/201)

Full Changelog: [7.4.2...7.4.3](https://github.com/MasaCMS/MasaCMS/compare/7.4.2...7.4.3)

## 7.4.2
### Security Vulnerability Fix
{: .no_toc }
#### What was the issue ?
{: .no_toc }

We've been informed of multiple vulnerabilities in Masa CMS.
#### What is fixed ?
{: .no_toc }

* The mentioned vulnerabilities have been fixed.
* Security fixes from the MuraLabs repository have been copied over to Masa CMS.
* Multiple dependancies have been updated to their latest releases.
* Unused dependancies have been removed.

#### What versions are affected?
{: .no_toc }

Masa CMS versions 7.2, 7.3 and 7.4 are affected.

#### What should you upgrade ?
{: .no_toc }

* If you’re on Masa CMS 7.4, you should update to version 7.4.2 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
* If you’re on Masa CMS 7.3, you should update to version 7.3.11 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.2, you should update to version 7.2.6 immediately. This can be done by applying a manual update.

Full Changelog: [7.4.1...7.4.2](https://github.com/MasaCMS/MasaCMS/compare/7.4.1...7.4.2)

## 7.3.11
### Security Vulnerability Fix
{: .no_toc }
#### What was the issue ?
{: .no_toc }

We've been informed of multiple vulnerabilities in Masa CMS.
#### What is fixed ?
{: .no_toc }

* The mentioned vulnerabilities have been fixed.
* Security fixes from the MuraLabs repository have been copied over to Masa CMS.
* Multiple dependancies have been updated to their latest releases.
* Unused dependancies have been removed.

#### What versions are affected?
{: .no_toc }

Masa CMS versions 7.2, 7.3 and 7.4 are affected.

#### What should you upgrade ?
{: .no_toc }

* If you’re on Masa CMS 7.4, you should update to version 7.4.2 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
* If you’re on Masa CMS 7.3, you should update to version 7.3.11 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.2, you should update to version 7.2.6 immediately. This can be done by applying a manual update.

Full Changelog: [7.3.10...7.3.11](https://github.com/MasaCMS/MasaCMS/compare/7.3.10...7.3.11)

## 7.2.6

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }

We've been informed of multiple vulnerabilities in Masa CMS.

#### What is fixed ?
{: .no_toc }

* The mentioned vulnerabilities have been fixed.
* Security fixes from the MuraLabs repository have been copied over to Masa CMS.

#### What versions are affected?
{: .no_toc }

Masa CMS versions 7.2, 7.3 and 7.4 are affected.

#### What should you upgrade ?
{: .no_toc }

* If you’re on Masa CMS 7.4, you should update to version 7.4.2 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.
* If you’re on Masa CMS 7.3, you should update to version 7.3.11 immediately. This can be done by applying a manual update.
* If you’re on Masa CMS 7.2, you should update to version 7.2.6 immediately. This can be done by applying a manual update.

Full Changelog: [7.2.5...7.2.6](https://github.com/MasaCMS/MasaCMS/compare/7.2.5...7.2.6)

## 7.4.1
### What's Changed
{: .no_toc }

* fix issue with ids in db update script by [@guustnieuwenhuis](https://github.com/guustnieuwenhuis) in [#157](https://github.com/MasaCMS/MasaCMS/issues/157)
* Replace hard-coded references to /admin directory by [@jimblesphere](https://github.com/jimblesphere) in [#177](https://github.com/MasaCMS/MasaCMS/issues/177)
* Update filebrowser.cfc by [@chexy](https://github.com/chexy) in [#175](https://github.com/MasaCMS/MasaCMS/issues/175)
* error when related content is scheduled, missing column parentType by [@sejourla](https://github.com/sejourla) in [#174](https://github.com/MasaCMS/MasaCMS/issues/174)
* Update database driver created by setup for MySQL/Lucee by [@quetwo](https://github.com/quetwo) in [#141](https://github.com/MasaCMS/MasaCMS/issues/141)
* fixed broken styling on categories tab
* fixed broken styling on component editing (front-end)
* fixed StructKeyDelete function by [@ejespersen-AMS](https://github.com/ejespersen-AMS)
* fixed class extensions in components

Full Changelog: [7.4.0...7.4.1](https://github.com/MasaCMS/MasaCMS/compare/7.4.0...7.4.1)

## 7.4.0
### What's Changed
{: .no_toc }
* updated default theme to the latest version
* updated mura.js to the latest version
* new setting showextensionsindefault to show the basic tab extended attributes below the editor
* new search module
* new primarynav module
* new gotofirstchild module
* new nextprevnav module
* new gattedasset module
* new button module
* new info module
* new media module
* reviewed navigation module
* reviewed form module
* reviewed image module
* reviewed CTA module

## 7.4.0-beta.3

## 7.3.10

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }

We've been informed of an authentication bypass vulnerability in Masa CMS.

#### What is fixed ?
{: .no_toc }

The mentioned vulnerability has been fixed.

#### What versions are affected?
{: .no_toc }

Masa CMS versions 7.2, 7.3 and 7.4-beta are affected.

#### What should you upgrade ?
{: .no_toc }

If you’re on Masa CMS 7.3, you should update to version 7.3.10 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.

## 7.2.5

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }

We've been informed of an authentication bypass vulnerability in Masa CMS.

#### What is fixed ?
{: .no_toc }

The mentioned vulnerability has been fixed.

#### What versions are affected?
{: .no_toc }

Masa CMS versions 7.2, 7.3 and 7.4-beta are affected.

#### What should you upgrade ?
{: .no_toc }

If you’re on Masa CMS 7.2, you should update to version 7.2.5 immediately. This can be done by applying a manual update.

## 7.3.9

### What's Changed
{: .no_toc }

* Update filebrowser.cfc by @jimblesphere in #128
* fix empty admin minified JS files
* replace We Are Orange with We Are North (https://www.wearenorth.eu/updates/we-are-north-now-not-orange-heres-why/)

Full Changelog: [7.3.8...7.3.9](https://github.com/MasaCMS/MasaCMS/compare/7.3.8...7.3.9)


## 7.4.0-beta.2

fixed an issue with empty generated javascript files


## 7.4.0-beta.1

This is a pre-release version of 7.4 including the follow updates:

* update for the default theme
* new setting showextensionsindefault to show the basic tab extended attributes below the editor
* new search module
* new primarynav module
* new gotofirstchild module
* new nextprevnav module


## 7.3.8

Bug fixes for:

* [#99](https://github.com/MasaCMS/MasaCMS/issues/99)
* [#116](https://github.com/MasaCMS/MasaCMS/issues/116)
* [#117](https://github.com/MasaCMS/MasaCMS/issues/117)

and CKEditor update to version 4.19.1


## 7.4.0-alpha.2

This is a pre-release version of 7.4 including the follow updates:

* new Gatted Asset module
* reviewed Navigation module


## 7.3.7

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }

We've been informed of a path traversal vulnerability in Masa CMS [CVE-2021-42183](https://nvd.nist.gov/vuln/detail/CVE-2021-42183).

#### What is fixed ?
{: .no_toc }

The mentioned vulnerability has been fixed.

#### What versions are affected?
{: .no_toc }

Masa CMS versions 7.2 and 7.3 are affected.

#### What should you upgrade ?
{: .no_toc }

If you’re on Masa CMS 7.2, you should update to version 7.2.4 immediately. This can be done by applying a manual update.


## 7.2.4

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }

We've been informed of a path traversal vulnerability in Masa CMS [CVE-2021-42183](https://nvd.nist.gov/vuln/detail/CVE-2021-42183).

#### What is fixed ?
{: .no_toc }

The mentioned vulnerability has been fixed.

#### What versions are affected?
{: .no_toc }

Masa CMS versions 7.2 and 7.3 are affected.

#### What should you upgrade ?
{: .no_toc }

If you’re on Masa CMS 7.2, you should update to version 7.2.4 immediately. This can be done by applying a manual update.


## 7.3.6

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }

We've been informed of a XSS security vulnerability in the Masa CMS administrator.

#### What is fixed ?
{: .no_toc }

Additional protection against XSS attacks is implemented to further secure the Masa CMS administrator.

#### What versions are affected?
{: .no_toc }

Masa CMS versions 7.2 and 7.3 are affected.

#### What should you upgrade ?
{: .no_toc }

If you’re on Masa CMS 7.2, you should update to version 7.2.3 immediately. This can be done by applying a manual update.


## 7.2.3

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }

We've been informed of a XSS security vulnerability in the Masa CMS administrator.

#### What is fixed ?
{: .no_toc }

Additional protection against XSS attacks is implemented to further secure the Masa CMS administrator.

#### What versions are affected?
{: .no_toc }

Masa CMS versions 7.2 and 7.3 are affected.

#### What should you upgrade ?
{: .no_toc }

If you’re on Masa CMS 7.2, you should update to version 7.2.3 immediately. This can be done by applying a manual update.


## 7.4.0-alpha.1

This is a pre-release version of 7.4 including the follow updates:

* updated mura.js to the latest version
* new Button module
* new Info module
* new Media module
* reviewed Form module
* reviewed Image module
* reviewed CTA module


## 7.3.5

### Bug fixes
{: .no_toc }

* bug fixes for
  * [issue 74](https://github.com/MasaCMS/MasaCMS/issues/74)
  * fixes for integration with s3 in File Browser


## 7.3.4

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }

We've been informed of a XSS security vulnerability in the Masa CMS administrator.

#### What is fixed ?
{: .no_toc }

Additional protection against XSS attacks is implemented to further secure the Masa CMS administrator.

#### What versions are affected?
{: .no_toc }

Masa CMS versions 7.2 and 7.3 are affected.

#### What should you upgrade ?
{: .no_toc }

If you’re on Masa CMS 7.3, you should update to version 7.3.4 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.


## 7.3.3

### Bug fixes
{: .no_toc }

* bug fixes for
  * [issue 75](https://github.com/MasaCMS/MasaCMS/issues/75)
  * JS error when publishing a page with an undefined canonicalurl
  * JS error when starting inline editing

## 7.3.2

### Bug fixes
{: .no_toc }

* bug fixes for
  * [issue 65](https://github.com/MasaCMS/MasaCMS/issues/65)
  * [issue 66](https://github.com/MasaCMS/MasaCMS/issues/66)
  * [issue 70](https://github.com/MasaCMS/MasaCMS/issues/70)

## 7.3.1

### Bug fixes
{: .no_toc }

* Improved extended attributes UI in the content manager
* Adobe ColdFusion compatibility fixes
* Improve customUI tab labels [issue 56](https://github.com/MasaCMS/MasaCMS/issues/56)
* bug fixes for
  * [issue 41](https://github.com/MasaCMS/MasaCMS/issues/41)
  * [issue 43](https://github.com/MasaCMS/MasaCMS/issues/43)
  * [issue 44](https://github.com/MasaCMS/MasaCMS/issues/44)
  * [issue 45](https://github.com/MasaCMS/MasaCMS/issues/45)
  * [issue 51](https://github.com/MasaCMS/MasaCMS/issues/51)


## 7.3

### New features
{: .no_toc }

* New interface for editing content and components in the [Masa CMS Administrator](/content/adding-content/via-administrator/)
* New [File Browser](/content/managing-content/filebrowser/)
* File Browser enabled by default
* Introducing a [deprecation warnings module](/deprecations/deprecation_warnings/)
* Introducing the [Masa Scope](/front-end-layout-manager/m-tag/masa-scope/)
* ORM Assembler is now in BETA
* Changed the default theme to [MasaBootstrap5](https://github.com/MasaCMS/MasaBootstrap5)

### Bug fixes
{: .no_toc }

* Old, unused code from Advertisement Manager removed from codebase
* Fixed a tenacious JavaScript console error
* ORM Scaffolder option list and option values list were incorrectly displayed

### Deprecations
{: .no_toc }

* Deprecated Mura Scope and tag
* Deprecated Razuna integration
* Deprecated Simple Forms
* [Documented deprecations](/deprecations/list-of_deprecations/)
* [Documented deprecations inherited from Mura 7.1](/deprecations/mura-deprecations/)

## 7.2.2

### Security Vulnerability Fix
{: .no_toc }

#### What was the issue ?
{: .no_toc }

We've been informed of a XSS security vulnerability in the Masa CMS administrator.

#### What is fixed ?
{: .no_toc }

Additional protection against XSS attacks is implemented to further secure the Masa CMS administrator.

#### What versions are affected?
{: .no_toc }

Masa CMS versions 7.2 and 7.3 are affected.

#### What should you upgrade ?
{: .no_toc }

If you’re on Masa CMS 7.3, you should update to version 7.3.4 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.


## 7.2.1

### Security Vulnerability Fix
{: .no_toc }


#### What was the issue ?
{: .no_toc }

We’ve been informed of a security vulnerability that allows any user to request files outside the asset folder from the server.

#### What is fixed ?
{: .no_toc }

We’ve improved the security around the assets API endpoint that is affected, to validate that the user can only request assets from the assets folder. In the process we’ve also applied restrictions to the asset upload endpoint, so that only logged in editors can upload assets.

#### What versions are affected?
{: .no_toc }

Only Masa CMS version 7.2 is affected

#### What should you upgrade ?
{: .no_toc }

If you’re on Masa CMS 7.2, you should update to version 7.2.1 immediately. This can be done by using the “Update Masa CMS Core” option in the menu of the Masa CMS Administrator or by applying a manual update.


## 7.2

### Mura CMS becomes Masa CMS
{: .no_toc }

* Renamed Mura CMS to Masa CMS
* Replaced Mura CMS logo's with Masa CMS logo's
* Removed Mura CMS contributor agreement
* Removed obsolete Docker config
* Removed CKFinder license
* Bugfixes

### New features
{: .no_toc }

* Setting for enabling/disabling File Manager, disabled by default
* New image upload in CKEditor, without using CKFinder
