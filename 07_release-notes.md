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

## 7.3

### New features
{: .no_toc }

* New interface for editing content and components in the Masa CMS Administrator
* New file manager
* Introducing a deprecation warnings module
* Introducing the Masa Scope
* ORM Assembler is not in BETA
* Changed the default theme to [MasaBoostrap5](https://github.com/MasaCMS/MasaBootstrap5)


### Bug fixes
{: .no_toc }

* Old, unused code from Advertisement Manager removed from codebase
* Fixed a tenacious JavaScript console error


### Deprecations
{: .no_toc }

* Deprecated Mura Scope and tag
* Deprecation warning when setting Razuna
* Deprecation warning for Simple Forms
* Created a list of deprecated features inherited from Mura 7.2


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
