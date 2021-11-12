---
layout: default
title: JSON API - FindOne
nav_order: 1
grand_parent: Customizing/Extending Masa
parent: Masa API
last_modified_date: 12-11-2021 13:00
permalink: /customizing-extending-masa/masa-api/JSON-API-FindOne/
---

# FindOne
Find an entity.

## Endpoint
```
GET https://yourdomain.com/{context}/index.cfm/_api/json/v1/{siteid}/{entityname}/{id}
```
OR

```
GET https://yourdomain.com/{context}/index.cfm/_api/json/v1/?method=findone&site={siteid}&entityname={entityName}&id={id}
```

## Request & Query Parameters

| Parameter  | Value                                                                               |
| ---------- | ----------------------------------------------------------------------------------- |
| context    | The path to where Mura CMS resides within the webroot (typically, an empty string). |
| siteid     | The SiteID of the site being searched.                                              |
| entityname | The entityname being searched. For example: "`content`", "`user`", "`feed`", etc.   |
| id         | The object ID of the entity being searched for.                                     |

## Example Response
The `data` object will contain the entity's keys and corresponding values.

```json
{
    "data": {
    "targetparams":"",
    "path":"00000000000000000000000000000000001,2C91A3B0-E375-9383-0B05636E6926868D",
    "menutitle":"Testing",
    "releaseDate":"",
    "fileid":"",
    "responsesendto":"",
    "id":"2C91A3B0-E375-9383-0B05636E6926868D",
    "type":"Page",
    "lastupdatebyid":"AD771D5C-BE0A-D43D-47F4E201B378BD7A",
    "forceSSL":0,
    "responsemessage":"",
    "subtype":"Default",
    "remoteurl":"",
    "contenttype":"",
    "childtemplate":"",
    "keypoints":"",
    "moduleid":"00000000000000000000000000000000000",
    "inheritobjects":"Inherit",
    "searchExclude":0,
    "featureStop":"",
    "newfile":"",
    "remotesourceurl":"",
    "displayStop":"",
    "remotesource":"",
    "remotePubDate":"",
    "tags":"",
    "majorVersion":0,
    "extendautocomplete":true,
    "contentsubtype":"",
    "url":"/index.cfm/testing/",
    "sortby":"orderno",
    "displayTitle":0,
    "approvalstatus":"",
    "credits":"",
    "oldfilename":"",
    "featureStart":"",
    "siteid":"default",
    "doCache":1,
    "imagesize":"small",
    "imagewidth":"AUTO",
    "target":"_self",
    "minorVersion":0,
    "approvalgroupid":"",
    "assocfilename":"",
    "lastUpdate":"2015-01-29T15:45:51",
    "summary":"",
    "images":{},
    "template":"",
    "moduleassign":"",
    "displayStart":"",
    "isFeature":0,
    "filesize":"",
    "approvingchainrequest":false,
    "categoryid":"",
    "tcontent_id":"0",
    "isLocked":0,
    "isNav":1,
    "newstags":"",
    "orderno":1,
    "htmltitle":"Testing",
    "urltitle":"testing",
    "approvalchainoverride":false,
    "body":"",
    "requestid":"",
    "restrictgroups":"",
    "active":1,
    "metadesc":"",
    "audience":"",
        "links":{
            "site":"http://cf11:8080/index.cfm/_api/json/v1/default?method=findOne&entityName=site&siteid=default",
            "categoryassignments":"http://cf11:8080/index.cfm/_api/json/v1/default?method=findQuery&siteid=default&entityName=contentCategoryAssign&contenthistid=2C92F953-E042-CBF6-42F66BD74A4BEC0B",
            "parent":"http://cf11:8080/index.cfm/_api/json/v1/default?method=findOne&siteid=default&entityName=content&id=00000000000000000000000000000000001",
            "stats":"http://cf11:8080/index.cfm/_api/json/v1/default?method=findOne&siteid=default&entityName=stats&id=2C91A3B0-E375-9383-0B05636E6926868D",
            "crumbs":"http://cf11:8080/index.cfm/_api/json/v1/default?method=findCrumbArray&siteid=default&entityName=content&id=2C91A3B0-E375-9383-0B05636E6926868D",
            "comments":"http://cf11:8080/index.cfm/_api/json/v1/default?method=findQuery&siteid=default&entityName=comment&contentid=2C91A3B0-E375-9383-0B05636E6926868D",
            "relatedcontent":"http://cf11:8080/index.cfm/_api/json/v1/default?method=findRelatedContent&siteid=default&id=2C91A3B0-E375-9383-0B05636E6926868D",
            "renderered":"http://cf11:8080/index.cfm/_api/json/v1/default/_path/testing",
            "kids":"http://cf11:8080/index.cfm/_api/json/v1/default?method=findQuery&siteid=default&entityName=content&parentid=2C91A3B0-E375-9383-0B05636E6926868D"
            },
    "restricted":0,
    "metakeywords":"",
    "nextN":10,
    "fileext":"",
    "notes":"",
    "display":1,
    "created":"2015-01-29T15:45:51",
    "contenthistid":"2C92F953-E042-CBF6-42F66BD74A4BEC0B",
    "responsedisplayfields":"",
    "expires":"",
    "imageheight":"AUTO",
    "filename":"testing",
    "relatedcontentsetdata":"",
    "sortdirection":"asc",
    "contentid":"2C91A3B0-E375-9383-0B05636E6926868D",
    "changesetid":"",
    "displayinterval":"Daily",
    "sourceiterator":"",
    "mobileExclude":0,
    "extendsetid":"",
    "remoteid":"",
    "parentid":"00000000000000000000000000000000001",
    "preserveid":"2C92F953-E042-CBF6-42F66BD74A4BEC0B",
    "title":"Testing",
    "lastupdateby":"Steve Withington",
    "approved":1,
    "extenddata":"",
    "blogtags":"",
    "responseChart":0
    }
}
```