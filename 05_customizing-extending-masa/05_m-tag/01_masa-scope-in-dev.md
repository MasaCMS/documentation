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

When developing Masa Themes or Plugins the `m`  scope is available. This is referred to as the 'Masa Scope'.
This scope exists next to the familiair `$` scope ('dollar scope').

## Examples

You can use the `m` scope in your template like so:

    m.siteConfig('assetPath')

Or

     m.dspCarouselByFeedName(
			feedName='Slideshow'
			, showCaption=true
			, cssID='myCarousel'
			, size='carouselimage'
			, interval=5000
			, autoStart=true
		)

This example is using the MuraBootstrap5 Theme; The function `dspCarouselByFeedName` in the `contentRenderer.cfc` is called via the `m` scope. 

Also the function available through Masa Plugins are available:

    m.muraLocations.dspFindLocationsForm()

This example is using the MuraLocations Plugin. The function `dspFindLocationsForm` in the `Eventhandler.cfc` is called via the `m` scope.