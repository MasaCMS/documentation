---
layout: default
title: Permissions
nav_order: 4
grand_parent: Getting started
parent: Basic concepts
last_modified_date: 31-07-2023 10:00
permalink: /getting-started/basic-concepts/permissions/
---

# Permissions

## Overview
There are four types of Permissions in Masa CMS.
Permissions are managed in Masa CMS Admin.
### Users
There are two type of Users:  
1. Site Member; a User that only has access to the front-end of the site. Site members don't have access to the Masa CMS Admin.
2. System user; a User that has access to the Masa CMS Admin.

Users can be an Group Member of multiple Groups. Through a group memberships a User can aquire additional Permissions.

### Groups
There are two types of Groups:  
1. Member Group; A Group in which Site Members and System Users can be added.
2. System Group; A Group in which only System Users can be added.

### Content Manager Permissions
In the Masa CMS Admin the Content Manager Permissions can be managed under "Site Settings" --> "Permission".
In this overview accces to the Content Manager is managed via Groups.  
![permissionscontentmanager](/assets/01_getting-started/01_basic-concepts/04_permissions/permissions_content_manager.png)  

Users in different Groups can have access to the Content Manager.
### Content Permissions
In het Masa CMS Admin you can manage the Permissions of a content item via the 'Actions' menu on the top right the page.  
![permissionscontentedit](/assets/01_getting-started/01_basic-concepts/04_permissions/permissions_content_edit.png)  

Here Permissions are managed through Groups.  
![permissionscontentpermissions](/assets/01_getting-started/01_basic-concepts/04_permissions/permissions_content_permissions.png)  
### Other permissions
Permissions can be applied to the following items:
1. Content Staging Permissions
2. Comments Permissions
3. Categories Permissions
4. Collections Permissions
With these items Permissions are also managed through Groups.  

[Read more in depth about Permissions functionality](/managing-masa/permissions/).