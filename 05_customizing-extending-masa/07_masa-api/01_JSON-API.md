---
layout: default
title: JSON API
nav_order: 1
grand_parent: Customizing/Extending Masa
parent: Masa API
last_modified_date: 20-10-2021 13:00
permalink: /customizing-extending-masa/masa-api/JSON-API/
---

# JSON API

## Introduction
The JSON API allows Masa CMS to be the main content creation hub within an organization, and allows developers to build their front-ends as pure JavaScript clients.

## Base URL
The base URL for the API endpoints is:

```
https://yourDomain.com/{context}/index.cfm/_api/json/v1/
```

## API Endpoint Reference

| Method   | Endpoint                                                                                                                                                                                                  | Usage                                                                                                              | Returns                                                                                                      |
| -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| GET      | [/{siteid}/{entityname}/{id}](https://fix-this-url.com/json-api/findone/)                                                                                          | [FindOne](https://fix-this-url.com/json-api/findone/)                       | [data](https://fix-this-url.com/json-api/findone/)                    |
| GET      | [/{siteid}/entityname}/{ids}](https://fix-this-url.com/json-api/findmany/)                                                                                         | [FindMany](https://fix-this-url.com/json-api/findmany/)                     | [data](https://fix-this-url.com/json-api/findmany/)                   |
| GET      | [/{siteid}/{entityname}/new](https://fix-this-url.com/json-api/findnew/)                                                                                           | [FindNew](https://fix-this-url.com/json-api/findnew/)                       | [data](https://fix-this-url.com/json-api/findnew/)                    |
| GET      | [/{siteid}/{entityname}/?](https://fix-this-url.com/json-api/findquery/)                                                                                           | [FindQuery](https://fix-this-url.com/json-api/findquery/)                   | [data](https://fix-this-url.com/json-api/findquery/)                  |
| GET      | [/{siteid}/{entityname}/{id}/{releatedentity}/?](https://fix-this-url.com/json-api/findrelatedentity/)                                                             | [FindRelatedEntity](https://fix-this-url.com/json-api/findrelatedentity/)   | [data](https://fix-this-url.com/json-api/findrelatedentity/)          |
| GET,POST | [/?method=findCalenderItems&siteid={siteid}&calendarid={calendarid}&start={start}&end={end}&format={format}](https://fix-this-url.com/json-api/findcalendaritems/) | [FindCalendarItems](https://fix-this-url.com/json-api/findcalendaritems/)   | [data / events](https://fix-this-url.com/json-api/findcalendaritems/) |
| POST     | [/?method=generateCSRFTokens&siteid={siteid}&context={entityid}](https://fix-this-url.com/json-api/generatecsrftokens/)                                            | [GenerateCSRFTokens](https://fix-this-url.com/json-api/generatecsrftokens/) | [data](https://fix-this-url.com/json-api/generatecsrftokens/)         |
| POST     | [/{siteid}/{entityname}/?csrf\_token={csrf\_token}&csrf\_token\_expires={csrf\_token\_expires}](https://fix-this-url.com/json-api/save/)                           | [Save](https://fix-this-url.com/json-api/save/)                             | [data](https://fix-this-url.com/json-api/save/)                       |
| DELETE   | [/{siteid}/{entityname}/{id}/?csrf\_token={csrf\_token}&csrf\_token\_expires={csrf\_token\_expires}](https://fix-this-url.com/json-api/delete/)                    | [Delete](https://fix-this-url.com/json-api/delete/)                         | [data](https://fix-this-url.com/json-api/delete/)                     |
| GET,POST | [/{siteid}/login/?username={username}&password={password}](https://fix-this-url.com/json-api/login/)                                                               | [Login](https://fix-this-url.com/json-api/login/)                           | [data](https://fix-this-url.com/json-api/login/)                      |
| GET,POST | [/{siteid}/logout](https://fix-this-url.com/json-api/logout/)                                                                                                      | [Logout](https://fix-this-url.com/json-api/logout/)                         | [data](https://docs.murasoftware.com/v7/mura-developers/mura-rendering/json-api/logout/)                     |

## Masa ORM


