---
layout: default
title: Configuration file
nav_order: 1
grand_parent: Getting started
parent: Configuration
last_modified_date: 20-10-2021 13:00
permalink: /getting-started/configuration/configuration-file/
---
# Configuration file
All the the Masa settings can be found in `/config/setting.ini.cfm`. A template for this file is available in`/core/templates/settings.template.cfm`
## The "settings.ini.cfm" File
This file contaitns the configuration setting for Masa.

### Example
```markdown
[production]
adminemail=info@masacms.com
dbtype=mysql
yourOwnKey=Your Value
```
You can use a secmiconlon (;) to comment a line. This line is then ignored.

## Reference
You can find a reference for this configuration file below.

### Settings Section

| Key          | Type   | Default    | 
| ------------ | ------ | ---------- | 
| appreloadkey | string | appreload  | 
| mode         | string | production |

### Production Section

| Key                                 | Type    | Default                                                  |
| ----------------------------------- | ------- | -------------------------------------------------------- |
| admindomain                         | string  | empty string                                             |
| admindir                            | string  | /admin                                                   |
| adminemail                          | string  | empty string                                             |
| adminssl                            | boolean | false                                                    |
| allowautoupdates                    | boolean | true                                                     | 
| allowedindexfiles                   | string  | index.cfm, index.json, index.html                        | 
| allowlocalfiles                     | boolean | false                                                    | 
| allowsimplehtmlforms                | boolean | true                                                     | 
| assetdir                            | string  | empty string                                             | 
| assetpath                           | string  | empty string                                             | 
| autodiscoverplugins                 | boolean | false                                                    | 
| autoresetpasswords                  | boolean | false                                                    | 
| autoupdatemode                      | string  | default                                                  | 
| bcryptpasswords                     | boolean | true                                                     | 
| clientmanagement                    | boolean | false                                                    | 
| clientstorage                       | string  | empty string                                             | 
| confirmsaveasdraft                  | boolean | true                                                     | 
| context                             | string  | empty string                                             | 
| cookiedomain                        | string  | empty string                                             | 
| cookiepath                          | string  | empty string                                             | 
| customtagpaths                      | string  | empty string                                             | 
| datasource                          | string  | empty string                                             | 
| dbcasesensitive                     | boolean | false                                                    | 
| dbpassword                          | string  | empty string                                             | 
| dbtype                              | string  | empty string                                             | 
| dbtablespace                        | string  | USERS                                                    | 
| dbusername                          | string  | empty string                                             | 
| debuggingenabled                    | boolean | true                                                     | 
| defaultfilemode                     | integer | 777                                                      | 
| enablemuratag                       | boolean | true                                                     | 
| encryptionkey                       | string  | hash of `getCurrentTemplatePath()`                       | 
| errortemplate                       | string  | /muraWRM/config/error.html                               | 
| filedir                             | string  | empty string                                             | 
| fmshowapplicationroot               | boolean | true                                                     | 
| fmshowsitefiles                     | boolean | true                                                     | 
| forceadminssl                       | boolean | true                                                     | 
| hashurls                            | boolean | false                                                    | 
| haslockablenodes                    | boolean | false                                                    | 
| hstsmaxage                          | integer | 1200                                                     | 
| imageinterpolation                  | string  | highQuality                                              | 
| indexfileinurls                     | boolean | true                                                     | 
| javasettingsloadcoldfusionclasspath | boolean | true                                                     | 
| javasettingsloadpaths               | string  | /requirements/lib                                        | 
| javasettingswatchextensions         | string  | jar,class                                                | 
| javasettingswatchinterval           | integer | 60                                                       | 
| locale                              | string  | server                                                   | 
| loginstrikes                        | integer | 4                                                        | 
| mailserverip                        | string  | empty string                                             | 
| mailserverpassword                  | string  | empty string                                             | 
| mailserverpopport                   | integer | 110                                                      | 
| mailserversmtpport                  | integer | 25                                                       | 
| mailserverssl                       | boolean | false                                                    | 
| mailservertls                       | boolean | false                                                    | 
| mailserverusername                  | string  | empty string                                             | 
| maxarchivedversions                 | integer | 50                                                       | 
| maxportalitems                      | integer | 1000                                                     | 
| maxsourceimagewidth                 | integer | 4000                                                     | 
| mfa                                 | boolean | false                                                    | 
| mfaperdevice                        | boolean | false                                                    | 
| mfasendauthcode                     | boolean | true                                                     | 
| notifywithversionlink               | boolean | true                                                     | 
| ormautomanagesession                | boolean | true                                                     | 
| ormcfclocation                      | string  | empty string                                             | 
| ormdatasource                       | string  | empty string                                             | 
| ormdbcreate                         | string  | update                                                   | 
| ormenabled                          | boolean | true                                                     | 
| ormeventhandling                    | boolean | true                                                     | 
| ormflushatrequestend                | boolean | false                                                    | 
| ormsavemapping                      | boolean | false                                                    | 
| ormskipcfcwitherror                 | boolean | false                                                    | 
| ormusedbformapping                  | boolean | false                                                    | 
| ping                                | boolean | false                                                    | 
| plugindir                           | string  | empty string                                             | 
| port                                | integer | ${cgi.SERVER\_PORT}                                      | 
| proxypassword                       | string  | empty string                                             | 
| proxyport                           | integer | ${cgi.SERVER\_PORT}                                      | 
| proxyserver                         | string  | empty string                                             | 
| proxyuser                           | string  | empty string                                             | 
| purgedrafts                         | boolean | true                                                     | 
| recaptchasitekey                    | string  | empty string                                             | 
| recaptchasecret                     | string  | empty string                                             | 
| recaptchalanguage                   | string  | en                                                       | 
| rendermuraalerts                    | boolean | true                                                     | 
| requesttimeout                      | integer | 1000                                                     | 
| sameformfieldsasarray               | boolean | false                                                    | 
| scriptprotect                       | boolean | true                                                     | 
| scriptprotectexceptions             | string  | body,source,params                                       | 
| securecookies                       | boolean | false                                                    | 
| sessioncookiesexpires               | string  | never                                                    | 
| sendfrommailserverusername          | boolean | true                                                     | 
| sessionhistory                      | integer | 0                                                        | 
| sessiontimeout                      | integer | 180                                                      | 
| showadminloginhelp                  | boolean | true                                                     | 
| siteidinurls                        | boolean | false                                                    | 
| sortpermission                      | string  | editor                                                   | 
| strictfactory                       | boolean | true                                                     | 
| stricthtml                          | boolean | false                                                    | 
| stricthtmlexclude                   | string  | empty string                                             | 
| strongpasswordregex                 | regex   | (?=^.{7,15}$)(?=.\*\\d)(?!\[.\\n\])(?=.\*\[a-zA-Z\]).\*$ | 
| strongpasswords                     | boolean | false                                                    | 
| tempdir                             | string  | empty string                                             | 
| title                               | string  | Masa CMS                                                 | 
| usedefaultsmtpserver                | boolean | true                                                     | 
| usefilemode                         | boolean | false                                                    | 
| windowdocumentdomain                | string  | empty string                                             | 