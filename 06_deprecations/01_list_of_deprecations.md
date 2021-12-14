---
layout: default
title: List of Deprecations
nav_order: 1
parent: Deprecations
last_modified_date: 13-12-2021 13:00
permalink: /deprecations/list-of_deprecations/
---

# List of Deprecations
The following functionality is deprecated as of Masa CMS 7.3.

##  Mura tags 
The tags `[mura]` and `[sava]` can be used in content for dynamic expression, like so:

```cfscript
[mura]TimeFormat(Now(), 'hh:mm:ss tt')[/mura]
```
    
This use of these tag is deprecated. Please use the '[m]' tag instead, like so:

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
````