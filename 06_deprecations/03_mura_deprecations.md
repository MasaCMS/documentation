---
layout: default
title: Mura Deprecations
nav_order: 3
parent: Deprecations
last_modified_date: 20-12-2021 13:00
permalink: /deprecations/mura-deprecations/
---

# Mura Deprecation

Following is a list of files and functions that already have been deprecated in Mura and are inhered by Masa CMS.
Please check which applied to your situation and update you code accordingly.
No warnings are logged for these deprecations.

## CFML

###  cfobject.cfc - ``injectMethod``
In  ``core/mura/cfobject.cfc`` the function ``injectMethod`` is deprecated. Please update to ``inject``.

### ``getThemeRenderer()``
This function is deprecated in the following files:
* core/mura/event.cfc
* core/mura/MasaScope.cfc (Masa CMS 7.3)
* core/mura/MuraScope.cfc (pre Masa CMS 7.3)
* core/mura/servletEvent.cfc
* core/mura/settings/settingsBean.cfc

Use the function ``getContentRenderer()`` instead.


### ``getSiteRenderer()``
This function is deprecated in the following files:

* core/mura/MasaScope.cfc (Masa CMS 7.3)
* core/mura/MuraScope.cfc (pre Masa CMS 7.3)

Use the function ``getContentRenderer()`` instead.

###  utility.cfc - ``getUUID``
In  ``core/mura/utility.cfc`` the function ``getUUID`` is deprecated. Please update to ``createUUID()`` which is a standard CFML/Lucee function.

###  contentRenderer.cfc - ``renderHTMLHeadQueue``
In  ``core/mura/content/contentRenderer.cfc`` the function ``renderHTMLHeadQueue`` is deprecated. 
Use the function ``renderHTMLQueue("Head")`` instead.


### json.cfc
The file `core/mura/json.cfc``is deprecated. Please use the JSON functions available in CFML/Lucee.

* [Adobe Coldfusion JSON Referece](https://helpx.adobe.com/coldfusion/cfml-reference/ajax-javascript-functions/coldfusion-autosuggest-getautosuggestobject/coldfusion-json-encode.html)
* [Lucee JSON documentation](https://docs.lucee.org/categories/json.html)


### mailerLimited.cfc
The file ``core/mura/mailerLimited.cfc``is deprecated. Please use other ways to send your e-mail. 

### cacheFactory.cfc
The file ``core/mura/cacheFactory.cfc``is deprecated. Please use other ways cache your variables.


## All files in ``/core/mura/client/api/soap/v1/``
All  the 7 files in this folder are deprecated. These are:

* bundle.cfc
* category.cfc
* content.cfc
* feed.cfc
* muraProxy.cfc
* service.cfc
* user.cfc

Please do not use them anymore.

### contentCommenterBean.cfc
The file ``core/mura/contentCommenterBean.cfc``is deprecated. Please do not us this ORM bean anymore.

### Depracted arguments in functions in contentManager.cfc

In the file ``core/mura/content/contentManager.cfc`` the argument `contentRenderer` is deprecated. This applies to the following functions:

* saveComment
* approveComment

Please remove this arguments in your calls to these functions in this .cfc.

### Depracted arguments in functions in contentRenderer.cfc and contentRenderUtility.cfc
In the file ``core/mura/content/contentRenderer.cfc`` and ``core/mura/content/contentRenderUtility.cfc  `` the following arguments are deprecated for the functions ``createHREF`` and ``createHREFforRSS``: 

* context
* stub
* indexFile

Please remove this arguments in your calls to these functions in this .cfc.

### Deprecated functions in contentRenderer.cfc
In the file ``core/mura/content/contentRenderer.cfc`` the following functions are depracated:

* dspUserTools
* dspCaptcha
* sendToFriendLink
		
Please do not use these function anymore.

### Property ``extranetSSL`` in settingBean.cfc
The property ``extranetSSL`` in ``core/mura/settings/settingsBean.cfc`` is deprecatd. Please do not use this setting anymore.

### Function ``setAddresses`` in userBean.cfc
The function ``setAddresses`` in ``core/mura/user/userBean.cfc`` is deprecated. Please do not use this function anymore; instead use ``userBean.set("addresses", addressesData)``.




# JS
