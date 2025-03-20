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

## Setting ACL for an image when uploading to S3

When uploading images in Masa CMS then new images are created with different sizes based of this new image.
If you have configured Masa CMS to upload these images to S3 then Masa CMS will also try to set the ACL of those new images.
The settings are: group='all' and 'permission=read'.
Setting the ACL on these images is deprecated and will be removed in the future.
You will have to make changes to the configuration of your S3 bucket in AWS.

## Support for Non BCrypt Passwords

The support of not using BCrypt Passwords with the setting `bcryptpasswords=false` in the settings.ini.cfm is deprecated.
Please use BCrypt to hash your passwords. When updating this setting to `true`, bear in mind that you will need to reset all your passwords on your Masa installation. You can use the 'Forget your password?' functionality for this.
The old non-bcrypt way of hashing passwords is obsolete and will be removed in the future.

## Support for LegacySessions

The support of legacysession with the setting `uselegacysessions=true` in the settings.ini.cfm is deprecated.
These code constructs are very old, are no longer supported, and will be removed in the future.
We advise not to use this setting anymore.

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
