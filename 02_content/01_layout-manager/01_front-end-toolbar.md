---
layout: default
title: Front-end toolbar
nav_order: 1
grand_parent: Content
parent: Layout manager
last_modified_date: 20-10-2021 13:00
permalink: /content/layout-manager/front-end-toolbar/
---

# Front-end toolbar

The Front-end Toolbar is a useful tool for inline editing the content of your page. 
It's displayed on top of the website when you are logged into the Masa CMS Admin.
In the following sections the different features are described from left to right.

## Switch visibility of the Front-end toolbar
The first option is the Masa CMS Logo in the Front-end Toolbar. By clicking on the logo you can switch between a full Front-end Toolbar and a small Masa CMS icon. This feature is convenient when you have content directly at the top of page of you website and want to view it.

1. Full toolbar:  
![frontendtoolbarfull](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_full.png)

2. Icon:  
![frontendtoolbaricon](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_icon.png)

## Published and Save
The second option is the 'Published' and 'Save' option.
The options switch depending on if you've made changes on the page or not.

When the page is not changed and you click on 'Published' a popup will open and show you publishing information of the page.  
![frontendtoolbarpublishedmodal](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_published_modal.png)  

When changes are made on the page the 'Published' option is changed to a 'Save' dropdown menu.
![frontendtoolbarsavemenu](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_save_menu.png)  

This menu has the following options:

1. Publish: save the changes and publish them directly.
2. Save Draft: save the changes as a draft to edit and publish later.
3. Save to Change Set: save the changes to a Changeset for updating the site in bulk.
4. Cancel: all changes are discarded.

## Front-end editing
![frontendtoolbareditmenu](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_edit_menu.png)  
This option is a dropdown menu with the following options:  
### Inline Edit
If you click this option then you can inline edit the page. 

#### Editable fields
The editable field wil light up with a red fieldname above it:  
![frontendtoolbarinlineedit](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_inline_edit_red.png)  
You can edit this part of the page. When you are done editing click 'Done Editing' on the right of the page.  
![frontendtoolbardoneediting](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_inline_done_editing.png)  
After editing you also need to save your changes, either by publishing directly, saving to draft or saving to Change Set.

#### Display Regions
The Display Regions that are used in the template that is configured for this page will also light up in red borders:  
![frontendtoolbardonedisplayregionseditred](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_display_regions_edit_red.png)  
A menu on the right of the page opens up with all the Modules you can drag and drop into a Display Region.  
![frontendtoolbardisplaymodules](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_display_modules.png)  
After dropping a Module into a Display Region, you can change the order of the Modules in the Display Region by drag-and-dropping them.
When Modules are placed into a Display Region you can edit them by clicking the blue pencil icon.
A menu on the right of the page opens ups with all the configurable options for this Module.

Example for the Archive Navigation Module:  
![frontendtoolbarmodulearchiveexample](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_module_archive_example.png)  
Each Module has different configurable options; e.g. the Module 'Call to Action' has different options than the Module 'Image'.
After editing you also need to save your changes, either by publishing directly, saving to draft or saving to Change Set.

### Full Edit
Redirects to the Masa CMS Admin to edit the page there.
### Delete
This will the delete the page and all it's content nested beneath it.
You need to confirm this action in a popup:  
![frontendtoolbardeletepopup](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_delete_popup.png)  

## Add
When you selecting this option a popup opens with the Content Types to add to the site.  
![frontendtoolbaraddmenu](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_add_menu.png)  
When selecting an item from the popup you are directed to the Masa CMS Admin where you can edit the new item.

## Version History
When selecting this option you are redirected to the Masa CMS Admin where you can view the Version History of the page:  
![frontendtoolbarversionhistory](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_version_history.png)  

## Permissions
Based on your permissions the Front-end Toolbar changes.
This can be because of Permissions, Approval Chains, etc.

## Multi-device preview
When you selecting this option a popup opens with the current page in a preview mode.
You can preview the page on different devices. These devices are Desktop, Tablet, Tablet Landscape, Phone, Phone Landscape.  
![frontendtoolbarpreview](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_preview.png)  
This way you can check how a page is displayed on different devices.

## Change Sets
These options are used for viewing changes that are in a Change Set.
Change Sets are helpfull for bulk updating the content of your website. 
All changes to your content are put in one Change Set, which can be published all at once.  

### Managing Change Sets
Change Sets themselves are managed in the Masa CMS Admin. In het left menu goto the second item 'Staging'.  
![frontendtoolbaradminstaging](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_admin_staging.png)  
An overview of all your Change Sets are shown.   

### Adding changes to Change Sets
Changes are put into the Change Set by saving the changes to a Change set, rather than publishing them directly or saving them as draft.  
![frontendtoolbarsavechangeset](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_save_change_set.png) 

### View changes in Change Set
By selecting a Change Set in the dropdown you can see the proposed changes applied to the content of the current page.
![frontendtoolbarchangesets](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_changesets.png)  
The second menu item 'Assignments' shows a dropdown of all the changed content items in the current Change Set.
![frontendtoolbarassignments](/assets/02_content/01_layout-manager/01_front-end-toolbar/front-end-toolbar_assignments.png)  
The third item is an indicator to show if the current page is already in the current Change Set or not.