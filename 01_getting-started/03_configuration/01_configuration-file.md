---
layout: default
title: Configuration file
nav_order: 1
grand_parent: Getting started
parent: Configuration
last_modified_date: 24-07-2023 13:00
permalink: /getting-started/configuration/configuration-file/
---
# Configuration file
All the the Masa settings can be found in `/config/setting.ini.cfm`. A template for this file is available in`/core/templates/settings.template.cfm`
## The "settings.ini.cfm" File
This file contains the configuration setting for Masa CMS.

### Example
```markdown
[production]
adminemail=info@masacms.com
dbtype=mysql
yourOwnKey=Your Value
```
You can use a semicolon (;) to comment a line. This line is then ignored.

## Reference
You can find a reference for this configuration file below.

### Settings Section

#### appreloadkey

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>appreload</code></dd>
  <dt>Description</dt>
  <dd>The URL variable used to reload Masa CMS</dd>
</dl>

#### mode

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>production</code></dd>
  <dt>Description</dt>
  <dd>The mode in which Masa CMS is running determines which configuration is loaded.</dd>
</dl>

### Mode Section

#### admindomain

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### admindir

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>/admin</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### adminemail

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### adminssl

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### allowedadmindomain

<dl>
  <dt>Type</dt>
  <dd>list</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>List of domains of which users set to system users when authenticating using SSO</dd>
</dl>

#### allowautoupdates

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### alloweddomain

<dl>
  <dt>Type</dt>
  <dd>list</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>List of domains of which users are allowed to authenticate using SSO</dd>
</dl>

#### allowedadmingroupemaillist

<dl>
  <dt>Type</dt>
  <dd>list</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>List of email addresses of users that are added to admin group when authenticating using SSO</dd>
</dl>

#### allowedindexfiles

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>index.cfm, index.json, index.html</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### allowlocalfiles

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### allowsimplehtmlforms

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### alloweds2emaillist

<dl>
  <dt>Type</dt>
  <dd>list</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>List of email addresses of users that are set to super user when authenticating using SSO</dd>
</dl>

#### assetdir

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### assetpath

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### autodiscoverplugins

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### autoresetpasswords

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### autoupdatemode

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>default</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### azureadclientid
New in 7.4.3
{: .label .label-orange }
{: .no_toc }

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Oauth client ID for Azure AD SSO configuration</dd>
</dl>

#### azureadclientsecret
New in 7.4.3
{: .label .label-orange }
{: .no_toc }

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Oauth client secret for Azure AD SSO configuration</dd>
</dl>

#### azureadtenantid
New in 7.4.3
{: .label .label-orange }
{: .no_toc }

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Oauth tenant ID for Azure AD SSO configuration</dd>
</dl>

#### bcryptpasswords

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### clientmanagement

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### clientstorage

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### confirmsaveasdraft

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### context

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### cookiedomain

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### cookiepath

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### customtagpaths

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### datasource

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### dbcasesensitive

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### dbpassword

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### dbtype

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### dbtablespace

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>USERS</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### dbusername

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### debuggingenabled

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### defaultfilemode

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>777</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### enablemuratag

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### enableoauth

<dl>
  <dt>Type</dt>
  <dd>list</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>List of enabled oauth providers.<br>Options: <code>google</code>, <code>facebook</code>, <code>github</code>, <code>azuread</code></dd>
</dl>

#### encryptionkey

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd>hash of <code>getCurrentTemplatePath()</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### errortemplate

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>/muraWRM/config/error.html</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### facebookclientid

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Oauth client ID for Facebook SSO configuration</dd>
</dl>

#### facebookclientsecret

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Oauth client secret for Facebook SSO configuration</dd>
</dl>

#### filedir

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### fmshowapplicationroot

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### fmshowsitefiles

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### forceadminssl

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### githubclientid

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Oauth client ID for Github SSO configuration</dd>
</dl>

#### githubclientsecret

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Oauth client secret for Github SSO configuration</dd>
</dl>

#### googleclientid

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Oauth client ID for Google SSO configuration</dd>
</dl>

#### googleclientsecret

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Oauth client secret for Google SSO configuration</dd>
</dl>

#### hashurls

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### haslockablenodes

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### hstsmaxage

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>1200</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### imageinterpolation

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>highQuality</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### indexfileinurls

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Display index.cfm in the URL.</dd>
</dl>

#### javasettingsloadcoldfusionclasspath

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### javasettingsloadpaths

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>/requirements/lib</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### javasettingswatchextensions

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>jar,class</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### javasettingswatchinterval

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>60</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### locale

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>server</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### loginstrikes

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>4</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### mailserverip

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### mailserverpassword

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### mailserverpopport

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>110</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### mailserversmtpport

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>25</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### mailserverssl

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### mailservertls

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### mailserverusername

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### maxarchivedversions

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>50</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### maxportalitems

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>1000</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### maxsourceimagewidth

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>4000</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### mfa

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### mfaperdevice

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### mfasendauthcode

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### notifywithversionlink

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### ormautomanagesession

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### ormcfclocation

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### ormdatasource

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### ormdbcreate

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>update</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### ormenabled

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### ormeventhandling

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### ormflushatrequestend

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### ormsavemapping

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### ormskipcfcwitherror

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### ormusedbformapping

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### ping

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### plugindir

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### port

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>${cgi.SERVER\_PORT</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### proxypassword

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### proxyport

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>${cgi.SERVER\_PORT</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### proxyserver

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### proxyuser

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### purgedrafts

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### recaptchasitekey

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### recaptchasecret

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### recaptchalanguage

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>en</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### rendermuraalerts

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### requesttimeout

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>1000</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### sameformfieldsasarray

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### scriptprotect

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### scriptprotectexceptions

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>body,source,params</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### securecookies

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### sessioncookiesexpires

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>never</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### sendfrommailserverusername

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### sessionhistory

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>0</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### sessiontimeout

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>180</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### showadminloginhelp

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Display the "Forget your password" link on the administrator login page.</dd>
</dl>

#### showextensionsindefault

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Display the assigned Extended Attributes of the Basic tab below the body, instead of being hidden behind the "Manage Extended Attributes" button.</dd>
</dl>

#### siteidinurls

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Include the site ID in the URL.</dd>
</dl>

#### sortpermission

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>editor</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### strictfactory

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### stricthtml

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### stricthtmlexclude

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### strongpasswordregex

<dl>
  <dt>Type</dt>
  <dd>regex</dd>
  <dt>Default</dt>
  <dd><code>(?=^.{7,15}$)(?=.*\d)(?![.\n])(?=.*[a-zA-Z]).*$</code></dd>
  <dt>Description</dt>
  <dd>The regular expression used to validate the password for its strength.</dd>
</dl>

#### strongpasswords

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Enforce strong password requirements.</dd>
</dl>

#### tempdir

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### title

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>Masa CMS</code></dd>
  <dt>Description</dt>
  <dd>The application title, typically used in the HTML head section.</dd>
</dl>

#### usedefaultsmtpserver

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### usefilemode

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>

#### windowdocumentdomain

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd></dd>
</dl>