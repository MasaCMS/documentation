---
layout: default
title: Quick Start
nav_order: 0
parent: Getting started
has_children: true
last_modified_date: 10-11-2021 13:00
permalink: /getting-started/quick-start/
---

# Quick Start 

Follow this guide to have a running Masa CSM instance running in no time.

1. Dowload and install [Docker](https://www.docker.com/get-started), if you not already have done so.

2. Download Masa CMS from this direct [download](https://github.com/MasaCMS/MasaCMS/archive/refs/heads/main.zip) link.
A .zip file is now being download.

3.  Unzip the .zip file into a directory of you choice. We will refer in this guide to this as the `MasaCMSRootDir`.

4. Goto your `MasaCMSRootDir` in a terminal window.

5. CD in the following subdirectory:
    * `\core\docker\local-mysql` for Windows and Mac
    * `/core/docker/local-mysql` for Linux 

6.  Type in the following command:  `docker-compose up`.
Two Docker containers will start, one for the database and one for Masa CMS.

   NOTE: Mac users will have to change the port number for the database container, since that port is already in use by the OS itself.        
   {: .alert .alert-warning }

7. Goto [http://localhost:8080](http://localhost:8080) to visit your local Masa CMS site.

8. Goto [http:/localhost:8080/admin](http:/localhost:8080/admin) to visit the Masa CMS Adminstator. You can login with the following credentials:
    * Username: `admin`
    * Password: `admin`