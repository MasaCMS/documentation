---
layout: default
title: Templates
nav_order: 3
grand_parent: Front-End/Layout Manager
parent: Add a theme
last_modified_date: 18-09-2023 11:00
permalink: /front-end-layout-manager/add-a-theme/templates/
---

# Templates
Templates are essentially HTML files with dynamics content. To make these .html files dynamic, the extension must be changed to .cfm.  
Be sure to put all the dynamics content between '<cfoutput>' tags to output the result.  
In the .cfm files all the functionality of CFML is now available to you. 

## Dynamic Parts
Through Masa CMS the M-scope is available. Functionalitity can be accessd through the variable 'm'.
### m.dspBody()
With 'dspBody' you can render various parts of the content of the page on which a template is selected.  
#### Example
```cfscript
#m.dspBody(
    body=m.content('body')
    , pageTitle=''
    , crumbList=false
    , showMetaImage=false
)#					
```

### m.dspObjects({number})#
With 'dspObjects({number})' you have can create a placeholder on your Template on which to drag Modules in the 'Inline Edit' mode.
The '{number}' corresponds with the number of the Display Region configured in your site.
Soo that in your Template you can have multiple Display Regions.

#### Example

```cfscript
#m.dspObjects(2)#				
```