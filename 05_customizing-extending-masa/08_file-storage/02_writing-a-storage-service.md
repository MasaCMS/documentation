---
layout: default
title: Writing a storage service
nav_order: 2
grand_parent: Customizing/Extending Masa
parent: File storage
last_modified_date: 16-10-2026 13:00
permalink: /customizing-extending-masa/file-storage/writing-a-storage-service/
---

# Writing a storage service
New in 8.0
{: .label .label-orange }
{: .no_toc }

A custom storage service is a CFML component that implements the interface `mura.fileStorage.IUserAssetStorageService`. You ship it in a module and register it when Masa CMS starts. On this page, you build a module called `myStorage` with a storage service called `myStorageService`.

Before you start, read [How file storage works](/customizing-extending-masa/file-storage/how-file-storage-works/).

## Table of contents
{: .no_toc .text-delta }

- TOC
{:toc}

## 1. Create the module

Create a folder for the module in the global `modules` directory of your Masa CMS installation:

```
modules/
  myStorage/
    model/
      handlers/
        myStorageHandler.cfc
      services/
        myStorageService.cfc
```

Masa CMS registers every component in a module's `model` folder as a bean, named after the file. `myStorageService.cfc` becomes the bean `myStorageService`.

Keep these points in mind:

* **Don't put the storage service in a folder called `beans` or `entities`.** Masa CMS registers components in those folders as transients, and creates a new instance each time code asks for one. A storage service must be a singleton, so put it in another folder, such as `services`.
* **The module doesn't need a `config.xml.cfm` file.** That file makes a module available in the Layout Manager, which a storage service doesn't need.
* **Masa CMS creates the storage service when it loads the module, by calling `init()` without arguments.** Don't give `init()` any required arguments.

## 2. Implement the interface

Create `model/services/myStorageService.cfc`. It implements `mura.fileStorage.IUserAssetStorageService` and has one method for each operation in the interface.

The skeleton below has every method, with the arguments and return types the interface requires. Replace each `throw()` with code for your storage backend. The [Storage service reference](/customizing-extending-masa/file-storage/storage-service-reference/) explains what each method must do.

```cfscript
component
	implements="mura.fileStorage.IUserAssetStorageService"
	extends="mura.cfobject"
	output="false"
{

	public any function init() {
		// Read your module's settings here (bucket, credentials, endpoint, ...).
		return this;
	}

	// ==================== Read ====================

	public string function readFile(required string path) {
		throw(type="NotImplemented", message="readFile");
	}

	public any function readFileBinary(required string path) {
		throw(type="NotImplemented", message="readFileBinary");
	}

	// ==================== Write and delete ====================

	public void function writeFile(required string path, required any content) {
		throw(type="NotImplemented", message="writeFile");
	}

	public void function deleteFile(required string path) {
		throw(type="NotImplemented", message="deleteFile");
	}

	public void function deleteDirectory(required string path, boolean recurse=false) {
		throw(type="NotImplemented", message="deleteDirectory");
	}

	// ==================== Exists, list and directories ====================

	public boolean function fileExists(required string path) {
		throw(type="NotImplemented", message="fileExists");
	}

	public boolean function directoryExists(required string path) {
		throw(type="NotImplemented", message="directoryExists");
	}

	public query function listDirectory(required string path, string filter="*", string type="all") {
		throw(type="NotImplemented", message="listDirectory");
	}

	public void function createDirectory(required string path) {
		throw(type="NotImplemented", message="createDirectory");
	}

	// ==================== Copy, move and rename ====================

	public void function copyFile(required string source, required string destination) {
		throw(type="NotImplemented", message="copyFile");
	}

	public void function moveFile(required string source, required string destination) {
		throw(type="NotImplemented", message="moveFile");
	}

	public void function renameFile(required string source, required string destination) {
		throw(type="NotImplemented", message="renameFile");
	}

	// ==================== Upload ====================

	public struct function uploadFile(required string destination, required string fileField) {
		throw(type="NotImplemented", message="uploadFile");
	}

	// ==================== Local copies for image operations ====================

	public string function resolveToLocal(required string path) {
		throw(type="NotImplemented", message="resolveToLocal");
	}

	public void function releaseLocal(required string localPath) {
		throw(type="NotImplemented", message="releaseLocal");
	}

	public void function writeFromLocal(required string localPath, required string remotePath) {
		throw(type="NotImplemented", message="writeFromLocal");
	}

	// ==================== Serving ====================

	public string function getBaseUrl(required string siteid) {
		throw(type="NotImplemented", message="getBaseUrl");
	}

	public boolean function streamToResponse(required string path, string method="inline") {
		throw(type="NotImplemented", message="streamToResponse");
	}

	// ==================== File cache ====================

	public void function uploadBinary(required any data, required string contentType, required string key) {
		throw(type="NotImplemented", message="uploadBinary");
	}

	public void function deleteObject(required string key) {
		throw(type="NotImplemented", message="deleteObject");
	}

	public array function listObjects(required string path, string prefix="") {
		throw(type="NotImplemented", message="listObjects");
	}

}
```

