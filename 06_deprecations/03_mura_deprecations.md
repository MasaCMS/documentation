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
No warnings are logged for these existing deprecations.

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
The file ``core/mura/json.cfc``is deprecated. Please use the JSON functions available in CFML/Lucee.

* [Adobe Coldfusion JSON Referece](https://helpx.adobe.com/coldfusion/cfml-reference/ajax-javascript-functions/coldfusion-autosuggest-getautosuggestobject/coldfusion-json-encode.html)
* [Lucee JSON documentation](https://docs.lucee.org/categories/json.html)


### mailerLimited.cfc
The file ``core/mura/mailerLimited.cfc``is deprecated. Please use other ways to send your e-mail. 

### cacheFactory.cfc
The file ``core/mura/cacheFactory.cfc``is deprecated. Please use other ways to cache your variables.


## All files in ``/core/mura/client/api/soap/v1/``
All the 7 files in this folder are deprecated. These are:

* bundle.cfc
* category.cfc
* content.cfc
* feed.cfc
* muraProxy.cfc
* service.cfc
* user.cfc

Please do not use them anymore.

### contentCommenterBean.cfc
The file ``core/mura/contentCommenterBean.cfc``is deprecated. Please do not use this ORM bean anymore.

### Deprecated arguments in functions in contentManager.cfc

In the file ``core/mura/content/contentManager.cfc`` the argument `contentRenderer` is deprecated. This applies to the following functions:

* saveComment
* approveComment

Please remove these arguments in your calls to these functions.

### Deprecated arguments in functions in contentRenderer.cfc and contentRenderUtility.cfc
In the files ``core/mura/content/contentRenderer.cfc`` and ``core/mura/content/contentRenderUtility.cfc  `` the following arguments are deprecated for the functions ``createHREF`` and ``createHREFforRSS``: 

* context
* stub
* indexFile

Please remove these arguments in your calls to these functions.

### Deprecated functions in contentRenderer.cfc
In the file ``core/mura/content/contentRenderer.cfc`` the following functions are deprecated:

* dspUserTools
* dspCaptcha
* sendToFriendLink
		
Please do not use these functions anymore.

### Property ``extranetSSL`` in settingBean.cfc
The property ``extranetSSL`` in ``core/mura/settings/settingsBean.cfc`` is deprecated. Please do not use this setting anymore.

### Function ``setAddresses`` in userBean.cfc
The function ``setAddresses`` in ``core/mura/user/userBean.cfc`` is deprecated. Please do not use this function anymore; instead use ``userBean.set("addresses", addressesData)``.

## Functions in configBean.cfc
In the file ``core/mura/configBean.cfc`` the following functions are deprecated:

* dbCreateIndex  (upgrade to dbUtility.cfc --> addIndex())
* dbTableColumns  (upgrade to dbUtility.cfc --> columns())
* dbDropIndex  (upgrade to dbUtility.cfc --> dropIndex())
* dbDropColumn (upgrade to dbUtility.cfc --> dropColumn())    

Please use the functions in ``core/mura/dbUtility.cfc`` instead.

### s3.cfc
The file ``core/mura/content/file/s3.cfc` is` deprecated.
Pleas use different solution for interacting with S3.

### Deprecated arguments in function ``getAdvancedSearch`` in userGateway.cfc and userManager.cfc
In the files ``core/mura/user/userGateway.cfc`` and ``core/mura/userGateway.cfc  `` the following arguments are deprecated for the function ``getAdvancedSearch``:

* siteid
* ispublic

Please remove these arguments in your calls to these functions.

# JS
## Function ``addLoadEvent`` in mura.js
The function addLoadEvent is deprecated in ``admin/assets/js/mura.js``. Please use ``renderClient`` and ``renderServer`` instead.