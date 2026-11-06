---
layout: default
title: Storage service reference
nav_order: 3
grand_parent: Customizing/Extending Masa
parent: File storage
last_modified_date: 16-10-2026 13:00
permalink: /customizing-extending-masa/file-storage/storage-service-reference/
---

# Storage service reference
New in 8.0
{: .label .label-orange }
{: .no_toc }

A storage service implements the interface `mura.fileStorage.IUserAssetStorageService`. This page describes each method, and the rules Masa CMS relies on. The local storage service, `mura.fileStorage.localStorageService`, is a complete working example.

## Table of contents
{: .no_toc .text-delta }

- TOC
{:toc}

## Paths and keys

Unless a method says otherwise, every `path`, `source`, `destination`, `remotePath` and `key` argument is a **storage key**, such as `default/assets/Image/logo.png` or `default/cache/file/{fileID}_small.jpg`. Your storage service receives keys for both User Assets (`assets`) and the file cache (`cache`). See [Storage keys](/customizing-extending-masa/file-storage/how-file-storage-works/#storage-keys).

The `localPath` arguments are the exception. They are absolute paths on the local file system.

## Read

### readFile

```cfscript
string function readFile(required string path)
```

Returns the content of a file as a string, like `fileRead()`.

### readFileBinary

```cfscript
any function readFileBinary(required string path)
```

Returns the content of a file as binary data, like `fileReadBinary()`.

## Write and delete

### writeFile

```cfscript
void function writeFile(required string path, required any content)
```

Writes a string or binary content to a file, and replaces the file if it exists. Creates parent directories when needed.

Write the content exactly as given. Don't add a line break at the end: when the caller wants one, Masa CMS adds it before calling `writeFile()`.

### deleteFile

```cfscript
void function deleteFile(required string path)
```

Deletes a file. Does nothing if the file doesn't exist.

### deleteDirectory

```cfscript
void function deleteDirectory(required string path, boolean recurse=false)
```

Deletes a directory. If `recurse` is `false` and the directory isn't empty, throw an error. If `recurse` is `true`, delete everything in it.

## Exists, list and directories

### fileExists

```cfscript
boolean function fileExists(required string path)
```

Returns whether a file exists, like `fileExists()`.

### directoryExists

```cfscript
boolean function directoryExists(required string path)
```

Returns whether a directory exists, like `directoryExists()`.

### listDirectory

```cfscript
query function listDirectory(required string path, string filter="*", string type="all")
```

Lists the contents of a directory, without subdirectories. Returns a query with the same columns as `cfdirectory action="list"`:

| Column | Content |
| :----- | :------ |
| `name` | Name of the file or directory |
| `directory` | The directory that contains it |
| `size` | Size in bytes, `0` for directories |
| `type` | `File` or `Dir` |
| `datelastmodified` | Date and time of the last change |

* `filter` works like the `filter` attribute of `cfdirectory`, for example `*.jpg`. Masa CMS also passes an exact name, to look up a single item.
* `type` is `all`, `file` or `dir`.

The File Browser uses this method to show folders, and Masa CMS uses it to clean up the file cache. Fill in every column.

### createDirectory

```cfscript
void function createDirectory(required string path)
```

Creates a directory, including any missing parent directories. Does nothing if the directory exists.

Some storage services, such as Amazon S3, don't have real directories. Decide how you represent them, for example with an empty placeholder object. A directory created with `createDirectory()` must show up in `directoryExists()` and `listDirectory()`, even when it's empty.

## Copy, move and rename

Masa CMS only calls these methods when both the source and the destination are in storage. When it moves files between the local file system and storage, it uses [`writeFromLocal()`](#writefromlocal) and [`resolveToLocal()`](#resolvetolocal) instead.

### copyFile

```cfscript
void function copyFile(required string source, required string destination)
```

Copies a file.

### moveFile

```cfscript
void function moveFile(required string source, required string destination)
```

Moves a file.

### renameFile

```cfscript
void function renameFile(required string source, required string destination)
```

Renames a file or a directory. The destination is in the same directory as the source, with a new name. When you rename a directory, everything in it moves along.

## Upload

### uploadFile

```cfscript
struct function uploadFile(required string destination, required string fileField)
```

Stores a file uploaded through an HTTP form. `fileField` is the name of the form field, and `destination` is the key of the directory to store the file in.

Returns a struct with the same keys as the result of `cffile action="upload"`:

| Key | Content |
| :-- | :------ |
| `serverFile` | File name as stored |
| `serverFileName` | File name as stored, without extension |
| `serverFileExt` | Extension as stored |
| `serverDirectory` | Directory the file was stored in |
| `contentType` | MIME type, for example `image` |
| `contentSubType` | MIME subtype, for example `png` |
| `fileSize` | Size in bytes |
| `clientFile` | Original file name |
| `clientFileName` | Original file name, without extension |
| `clientFileExt` | Original extension |
| `timeCreated` | Date and time of the upload |

## Local copies for image operations

Masa CMS edits images with CFML image functions, which only work on local files. These three methods give Masa CMS a local copy and store the result. See [Image operations](/customizing-extending-masa/file-storage/how-file-storage-works/#image-operations).

### resolveToLocal

```cfscript
string function resolveToLocal(required string path)
```

Returns the absolute local path of a file. A storage service that doesn't store files locally downloads the file to a temporary location and returns that path.

Masa CMS never deletes the returned path itself. It always calls `releaseLocal()` when it's done.

### releaseLocal

```cfscript
void function releaseLocal(required string localPath)
```

Releases a path returned by `resolveToLocal()`. Delete the temporary copy if your storage service created it. Leave any other path alone: Masa CMS calls `releaseLocal()` for every path it resolved, without checking where it came from.

The local storage service does nothing here, because `resolveToLocal()` returns the stored file itself.

### writeFromLocal

```cfscript
void function writeFromLocal(required string localPath, required string remotePath)
```

Stores a local file at `remotePath`, and replaces any file already there. Masa CMS doesn't delete the old file first, so `writeFromLocal()` must replace it.

After storing the file, remove the local file at `localPath`. The local storage service moves the file into place.

## Serving

### streamToResponse

```cfscript
boolean function streamToResponse(required string path, string method="inline")
```

Writes a file to the current HTTP response, with the right `Content-Type`, `Content-Length` and `Content-Disposition` headers. `method` is `inline` or `attachment`, and sets the `Content-Disposition`.

Returns `true` if the file was sent. Returns `false` if the file doesn't exist. Masa CMS then tries `resolveToLocal()`, and returns a 404 if that fails too. See [Serving files](/customizing-extending-masa/file-storage/how-file-storage-works/#serving-files).

### getBaseUrl

```cfscript
string function getBaseUrl(required string siteid)
```

Returns the base URL for the public files of a site, without a trailing slash. For example, `https://my-bucket.s3.amazonaws.com/default/assets`. The local storage service returns the site's file asset path followed by `/assets`.

Masa CMS doesn't call this method at the moment. Implement it so other code can build public URLs for your storage.

## File cache

Masa CMS uses these methods to manage the file cache: files attached to content, and the resized versions of images. The keys look like `{File Pool ID}/cache/file/{fileID}_{variant}.{extension}`.

### uploadBinary

```cfscript
void function uploadBinary(required any data, required string contentType, required string key)
```

Stores binary content under `key`, and replaces anything already there. `contentType` is the MIME type of the content, such as `image/jpeg`.

### deleteObject

```cfscript
void function deleteObject(required string key)
```

Deletes the file stored under `key`. Does nothing if it doesn't exist.

### listObjects

```cfscript
array function listObjects(required string path, string prefix="")
```

Returns the full keys of the files directly under `path` whose names start with `prefix`. Doesn't include subdirectories. Returns an empty array when nothing matches, or when `path` doesn't exist.

Masa CMS uses this method to delete every cached version of a file, including custom image sizes. The returned keys go straight to `deleteObject()`. A cloud storage service needs permission to list objects for this, as well as to delete them. For example, Amazon S3 needs `s3:ListBucket`.
