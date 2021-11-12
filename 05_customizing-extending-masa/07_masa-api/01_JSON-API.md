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


## Response Format
On success, the HTTP status code in the response header is 200 OK and the response body contains a data object in JSON format. On error, the header status code is an error code and the response body contains an error object.

### Example Response
```json
{
    "data": {
    "key": "value"
    }
}
```

## Response Status Codes
The JSON API uses the following response status codes:

| Status Code | Description                                                                                                                                                                                                                                               |
| ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 200         | OK - The request has succeeded. The client can read the result of the request in the body and the headers of the response.                                                                                                                                |
| 400         | Bad Request - The request could not be understood by the server due to malformed syntax. The message body will contain more information; see **Error Handling**, below.                                                                                       |
| 401         | Unauthorized - The request requires user authentication or, if the request included authoriation credentials, authorization has been refused for those credentials. Also, the JSON API feature may not be enabled for the site; see **How To Enabl**, above. |
| 403         | Forbidden - The server understood the request, but is refusing to fulfill it. For example, requestor does not have permission to a requested method.                                                                                                      |
| 404         | Not Found - The requested resource could not be found. This error can be due to a temporary or permanent condition.                                                                                                                                       |

## Error Handling
When an error occurs, the response data attribute will not exist. The response will instead contan an error attribute.

### Example Error Response
```json
{
    "error": {
        "message": "Insufficient Account Permissions"
    }
}
```

### Example Response Handler
```js
    $.getJSON('/index.cfm/json/v1/default/content/').then(
        function( resp ) {
            if ( 'error' in resp ) {
            //handle error
            } else {
            //do stuff
            }
        }
    });
```

## Masa ORM


