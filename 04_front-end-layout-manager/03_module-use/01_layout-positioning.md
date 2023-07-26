---
layout: default
title: Layout/positioning
nav_order: 1
grand_parent: Front-End/Layout Manager
parent: Module use
last_modified_date: 20-10-2021 13:00
permalink: /front-end-layout-manager/module-use/layout-positioning/
---

# Layout/positioning


When the Layout Manager is active, a "pencil" icon will appear whenever the mouse hovers over Modules placed in the content area. This is both the "edit" button, and the "drag" handle for moving the Module.

## Position
A page will contain at least one "drop" area, a container into which Modules can be dragged from the right-side "Layout Manager" list. When a dragged module is above a valid drop area, the section will highlight in red with the drop area's name appearing top-left. Once dropped, it is possible to reposition the module by dragging it via the "pencil" icon, so that it can be placed above/below other Modules in the same contained area or into another contained area.

## Containers
There are two types of Modules: Containers, which act as self-contained areas for other Modules (in some cases, even other Containers); and functional Modules, such as Navigation or Collection.

While additional functionality is planned for Containers, for now are intended to give added layout flexibility when simple styling will not do. Because Containers can be styled just as any other Module, they are ideal for laying out panels on a given web page, for instance when a set of informational "Cards" is needed, or for one-off styles.

As noted throughout this documentation, even though Containers can be nested infinitely, it is far better to use them sparingly, as they will demand a higher performance/rendering cost than simple stying would.