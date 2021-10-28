---
layout: default
title: Upgrade from Mura to Masa CMS
nav_order: 4
parent: Getting started
last_modified_date: 20-10-2021 13:00
permalink: /getting-started/upgrade-from-mura-to-masa-cms/
---

# Upgrade from Mura to Masa CMS

Masa CMS is backward compatible with Mura CMS. Migrating is as easy as executing an upgrade.

## Steps to execute

To migrate from Mura CMS to Masa CMS, execute the following steps:

* locate the `config/settings.ini.cfm` file in your project
* search for the `autoupdateurl` setting in this file
* update its value to `https://github.com/MasaCMS/MasaCMS/archive/main.zip`
* login to the Mura administrator
* reload application
* execute an "update core"
* Welcome to Masa CMS!
