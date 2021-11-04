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

When creating content in Masa CMS you use the `[masa]` tag for rendering dynamic content.
This is very powerfull way to acces CFML and Masa functionality.

## Examples
You can use CFML functions inside your `[masa]` tag:

    [masa]TimeFormat(Now(), 'hh:mm:ss tt')[/masa]
    
You can also call Masa specific functions that are available through the Masa scope:
    
    [masa]masa.dspInclude('custom_file_path/inc/includeFile.cfm')[/masa]

Or

    [masa]masa.siteConfig('assetPath')[/masa]

Thus you can also call your own functions you've created in your `contentRenderer.cfc` in your Theme:

    [masa]
    masa.dspCarouselByFeedName(
			feedName='Slideshow'
			, showCaption=true
			, cssID='myCarousel'
			, size='carouselimage'
			, interval=5000
			, autoStart=true
		)
    [/masa]

This example is using the MuraBootstrap5 Theme.

Also the function available through Masa Plugins are available:

    [masa]masa.muraLocations.dspFindLocationsForm()[/masa

This example is using the MuraLocations Plugin.
## Permissions

Any user that can edit content, can use the `[masa]` tag.