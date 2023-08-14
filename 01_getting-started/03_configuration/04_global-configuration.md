---
layout: default
title: Global configuration
nav_order: 4
grand_parent: Getting started
parent: Configuration
last_modified_date: 11-08-2023 10:00
permalink: /getting-started/configuration/global-configuration/
---

# Global configuration
In the Masa CMS Admin there are global settings in the left menu.  
![globalconfigmenu](/assets/01_getting-started/03_configuration/04_global_configuration/global_configuration_menu.png)  
## Sites
Here you can see an overview of all the Masa sites in your current installation.  
![globalconfigsites](/assets/01_getting-started/03_configuration/04_global_configuration/global_configuration_sites.png)  
You can also view and change the bind order.  
![globalconfigbindorder](/assets/01_getting-started/03_configuration/04_global_configuration/global_configuration_bind_order.png)
## Add Site
When adding a site the most important configuration item is the Site ID. Choose this carefully, since it can't be changed.  
![globalconfigaddsite](/assets/01_getting-started/03_configuration/04_global_configuration/global_configuration_add_site.png)

## Copy Site

A site can be copied from one existing site to another existing site within Masa CMS.  
![globalconfigcopysite](/assets/01_getting-started/03_configuration/04_global_configuration/global_configuration_copy_site.png)

## Plugins
Here you can see an overview of all the Plugins that are installed in the Masa CMS.
![globalconfigplugins](/assets/01_getting-started/03_configuration/04_global_configuration/global_configuration_plugins.png)
You can also install new Plugins, either via upload or via an URL.  
When you go into the details of a Plugin you can see on which Site(s) the plugin is assigned to under 'Site Assignment'.  
![globalconfigpluginssiteassigment](/assets/01_getting-started/03_configuration/04_global_configuration/global_configuration_plugins_site_assignment.png)  
This means that the plugin is availabe for that particulair site. 

## Update Masa CMS Core
You can auto-update the Masa CMS Core, but be sure to make a backup of your Masa CMS installation.  
![globalconfigupdatecore](/assets/01_getting-started/03_configuration/04_global_configuration/global_configuration_update_core.png)

## Reload application
For some changes the application needs to be reloaded for them to have effect. After reloading you are redirected to the Content Manager.