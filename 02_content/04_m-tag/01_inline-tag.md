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

When creating content in Masa CMS you use the `[m]` tag for rendering dynamic content.
This is very powerfull way to acces CFML and Masa functionality.

## Examples
You can use CFML functions inside your `[m]` tag:

```cfscript
[m]TimeFormat(Now(), 'hh:mm:ss tt')[/m]
```
    
You can also call Masa CMS specific functions that are available through the Mura scope:
    
```cfscript
[m]m.dspInclude('custom_file_path/inc/includeFile.cfm')[/m]
```

Or

```cfscript
[m]m.siteConfig('assetPath')[/m]
```

Thus you can also call your own functions you've created in your `contentRenderer.cfc` in your Theme:

```cfscript
[m]
m.dspCarouselByFeedName(
        feedName='Slideshow'
        , showCaption=true
        , cssID='myCarousel'
        , size='carouselimage'
        , interval=5000
        , autoStart=true
    )
[/m]
```

This example is using the [MasaBootstrap5](https://github.com/MasaCMS/MasaBootstrap5) Theme.

Also the function available through Masa CMS Plugins are available:

```cfscript
[m]m.muraLocations.dspFindLocationsForm()[/m]
```

This example is using the MuraLocations Plugin.
## Permissions

Any user that can edit content, can use the `[m]` tag.