The CFML engine checks the component against the interface when Masa CMS creates it. If a method is missing, or an argument or return type doesn't match, Masa CMS fails to start.

{: .note}
If your storage backend works like a local file system, for example a network drive, you can extend `mura.fileStorage.localStorageService` instead and only override the methods you need to change.

## 3. Add your settings

Keep the settings for your storage backend in your module, not in Masa CMS core. A convenient place is the [configuration file](/getting-started/configuration/configuration-file/), `config/settings.ini.cfm`. Masa CMS loads every setting in that file, including settings it doesn't know:

```ini
mystoragebucket=my-bucket
mystorageendpoint=https://storage.example.com
```

Read them in your storage service's `init()`:

```cfscript
public any function init() {
	var configBean = getBean("configBean");
	variables.bucket = configBean.getValue(property="mystoragebucket", defaultValue="");
	variables.endpoint = configBean.getValue(property="mystorageendpoint", defaultValue="");
	return this;
}
```

Don't put credentials in your module's code. You can also set these settings as [environment variables](/getting-started/configuration/env-variables/), for example `MURA_MYSTORAGEBUCKET`.

## 4. Register the storage service

Create `model/handlers/myStorageHandler.cfc`. In its `onApplicationLoad` event, point the `fileStorageService` alias at your storage service:

```cfscript
component extends="mura.cfobject" output="false" {

	function onApplicationLoad(m) {
		getServiceFactory().addAlias("fileStorageService", "myStorageService");
	}

}
```

From now on, every time Masa CMS asks for `fileStorageService`, it gets `myStorageService`.

{: .warning}
Register the storage service in a module event handler's `onApplicationLoad`, as shown above. Masa CMS calls this event while it loads the module, before it uses file storage for the first time. The bean factory keeps the first storage service it hands out under the name `fileStorageService`. If you change the alias later, for example in `onSiteRequestStart`, Masa CMS keeps using the local storage service until the application reloads.

## 5. Try it out

1. Reload the application.
2. Upload a file in the File Browser under 'User Assets', and check that it's stored in your storage backend.
3. Open the file's URL, `/sites/{File Pool ID}/assets/...`, and check that the file is served from your storage backend. This needs the URL rewrite rules described in [Web server configuration](/getting-started/configuration/web-server-configuration/).
4. Add an image to a page, and check that Masa CMS stores the image and its resized versions in your storage backend.
5. Rotate or crop an image in the File Browser.
6. Delete the file and the image, and check that they're gone from your storage backend, including the resized versions.

## 6. Test your storage service

Write automated tests for your storage service in your module's own test suite. Masa CMS includes tests for its local storage service, which show the behaviour Masa CMS expects from storage:

* `core/tests/specs/mura/core/fileStorageLocal.cfc`: files attached to content, the file cache, resized images, and image operations.
* `core/tests/specs/mura/core/fileBrowserLocal.cfc`: User Assets operations through the File Browser.

They're a useful starting point for your own tests.
