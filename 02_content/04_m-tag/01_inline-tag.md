---
layout: default
title: Inline tag
nav_order: 1
grand_parent: Content
parent: M-tag
last_modified_date: 04-11-2021 14:00
permalink: /content/m-tag/inline-tag/
---

# Inline tag

When creating content in Masa CMS you use the `[mura]` tag for rendering dynamic content.
This is very powerfull way to acces CFML and Masa functionality.

## Examples
You can use CFML functions inside your `[mura]` tag:

```cfscript
[mura]TimeFormat(Now(), 'hh:mm:ss tt')[/mura]
```
    
You can also call Masa specific functions that are available through the Mura scope:
    
```cfscript
[mura]m.dspInclude('custom_file_path/inc/includeFile.cfm')[/mura]
```

Or

```cfscript
[mura]m.siteConfig('assetPath')[/mura]
```

Thus you can also call your own functions you've created in your `contentRenderer.cfc` in your Theme:

```cfscript
[mura]
m.dspCarouselByFeedName(
        feedName='Slideshow'
        , showCaption=true
        , cssID='myCarousel'
        , size='carouselimage'
        , interval=5000
        , autoStart=true
    )
[/mura]
```

This example is using the MuraBootstrap5 Theme.

Also the function available through Masa Plugins are available:

```cfscript
[mura]m.muraLocations.dspFindLocationsForm()[/mura]
```

This example is using the MuraLocations Plugin.
## Permissions

Any user that can edit content, can use the `[mura]` tag.