---
layout: default
title: Events
nav_order: 6
parent: Customizing/Extending Masa
has_children: true
last_modified_date: 20-10-2021 13:00
permalink: /customizing-extending-masa/events/
---

# Events

Masa CMS is extremely customisable and one of the ways to achieve that is through events. In this section of the documentation the [event hooks](/customizing-extending-masa/events/event-hooks/) are explained and listed, you'll learn about the [event lifecycles](/customizing-extending-masa/events/lifecycles/) and we explain how to write [event handlers](/customizing-extending-masa/events/event-handlers/).

## Lifecycle events

A lifecycle event is an event that gets triggered on every single request, wether it is a front-end request or a request to the Masa CMS administrator.

An example of a lifecycle event is `onSiteRequestStart` that is triggered early on every front-end request or the `onPageBodyRender` event that is triggered when the body of a Page is rendered.

## Contextual events

Events that aren't triggered on every request, but only when a specific action is executed, are contectual events. 

The `onSiteLogin` event is an example of a contextual event, it is only triggered when a user logs into the website.