---
layout: default
title: List of Deprecations
nav_order: 1
parent: Deprecations
last_modified_date: 13-12-2021 13:00
permalink: /deprecations/list-of_deprecations/
---

# List of Deprecations

The following functionality is deprecated as of Masa CMS 7.5

## ACL Settings for Image Uploads to S3

When uploading images in Masa CMS, new images are created in various sizes based on the original image. If you have configured Masa CMS to upload these images to S3, it will attempt to set the Access Control List (ACL) for these images. The default settings are:

- Group: all
- Permission: read

Please note that setting the ACL for these images is deprecated and will be removed in a future release. To ensure continued functionality, you will need to update the configuration of your S3 bucket in AWS.

## Deprecation of Non-BCrypt Password Support

The use of non-BCrypt passwords, controlled by the setting `bcryptpasswords=false` in `settings.ini.cfm`, is now deprecated. We strongly recommend switching to BCrypt for password hashing. When enabling this setting (`bcryptpasswords=true`), please be aware that you will need to reset all user passwords in your Masa installation. You can do this using the "Forgot your password?" functionality.
Note that the old, non-BCrypt password hashing method will be removed in a future release.

## Deprecation of Legacy Session Support

The use of legacy sessions, controlled by the setting `uselegacysessions=true` in `settings.ini.cfm`, is deprecated. These legacy session mechanisms are outdated, unsupported, and will be removed in a future version. We recommend discontinuing the use of this setting.

---

The following functionality is deprecated as of Masa CMS 7.4.8

## Unsupported Locales

In the Masa CMS Admin under 'Site Settings' you can set the Locale for your site.

However not all these Locales are supported in het Masa CMS Admin when working with date selection.

In the dropdown of Locales we have inidicated these unsupported locales with the text '(not supported, deprecated)' after the name of the Locale.

![](/assets/06_deprecations/list_of_deprecations/deprecations_supported_locales.png)

We advise you to check if your Locale is supported and if not to update your site to a supported Locale.

---

The following functionality is deprecated as of Masa CMS 7.3.

## Mura tags

The tags `[mura]` and `[sava]` can be used in content for dynamic expression, like so:

```cfscript
[mura]TimeFormat(Now(), 'hh:mm:ss tt')[/mura]
```

This use of these tags is deprecated. Please use the '[m]' tag instead, like so:

```cfscript
[m]TimeFormat(Now(), 'hh:mm:ss tt')[/m]
```

Please update your content accordingly.

## Masa Scope

You can access various functions and variables in Masa CMS through the Masa Scope, like so:

```cfscript
#$.content('title')#
```

OR

```cfscript
#mura.content('title')#
```

This use of the scopes `$` (dollar scope) and `mura` is deprecated. Please only use the `m` scope instead, like so:

```cfscript
#m.content('title')#
```

## setCustomMuraScopeKey

This function is part of the Masa Scope. The function `setCustomMuraScopeKey` has been deprecated.
Please use the function `setCustomMasaScopeKey` instead.

Replace:

```cfscript
m.setCustomMuraScopeKey('myCustomObject', customObject);
```

with:

```cfscript
 m.setCustomMasaScopeKey('myCustomObject', customObject);
```

## MuraScope.cfc

The object MuraScope is deprecated and will be replaced by MasaScope.cfc.

Most likely you will not instantiate the Masa Scope yourself.
As an example however, the following example is something that can be used:

```cfscript
application.serviceFactory.getBean("MuraScope").init('mySiteID');
```

If you are using a construction where you instantiate the Masa Scope, then upgrade your code to instantiate the MasaScope object instead of the MuraScope object.

```cfscript
application.serviceFactory.getBean("MasaScope").init('mySiteID');
```

## Simple Forms

Simple Forms are deprecated; please use Forms created with the Form Builder instead.
Migrate existing Simple Forms to Forms created with the Form Builder.

Creating Simple Forms is switched off by default now. You can still maintain existing Simple Forms.
If you still need to create a Simple Form, you need to change the setting in the `settings.ini.cfm`.

```markdown
allowSimpleHTMLForms=true
```

Don't forget to reload Masa.
The 'Simple Form' option now becomes available again:

![](/assets/06_deprecations/list_of_deprecations/deprecation_simple_forms_2.png)

## Razuna

Razuna is deprecated. Migrate to different Digital Asset Management system.

Razuna is switched off by default. If you still need to use it for some reason, you need to change the setting in the `settings.ini.cfm`.

```markdown
razuna=true
```
