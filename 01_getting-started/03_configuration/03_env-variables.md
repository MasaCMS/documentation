---
layout: default
title: Environment variables
nav_order: 3
grand_parent: Getting started
parent: Configuration
last_modified_date: 18-10-2023 13:00
permalink: /getting-started/configuration/env-variables/
---

# Environment variables

Masa CMS can be configured using environment variables. When hosting Masa CMS in a Docker container on a public cloud provider, this comes in very useful.

## Available variables

All Masa CMS settings are available as environment variables using the following format: `MURA_{setting}`, for example `MURA_APPRELOADKEY`.

[List of available settings](/getting-started/configuration/configuration-file/)

Additionally, there are some more environment variables that allow you to configure your Masa CMS environment:

* MURA_ADMIN_USERNAME
* MURA_ADMIN_PASSWORD
