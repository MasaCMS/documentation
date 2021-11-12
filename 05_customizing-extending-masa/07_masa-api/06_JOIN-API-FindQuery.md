---
layout: default
title: JSON API - FindQuery
nav_order: 1
grand_parent: Customizing/Extending Masa
parent: Masa API
last_modified_date: 12-11-2021 13:00
permalink: /customizing-extending-masa/masa-api/JSON-API-FindQuery/
---

# FindQuery
Get an array of entity items.

## Endpoint
```
GET https://yourdomain.com/{context}/index.cfm/_api/json/v1/{siteid}/{entityname}/?
```
OR
```
GET https://yourdomain.com/{context}/index.cfm/_api/json/v1/?method=findquery&siteid={siteid}&entityname={entityname}/?
```

## Request & Query Parameters

| Parameter    | Value                                                                                                                                                                                                                                                                                                                                                  |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| context      | The path to where Mura CMS resides within the webroot (typically, an empty string).                                                                                                                                                                                                                                                                    |
| siteid       | The SiteID of where the entity will be stored.                                                                                                                                                                                                                                                                                                         |
| entityname   | The entity's name. For example: `?entityname=content`                                                                                                                                                                                                                                                                                                  |
| fields       | _Optional._ A comma-separated listed of fields to return. For example: `?fields=title,summary,contentid`                                                                                                                                                                                                                                               |
| maxitems     | _Optional._ Limit the number of records to return. For example: `?maxitems=10`                                                                                                                                                                                                                                                                         |
| itemsperpage | _Optional._ Sets the desired number of items to return for each page. For example: `?itemsperpage=3`                                                                                                                                                                                                                                                   |
| pageindex    | _Optional._ Sets the desired page for pagination. For example: `?pageindex=2`                                                                                                                                                                                                                                                                          |
| sort         | _Optional._ Control the sort order and direction of entities by specific attributes/fields. To sort decending, prefix the attribute/field with a minus sign (`-`). You may explicitly use the plus sign (`+`) to indicate the default setting of ascending. For example, to sort by "credits" ascending, and "title" decending: `?sort=credits,-title` |
| cachedwithin | _Optional._ Sets the desired cache timespan in seconds. For example: `?cachedwithin=120`                                                                                                                                                                                                                                                               |

## Custom Query Parameters
Filter results by passing an attribute name of your entity, and the value to search for. Use the star `(*)`to denote wildcard.

The following example assumes the entity has an attribute named `title`:

```
GET https://yourdomain.com/{context}/index.cfm/_api/json/v1/?method=findquery&siteid={siteid}&entityname={entityname}&title=about*
```
This should return any entities with a `title` attribute that starts with `about`, such as "about, About, About Us, About Time."

## Example Response
If one or more entities are found, an `items` array will be present in the `data` object.

```json
{
   "data":{
      "endindex":1,
      "startindex":1,
      "totalpages":1,
      "totalitems":1,
      "links":{
         "self":"http://domain/index.cfm/_api/json/v1/default/?&sort=title&entityname=content&siteid=default&fields=title,summary,contentid&itemsperpage=10&maxitems=50&method=undefined&pageIndex=1"
      },
      "itemsperpage":10,
      "items":[
         {
            "entityname":"content",
            "images":{
               
            },
            "contentid":"00000000000000000000000000000000001",
            "siteid":"default",
            "url":"/",
            "links":{
               "renderered":"http://domain/index.cfm/_api/json/v1/default/_path/",
               "categoryassignments":"http://domain/index.cfm/_api/json/v1/default?method=findQuery&siteid=default&entityName=contentCategoryAssign&contenthistid=14CA1DCF-41A8-4D04-861AFE9D4162CD7C",
               "relatedcontent":"http://domain/index.cfm/_api/json/v1/default?method=findRelatedContent&siteid=default&entityName=content&id=00000000000000000000000000000000001",
               "crumbs":"http://domain/index.cfm/_api/json/v1/default?method=findCrumbArray&siteid=default&entityName=content&id=00000000000000000000000000000000001",
               "stats":"http://domain/index.cfm/_api/json/v1/default?method=findOne&siteid=default&entityName=stats&id=00000000000000000000000000000000001",
               "self":"http://domain/index.cfm/_api/json/v1/default/_path/",
               "comments":"http://domain/index.cfm/_api/json/v1/default?method=findQuery&siteid=default&entityName=comment&contentid=00000000000000000000000000000000001",
               "site":"http://domain/index.cfm/_api/json/v1/default?method=findOne&entityName=site&siteid=default",
               "parent":"http://domain/index.cfm/_api/json/v1/default?method=findOne&siteid=default&entityName=content&id=00000000000000000000000000000000END",
               "kids":"http://domain/index.cfm/_api/json/v1/default?method=findQuery&siteid=default&entityName=content&parentid=00000000000000000000000000000000001"
            },
            "id":"00000000000000000000000000000000001",
            "title":"Home",
            "summary":""
         }
      ],
      "pageindex":1
   },
   "params":{
      "sort":"title",
      "entityname":"content",
      "siteid":"default",
      "fields":"title,summary,contentid",
      "itemsperpage":10,
      "maxItems":50,
      "pageindex":1
   },
   "method":"findQuery",
   "apiversion":"v1"
}
```