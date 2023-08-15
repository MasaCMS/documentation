---
layout: default
title: Site configuration
nav_order: 5
grand_parent: Getting started
parent: Configuration
last_modified_date: 14-08-2023 10:00
permalink: /getting-started/configuration/site-configuration/
---

# Site configuration  
In the Masa CMS Admin there are site settings in the left menu.  
![siteconfigmenu](/assets/01_getting-started/03_configuration/05_site_configuration/site_configuration_menu.png)  
These are the settings in the context of the current selected site in the menu above.  
![siteconfigcurrentsite](/assets/01_getting-started/03_configuration/05_site_configuration/site_configuration_current_site.png)  

## Edit Settings
Here you can edit the settings for you site.  
![siteconfigsettings](/assets/01_getting-started/03_configuration/05_site_configuration/site_configuration_settings.png)  
The Site ID can not be changed.

## Permissions
Here you can manage the permissions for the Content Manager.  
![siteconfigpermissions](/assets/01_getting-started/03_configuration/05_site_configuration/site_configuration_permissions.png)  
This is done via the Group a User is a member of. Only Users via the System Groups can have access te the Content Manager in the Masa CMS Admin. Member Groups can have editing capabilities via the front-end of the Masa CMS site, but not via the Masa CMS Admin.

## Approval Chains
Here you can edit and manage Approval Chains. Approval Chains allow for a 'chain' of content creation and review by different Users. That way the content on your website always is checked en verified before it is published.

## Class Extensions
Here you can manage the Class Extensions. Class Extensions are a way to customize common objects within Masa CMS. So instead of a default Page content object, you can create a custom Blog content object, which is derived from the Page. In this way you can tailor the content objects in Masa CMS to the needs and topic of your site.

## Create Site Bundle
You can create a Site Bundle of your Site. A Bundle includes a Site's architecture & content, all rendering files (display objects, themes, javascript, etc.). This way you can deploy content from one site to another site across instances. This can be usefull in a OTAP environment or creating a backup of the content of your site..

## Deploy Site Bundle
After creating as Site Bundle, you can deploy the site bundles here. Remember that when deploying a site bundle that all content will be overwritten!

## Web Service (REST)
Masa CMS provides REST Webservices. This way you can create custom front-end clients and let Masa CMS provide the content for them. The content for these clients can then be managed in the Masa CMS Admin.  

## JSON API
Masa CMS provides Webservices based on JSON API. Similair to the WebServices using REST.

## Trash Bin 
When a Content Item is deleted from Masa CMS, it is not immediately removed, but placed into the Trash Bin.