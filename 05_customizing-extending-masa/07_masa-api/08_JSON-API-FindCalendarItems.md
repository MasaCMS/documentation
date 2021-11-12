---
layout: default
title: JSON API - FindCalendarItems
nav_order: 1
grand_parent: Customizing/Extending
 Masa
parent: Masa API
last_modified_date: 12-11-2021 13:00
permalink: /customizing-extending-masa/masa-api/JSON-API-FindCalendarItems/
---

# FindCalendarItems
Get calendar content items.

## Endpoint
```
GET https://yourdomain.com/{context}/index.cfm/_api/json/v1/?method=findcalendaritems&siteid={siteid}&calendarid={calendarid}&start={start}&end={end}&format={format}
```

## Request & Query Parameters

| Path parameter | Value                                                                                                                     |
| -------------- | ------------------------------------------------------------------------------------------------------------------------- |
| context        | The path to where Mura CMS resides within the webroot (typically, an empty string).                                       |
| siteid         | The SiteID of where the entity will be stored.                                                                            |
| calendarid     | The `contentid` of a Mura CMS content item with the "Type" set to Calendar.                                               |
| start          | _Optional_. The start date to filter by.                                                                                  |
| end            | _Optional_. The end date to filter by.                                                                                    |
| format         | _Optional_. Options are `default` (the default setting) or `fullcalendar`. This determines how the response is formatted. |
| categoryid     | _Optional_. Filters results by categoryid.                                                                                |
| tag            | _Optional_. Filters results by tag.                                                                                       |


## Example "Default" Response
If multiple entities are found, an `items` array will be present in the `data` object.
```json{
   "data":{
      "items":[
         {
            "contentid":"2C91A3B0-E375-9383-0B05636E6926868D",
            "title":"Event 1"
         },
         {
            "contentid":"6C92F953-E042-CBF6-42F66BD74A4BEC0B",
            "title":"Event 2"
         }
      ]
   }
}
```

If only one entity is found, the data object will contain the entity's keys and corresponding values.
```json
{
   "data":{
      "contentid":"2C91A3B0-E375-9383-0B05636E6926868D",
      "title":"Event 1"      
   }
}
```

## Example "FullCalendar" Response
An `events` array will be returned.

```json
{
   "events":[
      {
         "contentid":"2C91A3B0-E375-9383-0B05636E6926868D",
         "title":"Event 1"
      },
      {
         "contentid":"6C92F953-E042-CBF6-42F66BD74A4BEC0B",
         "title":"Event 2"
      }
   ]
}
```