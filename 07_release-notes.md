---
layout: default
title: Release notes
nav_order: 7
last_modified_date: 11-01-2022 11:30
permalink: /release-notes/
---

# Release notes
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

- TOC
{:toc}

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
