---
layout: default
title: Masa scope in dev
nav_order: 1
grand_parent: Customizing/Extending Masa
parent: M-tag
last_modified_date: 20-10-2021 13:00
permalink: /customizing-extending-masa/m-tag/masa-scope-in-dev/
---

# Masa scope in dev

When developing Masa Themes or Plugins the `masa`  scope is available.
This is scope exists next to the familiair `$` and `m` scope.

## Examples

You can use the `masa` in your template like so:

    masa.siteConfig('assetPath')

Or

     masa.dspCarouselByFeedName(
			feedName='Slideshow'
			, showCaption=true
			, cssID='myCarousel'
			, size='carouselimage'
			, interval=5000
			, autoStart=true
		)

This example is using the MuraBootstrap5 Theme; The function `dspCarouselByFeedName` in the `contentRenderer.cfc` is called via the `masa` scope. 

Also the function available through Masa Plugins are available:

    masa.muraLocations.dspFindLocationsForm()

This example is using the MuraLocations Plugin. The function `dspFindLocationsForm` in the `Eventhandler.cfc` is called via the `masa` scope.


