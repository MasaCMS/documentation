---
layout: default
title: File Browser
nav_order: 9
grand_parent: Content
parent: Managing content
last_modified_date: 12-01-2022 09:00
permalink: /content/managing-content/filebrowser/
---

# File Browser
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

- TOC
{:toc}
## File Browser Oveview
With the File Browser enabled in the left menu the 'File Browser' menu item is now available.

![](/assets/02_content/03_managing_content/09_filebrowser/01_filebrowser_menu.png)

An overview of the File Brower is shown:

![](/assets/02_content/03_managing_content/09_filebrowser/02_filebrowser_overview.png)

There are several options:
* The buttons 'User Assets', 'Sites Files', 'Application Root' are the three file locations that are important for Masa CMS. Clicking on a buttons takes you to these locations.
* Files can be displayd in List View (the default) or Grid View.
* You can filter files and directories in the input 'Type to filter'.

## Uploading a file
You can upload files to the File Browser as follows:

1. Click on 'Drop files here to upload, or click to browse'
![](/assets/02_content/03_managing_content/09_filebrowser/03_filebrowser_upload.png)
2. A file dialog of your file system now opens. Select the file you want to upload. It is also possible to upload multiple files by selecting multiple files from your file system.
3. The files are now being uploaded and shown in the overview:
![](/assets/02_content/03_managing_content/09_filebrowser/04_filebrowser_upload_2.png)


## File operations
On the left side of the filename of each file there are three dots. Click on them to open a menu with the available file operations:

![](/assets/02_content/03_managing_content/09_filebrowser/05_filebrowser_options.png)

* Edit; you can edit the content of the file. This option is only availabe for text files.
* Move; move the file to another directory.
* Rename; rename the file. Note: You can not change the extension of the file.
* Download; download the file.
* Delete: delete the file from the file system.

### Editing an image file
If the file is an image, it can be edited in the File Browser.
![](/assets/02_content/03_managing_content/09_filebrowser/06_filebrowser_image_modal.png)

Under 'Edit Image' there are several image manipulation options:
* Rotate Left
* Rotate Right
* Resize

![](/assets/02_content/03_managing_content/09_filebrowser/06_filebrowser_image_modal_edit_image.png)

### Duplicating an image file
An image has an extra three dot menu option 'Duplicate' to duplicate an image.
## Folders

### Create a new folder
You can create a new folder by clicking the 'Add Folder' button.

![](/assets/02_content/03_managing_content/09_filebrowser/07_filebrowser_add_folder.png)


A modal now opens in which you provide the name of the folder.
![](/assets/02_content/03_managing_content/09_filebrowser/08_filebrowser_folder_modal.png)


The new folder is created and displayed in the file overview.
![](/assets/02_content/03_managing_content/09_filebrowser/09_filebrowser_folder_added.png)

### Folder operations
In the file overview each folder has a three dots menu item on the left of the folder name. Clicking on it opens a menu with the following options:

* Rename; rename the folder.
* Delete; delete the folder. Note: You can only delete folders which are empty.

## Disabeling File Browser
By default the File Browser is enabled in Masa CMS.  If you don't want give users acces to the file system via the File Browser, then you can disable this feature. Goto your `settings.ini.cfm` file and and set the value `filemanagerenabled` to `false`. It should look like this:
```markdown
filemanagerenabled=false
```
Reload Masa CMS to apply the changes. The File Browser is now disabled. It will not be shown in the menu