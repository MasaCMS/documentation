---
layout: default
title: JSON API - FindNew
nav_order: 1
grand_parent: Customizing/Extending Masa
parent: Masa API
last_modified_date: 12-11-2021 13:00
permalink: /customizing-extending-masa/masa-api/JSON-API-FindNew/
---

# FindNew
Gets a new entity.

## Endpoint
```
GET https://yourdomain.com/{context}/index.cfm/_api/json/v1/{siteid}/{entityname}/new
```
OR
```
GET https://yourdomain.com/{context}/index.cfm/_api/json/v1/?method=findnew&siteid={siteid}&entityname={entityname}
```
## Request & Query Parameters

| Parameter  | Value                                                                               |
| ---------- | ----------------------------------------------------------------------------------- |
| context    | The path to where Mura CMS resides within the webroot (typically, an empty string). |
| siteid     | The SiteID of where the entity will be stored.                                      |
| entityname | The entity's name.                                                                  |


## Example Response
```json
{
   "data":{
      "id":"2C91A3B0-E375-9383-0B05636E6926868D",
      "name":"Example",
      "links":{
         "relatedentitylink1":"http://...",
         "relatedentitylink2":"http://..."
      }
   }
}
```
