---
layout: default
title: File Browser
nav_order: 9
grand_parent: Content
parent: Managing content
last_modified_date: 12-01-2022 09:00
permalink: /content/managing-content/filebrowser/
---

# File Browser
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

- TOC
{:toc}


## Enabeling File Browser

By default the File Browser is disabled in Masa CMS.  Goto your `settings.ini.cfm` file and and set the value `filemanagerenabled` to `true`. It should look like this:
```markdown
filemanagerenabled=true
```
Reload Masa CMS. The File Browser is now available.

## File Browser Oveview
With the File Browser enabled in the left menu the 'File Browser' menu item is now available.

![](/assets/02_content/03_managing_content/09_filebrowser/01_filebrowser_menu.png)

An overview of the File Brower is shown:

![](/assets/02_content/03_managing_content/09_filebrowser/02_filebrowser_overview.png)

There are several options:
* The buttons 'User Assets', 'Sites Files', 'Application Root' are the three file locations that are important for Masa CMS. Clicking on a buttons takes you to these locations.
* Files can be displayd in List View (the default) or Grid View.
* You can filter files and directories in the input 'Type to filter'.

## Uploading a file