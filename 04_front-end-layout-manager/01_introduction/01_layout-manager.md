---
layout: default
title: Layout manager
nav_order: 1
grand_parent: Front-End/Layout Manager
parent: Introduction
last_modified_date: 20-10-2021 13:00
permalink: /front-end-layout-manager/introduction/layout-manager/
---

# Layout Manager

The Layout Manager is the front-end tool for composing the layout of pages, entering content, and adding/configuring automated tools like navigation, forms, feeds and collections.

## Concept

Instead of relying upon hard-coded, code-based layout templates, the Layout Manager allows you to drag-and-drop highly configurable "Modules" onto a page. Each Module (depending upon it's type and location) will have an associated "configurator" that allows further customization, such as functional settings (feed source, form name, etc.) and layout (alignment/width, associated CSS classes/styles, etc.). In this way, the editor is allowed a great deal of flexibility when laying out each page, seeing the results immeditately and without having to edit or create hard-coded templates.

## How-to

To enable the Layout Manager, log into Masa CMS with an account that has editing permissions enabled, then from the top editor toolbar choose "Edit (pencil icon) -> Inline Edit". A list of Modules will appear on the right-hand side of the page. Use your mouse to drag this into the content area. You will see a context label appear above an available "drop" container when you drag the Module over it. Releasing the mouse button (aka "dropping" it) will place the Module into the container.

## Basics of Layout

When the Layout Manager is active, a "pencil" icon will appear whenever the mouse hovers over a Module in the content area. This is both the "edit" button, and the "drag" handle for moving the Module up/down within the current container or to drag it into another container.

There are two types of Modules: "Containers", which act as placeholders for other Modules (in some cases, even other Containers), and functional Modules, such as Navigation or Collection. *Note*: regarding Containers; it is better to use CSS/styling to layout complex content than use multiple nested containers, as there is a small but increasing performance penalty the more deeply you nest Containers.

## Configurators

For each Module, there is an associated "Configurator", a menu of settings that allow you to configure both the Module and its layout/styling properties. To access a Module's Configurator (once it is placed in the content area) click on the top-left pencil icon that displays when you hover over it.
