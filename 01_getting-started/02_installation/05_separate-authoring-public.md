---
layout: default
title: Separate authoring and public environment
nav_order: 5
grand_parent: Getting started
parent: Installation
last_modified_date: 23-10-2026 12:00
permalink: /getting-started/installation/separate-authoring-public/
---

# Separate authoring and public environment

In a standard installation, editors and visitors use the same Masa CMS server. For extra security, you can split this into two environments:

- an **authoring server**, where editors manage content through the admin, and
- a **public server**, which serves the sites to visitors and has no admin.

The admin is then no longer reachable from the internet, which removes an important target for attackers. The public server can also be scaled and tuned for visitors, without affecting the editors.

## Architecture

Both servers run their own Masa CMS installation and share one database:

| Component | Role |
|-----------|------|
| **Database** | One database, used by both servers. Content, users, settings and permissions are stored here, so changes made on the authoring server are immediately available on the public server. |
| **Authoring server** | Runs the Masa CMS admin. Place it on an internal network or behind a VPN, so that only editors can reach it. |
| **Public server** | Serves the sites to visitors. The admin is disabled. You can run more than one public server behind a load balancer. |

{: .important}
The configurations on this page are examples. Every setup is different, so review and test them before using them in production. The system administrator is responsible for the final configuration.

## Requirements

- Both servers run the **same version** of Masa CMS, and the same themes, modules and plugins. Masa CMS updates the database when it starts after an upgrade, so always upgrade all servers together.
- Both servers use a datasource that points to the shared database.
- Both servers have access to the same uploaded files. See [Share uploaded files](#share-uploaded-files).

## Share uploaded files

Uploaded files are stored on disk, not in the database. This includes File content items, Associated Images, files uploaded through the file browser, and files that visitors upload through forms on the public server. Both servers need to see the same files.

Choose one of these options:

### Shared storage (recommended)

Mount the same network storage on both servers, and point Masa CMS to it in `/config/settings.ini.cfm` on **both** servers:

```ini
filestore=fileDir
filedir=/mnt/masa-files
assetdir=/mnt/masa-files
assetpath=https://www.example.com/masa-files
```

- `filedir` and `assetdir` are the folders on disk where Masa CMS stores files. Masa CMS creates a folder per site inside them.
- `assetpath` is the URL where browsers can load these files. Configure your web server to serve the shared storage at that URL, for example with an alias.

Because the files are served from a different location, adjust the lockdown rules of [Restrict access to the cache folder](/getting-started/security/restrict-cache-folder-access/) and [Secure upload folders](/getting-started/security/secure-upload-folders/) to this path.

{: .warning}
Set permissions on the shared storage so that only the CFML engine can write to it. Do not use `defaultfilemode=777`, which makes files writable for every user on the server. Leave `usefilemode=false` and manage permissions on the storage itself.

### File synchronisation

Copy files between the servers with a synchronisation tool. This is the most complex option: files that visitors upload through forms on the public server must also be copied back to the authoring server, otherwise editors cannot see them. If you only synchronise from the authoring server to the public server, those uploads are lost from the editors' view.

## Configure the public server

Add the following to `/config/settings.ini.cfm` on the public server, and reload Masa CMS:

```ini
disableadmin=true
enablefrontendtools=false
```

- `disableadmin=true` switches off the admin. Requests to the admin are handled as regular page requests, which normally show the 404 page. Use this setting rather than deleting the `/admin` folder: a deleted folder comes back with the next upgrade, the setting does not.
- `enablefrontendtools=false` hides the front-end editing tools, which would not work without the admin.

Visitors can still log in on the public server to access restricted content (extranet). Only editing is done on the authoring server.

### Database access

The public server still writes to the database: for example form submissions, comments, login attempts, and commands between servers. Give it a database user that can read and write data, but not change the database structure.

If you use a database replica for read queries, you can point `readonlydatasource` (with `readonlydbusername` and `readonlydbpassword`) to it. Masa CMS then sends queries that only read data to that datasource, and everything else to the main datasource.

## Configure the authoring server

- Make the admin only reachable from your internal network or VPN. See [Lock down the admin](/getting-started/security/lock-down-admin/).
- Editors preview content on the authoring server. If they need to see the public site exactly as visitors do, use the public server.

## Keep the servers in sync

When an editor publishes content or clears the cache on the authoring server, the public server must also clear its cache. Masa CMS does this through the shared database: each server registers itself, and commands such as cache purges and application reloads are passed on to the other servers.

Make sure this is enabled on **all** servers:

```ini
broadcastclustercommands=true
broadcastcachepurges=true
broadcastappreloads=true
```

## Deploying code

Themes, modules and plugins are files on each server, and they must be the same everywhere.

- Store your themes, modules and custom code in version control, such as Git.
- Deploy changes to all servers at the same time, for example with a deployment pipeline.
- Plugins installed through the admin are only written to the authoring server. Copy the plugin files to the public servers as well, or include them in your deployment.

## Development and test environments

For development and testing, use separate environments with their own database. Copy the production database and files to these environments regularly, so you test against realistic content. Never point a development or test environment to the production database.
