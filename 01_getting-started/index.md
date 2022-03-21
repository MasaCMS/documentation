---
layout: default
title: Getting started
nav_order: 2
has_children: true
last_modified_date: 20-10-2021 13:00
permalink: /getting-started/
---

# Getting started

## Requirements

- [Docker](https://docs.docker.com/get-started/)
- [Commandbox CLI](https://commandbox.ortusbooks.com/getting-started-guide)

## Install

Install Masa CMS using the Commandbox CLI and Forgebox (package manager).

```console
CommandBox> install coldbox
```

## Start

Start a Docker setup that launches a CFML application container and a database container.

_Unix_

```console
> cd core/docker/local-mysql/
> docker compose up
```

_Windows_

```console
> dir core\docker\local-mysql\
> docker compose up
```

## And enjoy!

- Goto [http://localhost:8080](http://localhost:8080) to visit your local Masa CMS site.

- Goto [http:/localhost:8080/admin](http:/localhost:8080/admin) to visit the Masa CMS Administrator. You can login with the following credentials:
    * Username: `admin`
    * Password: `admin`