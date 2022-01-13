---
layout: default
title: Deprecation Warnings
nav_order: 2
parent: Deprecations
last_modified_date: 13-12-2021 13:00
permalink: /deprecations/deprecation_warnings/
---

# Deprecation Warnings
For the functionalities that are deprecated, a warning is written into a seperate log file.
This way you can collect en review the deprecations that apply to your Masa CMS installation.
Deprecation warnings are enabled by default and written into `deprecations.log` file.

This file contains the deprecation warning, a short explanation and a short stack trace of 10 lines.
Stack trace lines of the `pluginManager.cfc` and the deprecation module `handler.cfc` are omitted from this log.

A deprecation log file looks something like this:

![](/assets/06_deprecations/deprecation_warnings/deprecation_log_1.png)

Use this log file to remove deprecated functionality from you code.

## Configuration
There are two settings that control deprecation warnings in Masa CMS:

```markdown
deprecationwarningsenabled=true
deprecationlogfile=deprecations
```

By default `deprecationwarningsenabled` is `true`, enabling logging the deprecation warnings.

We advise to disable deprecation warnings for production environments.
{: .alert .alert-warning }

The warnings are written into a log with the name `deprecations.log`. You can find this log in you Lucee / CFML log directory.

You can overwrite these settings in `settings.ini.cfm`.