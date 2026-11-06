---
layout: default
title: File storage
nav_order: 8
parent: Customizing/Extending Masa
has_children: true
last_modified_date: 16-10-2026 13:00
permalink: /customizing-extending-masa/file-storage/
---

# File storage
New in 8.0
{: .label .label-orange }

Masa CMS stores two kinds of files for each site:

* **User Assets:** files you upload through the File Browser under 'User Assets', or through the editor.
* **The file cache:** files attached to content, such as images and downloads, and the resized versions Masa CMS creates of each image.

By default, Masa CMS stores these files on the local file system of the server it runs on. All reading and writing goes through a **storage service**. You can replace that storage service with your own, for example to store files in Amazon S3, Google Cloud Storage or Azure Blob Storage. You do this in a module, without changing any Masa CMS code.

{: .note}
Masa CMS only includes the local storage service. The built-in S3 file store (`filestore=s3`) was removed in Masa CMS 8.0. To store files in S3, write a custom storage service.

In this section:

* [How file storage works](/customizing-extending-masa/file-storage/how-file-storage-works/): which files go through the storage service, how files are identified, and how they are served.
* [Writing a storage service](/customizing-extending-masa/file-storage/writing-a-storage-service/): build and register your own storage service in a module.
* [Storage service reference](/customizing-extending-masa/file-storage/storage-service-reference/): every method a storage service implements, and the rules each one follows.
