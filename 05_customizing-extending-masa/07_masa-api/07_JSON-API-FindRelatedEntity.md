---
layout: default
title: JSON API - FindRelatedEntity
nav_order: 1
grand_parent: Customizing/Extending
 Masa
parent: Masa API
last_modified_date: 12-11-2021 13:00
permalink: /customizing-extending-masa/masa-api/JSON-API-FindRelatedEntity/
---

# FindRelatedEntity
Gets a related entity.

## Endpoint
```
GET https://yourdomain.com/{context}/index.cfm/_api/json/v1/{siteid}/{entityname}/{id}/{relatedentity}/?
```
OR
````
GET https://yourdomain.com/{context}/index.cfm/_api/json/v1/?method=findquery&siteid={siteid}&entityname={relatedentity}&entitynamefk={id}
```

## Request & Query Parameters

| Path parameter | Value                                                                               |
| -------------- | ----------------------------------------------------------------------------------- |
| context        | The path to where Mura CMS resides within the webroot (typically, an empty string). |
| siteid         | The SiteID of where the entity will be stored.                                      |
| entityname     | The entity's name.                                                                  |
| id             | The ID of an entity.                                                                |
| relatedentity  | The name of a related entity.                                                       |
| entitynamefk   | The ID of an entity.                                                                |

## Example Response
If multiple entities are found, an `items` array will be present in the `data` object.
```json
{
   "data":{
      "items":[
         {
            "id":"2C91A3B0-E375-9383-0B05636E6926868D",
            "name":"Example",
            "links":{
               "relatedentitylink1":"http://...",
               "relatedentitylink2":"http://..."
            }
         },
         {
            "id":"6C92F953-E042-CBF6-42F66BD74A4BEC0B",
            "name":"Another Example",
            "links":{
               "relatedentitylink1":"http://...",
               "relatedentitylink2":"http://..."
            }
         }
      ]
   }
}
```

If only one entity is found, the data object will contain the entity's keys and corresponding values.

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