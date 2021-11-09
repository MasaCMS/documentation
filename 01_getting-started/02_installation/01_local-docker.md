---
layout: default
title: Local - Docker
nav_order: 1
grand_parent: Getting started
parent: Installation
last_modified_date: 4-11-2021 14:00
permalink: /getting-started/installation/local-docker/
---

# Local: Docker

Prerequisite: [Docker](https://www.docker.com/) must be installed.

1. Clone the MasaCMS repository from [GitHub](https://github.com/MasaCMS/MasaCMS) to you local machine.

2. Goto the directory in which you cloned the MasaCMs Repository with a commandline tool (like Bash).

3. Goto the subfolder `\core\docker\`. In this folder you can find several Docker configurations for different database flavours.
    * `local-mssql`  for Microsoft SQL Server
    * `local-mysql`  for MySQL
    * `local-oracle` for Oracle
    * `local-postgresql` for PostgreSQL

4. Goto the subfolder of the database you want to use.

5. Start the Docker image by typing `docker-compose up`. Two Docker containers will start, one for the database and one for Masa CMS.

    NOTE: Mac users will have to change the port number for the database container, since that port is already in use by the OS itself.
    {: .alert .alert-warning }

6. Goto [http://localhost:8080](http://localhost:8080) to visit your local Masa site.

7. Goto [http:/localhost:8080/admin](http:/localhost:8080/admin) to visit the Masa Adminstator. You can login with the following credentials:
    * Username: `admin`
    * Password: `admin`