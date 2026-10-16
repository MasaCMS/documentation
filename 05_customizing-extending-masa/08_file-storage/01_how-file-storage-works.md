---
layout: default
title: How file storage works
nav_order: 1
grand_parent: Customizing/Extending Masa
parent: File storage
last_modified_date: 16-10-2026 13:00
permalink: /customizing-extending-masa/file-storage/how-file-storage-works/
---

# How file storage works
New in 8.0
{: .label .label-orange }
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

- TOC
{:toc}

## What goes through the storage service

The storage service handles the files of each site's File Pool:

| Files | Location on disk with local storage |
| :---- | :---------------------------------- |
| User Assets | `{assetdir}/{File Pool ID}/assets/` |
| File cache | `{filedir}/{File Pool ID}/cache/file/` |

`assetdir` and `filedir` are set in the [configuration file](/getting-started/configuration/configuration-file/). By default, both point to the `sites` directory of your Masa CMS installation.

Everything else stays on the local file system, and a custom storage service doesn't change it. This includes the File Browser's 'Site Files' and 'Application Root' locations, themes, modules and plugins.

## The `fileStorageService` bean

Masa CMS code never uses a storage service directly. It always asks the bean factory for the bean named `fileStorageService`:

```cfscript
getBean("fileStorageService").readFile(key);
```

By default, `fileStorageService` is an alias for `localStorageService`, which stores files on the local file system. To use another storage service, you point the alias at your own bean. See [Writing a storage service](/customizing-extending-masa/file-storage/writing-a-storage-service/).

There is one storage service for the whole Masa CMS instance. All sites use the same one.

Masa CMS uses the storage service in these places:

* The `fileWriter` bean checks every path it receives. If the path is inside a site's User Assets, it sends the operation to the storage service. Other paths go to the local file system as before. Code that uses `fileWriter` for User Assets automatically works with any storage service.
* The `fileManager` and `fileDAO` beans use the storage service for the file cache: storing uploaded files, creating resized images, serving files and cleaning up the cache.
* The File Browser uses `fileWriter`, so all User Assets operations in the File Browser go through the storage service.

## Storage keys

The storage service identifies each file by a **storage key**:

```
{File Pool ID}/{type}/{path}
```

For example:

| Storage key | File |
| :---------- | :--- |
| `default/assets/Image/logo.png` | A User Asset in the `Image` folder |
| `default/cache/file/{fileID}.jpg` | An image attached to content |
| `default/cache/file/{fileID}_small.jpg` | The 'small' version of that image |
| `default/cache/file/{fileID}_200x100.jpg` | A custom size of that image |

Storage keys always use forward slashes and never start with a slash. Your storage service receives keys of both types, `assets` and `cache`.

The first part is the site's **File Pool ID**, not its site ID. Sites that share a File Pool share the same keys, and so the same files. With local storage, the key is the file's path relative to `assetdir` (for `assets`) or `filedir` (for everything else). Most cloud storage services can use the key directly as the object name.

The component `mura.fileStorage.storageKey` builds and reads storage keys. You can use it in your own storage service.

## Serving files

Public URLs for User Assets and cached files stay the same with any storage service:

```
/sites/{File Pool ID}/assets/Image/logo.png
/sites/{File Pool ID}/cache/file/{fileID}.jpg
```

With local storage, the web server finds these files on disk and serves them directly. With a cloud storage service, the files aren't on disk. The URL rewrite rules that come with Masa CMS (`htaccess.txt`, `nginx.conf.txt` and `web.config.txt`) send any request for a file that doesn't exist on disk to Masa CMS. See [Web server configuration](/getting-started/configuration/web-server-configuration/).

When a request for `/sites/{site}/assets/...` or `/sites/{site}/cache/...` reaches Masa CMS, it passes the request to the storage service:

1. Masa CMS calls `streamToResponse()`, which writes the file to the HTTP response.
2. If `streamToResponse()` returns `false`, Masa CMS calls `resolveToLocal()` to get a local copy of the file and streams that copy instead.
3. If there is no local copy either, Masa CMS returns a 404.

## Image operations

Masa CMS uses CFML image functions to resize, crop, rotate and flip images. These functions only work on local files. For these operations, Masa CMS:

1. Calls `resolveToLocal()` to get a local copy of the image. A cloud storage service downloads the file to a temporary location.
2. Edits the local copy.
3. Calls `writeFromLocal()` to store the result. A cloud storage service uploads the file.
4. Calls `releaseLocal()` when it no longer needs the local copy. A cloud storage service deletes the temporary file.
