---
layout: default
title: Folder structure
nav_order: 1
grand_parent: Front-End/Layout Manager
parent: Add a theme
last_modified_date: 18-09-2023 09:00
permalink: /front-end-layout-manager/add-a-theme/folder-structure/
---

# Folder structure

## Theme Locations
Themes can be placed in two locations:

* /{masa-install}/themes/  - This is the global location for themes. All sites from your Masa CMS installation can use these themes.

* /{masa-install}/sites/{siteid}/themes - This is the site specific location for themes. Only the site under this file location can use this theme.

## Theme structure

| Directory or file | Description |
| ----------- | ----------- |
| {theme}/assets/ | In this directory you can put all the assets, like libraries and frameworks.  |
| {theme}/content_types/ | The configuration for theme specific Content Types are put here.  |
| {theme}/css/ | If an 'editor.css' file is present in this directory, than the styles will be included in the CKEditor.  |
| {theme}/modules/ | [Modules](/front-end-layout-manager/add-a-theme/modules/) are configured here.  |
| {theme}/images/ | Theme specific images (like logo's etc) are stored here.  |
| {theme}/js/ | In this directory you can put all the theme-specific Javascript  |
| {theme}/resource_bundles/ | Resource bundles are stored here.  |
| {theme}/templates/ | [Templates](/front-end-layout-manager/add-a-theme/templates/) are configured here.  |
| {theme}/config.xml.cfm | In this file you can configure theme-specific settings.  |
| {theme}/contentRenderer.cfc | The default 'contentRenderer.cfc' and it's functions can be overwritten here.  |
| {theme}/eventHandler.cfc | In the 'eventHandler.cfc' you can plug into the Event Cycle of Masa CMS / CFML.  |