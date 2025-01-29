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
  <dd>The mode in which Masa CMS is running determines which configuration is loaded</dd>
</dl>

### Mode Section

#### admindomain

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Configures a seperate URL for the Masa CMS Admin</dd>
</dl>

#### admindir

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>/admin</code></dd>
  <dt>Description</dt>
  <dd>Configure a different directory for the Masa CSM Admin other than '/admin'. Masa CMS must be reloaded from the webroot for this change to have effect.</dd>
</dl>

#### adminemail

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>The default email address for the Masa CMS Admin administrator.</dd>
</dl>

#### adminssl

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Configuration option whether a SSL certificate is present for the Masa CMS Admin</dd>
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
  <dd>Configuration option to display auto-update links in the Masa CMS Admin</dd>
</dl>

#### alloweddomain

<dl>
  <dt>Type</dt>
  <dd>list</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>List of domains of which users are allowed to authenticate using SSO, if not allowed the user is created but set to inactive</dd>
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
  <dd>Filenames that are allowed to be used in the index of Masa CMS</dd>
</dl>

#### allowlocalfiles

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Allow whether local files may be used when importing into Masa CMS</dd>
</dl>

#### allowsimplehtmlforms

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>When this value is set to <code>false</code> only forms are allowed that are build using the FormBuilder.</dd>
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

#### allowunicodeinfilenames

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Allow filenames with unicode characters</dd>
</dl>

#### assetdir

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Configurable directory where the assets of your site are located</dd>
</dl>

#### assetpath

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Configurable URL where the assets of you sites are located.</dd>
</dl>

#### autodiscoverplugins

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Let Masa CMS automatically scan for plugins and install them.</dd>
</dl>

#### autoresetpasswords

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>When set to <code>true</code> then the password is reset of the user using the 'Lost Password' functionality. An e-mail with the new password is sent. Otherwise just an e-mail with a link to log in is sent to the user.</dd>
</dl>

#### autoupdatemode

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>default</code></dd>
  <dt>Description</dt>
  <dd>Options are <code>default</code> and <code>preview</code>. This last option allows Beta releases to be used for the update.</dd>
</dl>

#### autoupdatesleep
<dl>
  <dt>Type</dt>
  <dd>numeric</dd>
  <dt>Default</dt>
  <dd><code>empty</code></dd>
  <dt>Description</dt>
  <dd>Tells Masa CMS to pause for a number of seconds after updating the core. This is usefull for files to be synched across multiple servers.</dd>
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
  <dd>Configurable option to encrypt the passwords using BCrypt, if set to <code>false</code> passwords are hashed instead.</dd>
</dl>

#### bcryptlogrounds

<dl>
  <dt>Type</dt>
  <dd>numeric</dd>
  <dt>Default</dt>
  <dd><code>10</code></dd>
  <dt>Description</dt>
  <dd>When BCrypt is being used, then this configures how many logrounds are used for adding salt to the encryption proces.</dd>
</dl>

#### bcryptreseedfrequency

<dl>
  <dt>Type</dt>
  <dd>numeric</dd>
  <dt>Default</dt>
  <dd><code>60</code></dd>
  <dt>Description</dt>
  <dd>When BCrypt is being used, then this configures how often to re-seed in seconds.</dd>
</dl>

#### broadcastclustercommands

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>When Masa CMS is using a cluster, broadcast cluster commmands.</dd>
</dl>

#### broadcastappreloads

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>When Masa CMS is using a cluster, broadcast app reloading.</dd>
</dl>

#### broadcastcachepurges

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>When Masa CMS is using a cluster, broadcast cache purges.</dd>
</dl>

#### bundledeployerroremail

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty</code></dd>
  <dt>Description</dt>
  <dd>If the deployment of a site bundle fails, a mail can be sent to an e-mail address with debugging information.</dd>
</dl>

#### bundleminspacerequired

<dl>
  <dt>Type</dt>
  <dd>numeric</dd>
  <dt>Default</dt>
  <dd><code>1</code></dd>
  <dt>Description</dt>
  <dd>Before attempting to create a site bundle, check if the 'bundleminspacerequired' is available. If not, generate an error. Value is in Gb.</dd>
</dl>

#### cffpconfigfilename

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>cffp.ini.cfm</code></dd>
  <dt>Description</dt>
  <dd>Configure an alternate config file for CFFormProtect.</dd>
</dl>

#### contentgatewaytable

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>tcontent</code></dd>
  <dt>Description</dt>
  <dd>Configure an alternate database table for content, other than 'tcontent'.</dd>
</dl>

#### clearoldbroadcastcommands

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>When Masa CMS is using a cluster, clear the old broadcast commands.</dd>
</dl>

#### clientmanagement

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Application.cfc variable</dd>
</dl>

#### clientstorage

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Application.cfc variable</dd>
</dl>

#### confirmsaveasdraft

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>When you navigate away without saveng an alert is shown if you want to save the changes as 'draft'.</dd>
</dl>

#### context

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Masa CMS wil automatically configure this field when installed. If you move Masa CMS to a different location you must update this setting.</dd>
</dl>

#### cookiedomain

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Configures the domain of the cookie</dd>
</dl>

#### cookiepath

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Configures the domain of the cookie</dd>
</dl>

#### createrequireddirectories

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Setting whether to create the required directories needed for Masa CMS or not. Usefull in a clustered enviroment in which directories are already synched and not need to be created by Masa CMS.</dd>
</dl>

#### customtagpaths

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Configure the path in which the Customtags are located. Comma-delimited list.</dd>
</dl>

#### customurlvardelimiters

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty</code></dd>
  <dt>Description</dt>
  <dd>Configure custom delimeter for URL variables.</dd>
</dl>

#### dashboard
<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Setting whether the Dashboard can be enabled per site in Site Settings. --> Edit Settings --> Modules</dd>
</dl>

#### dashboardcomments

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Show comments on the Dashboard in the Masa CMS Admin.</dd>
</dl>

#### datacollection

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Enable Data Collection Manager.</dd>
</dl>

#### datasource

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Configurable datasource where Masa CMS should acces the database.</dd>
</dl>

#### dbcasesensitive

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Configure if your database is CaSe SeNsItIvE (like Oracle or Postgres)</dd>
</dl>

#### dbpassword

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Do not use this setting if you have datasource configured.</dd>
</dl>

#### dbtype

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Configure which database type Masas CMS is running on. Supported options are 'MS SQL', 'MySQL', 'Postgres' and 'Oracle'</dd>
</dl>

#### dbtablespace

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>USERS</code></dd>
  <dt>Description</dt>
  <dd>Configurable option only for Oracle databases</dd>
</dl>

#### dbusername

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Do not use this setting if you have datasource configured.</dd>
</dl>

#### debuggingenabled

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Configurable option whether so show CFML errors in the browser or use the files under <code>errortemplate</code> config option when set to <code>false</code></dd>
</dl>

#### defaultfilemode

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>777</code></dd>
  <dt>Description</dt>
  <dd>If Masa CMS is installed on a *nix type sytem the default file permissions are configured with this option</dd>
</dl>

#### defaultlocale

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Configure a default locale.</dd>
</dl>

#### defaultthemeurl

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>https://github.com/MasaCMS/MasaBootstrap5/archive/main.zip</code></dd>
  <dt>Description</dt>
  <dd>When Masa CMS is stared for the first time, no Masa Theme is present and a Default Theme is downloaded. Currently this is the Masa Bootstrap 5 Theme.</dd>
</dl>

#### editablecomments
<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>empty</code></dd>
  <dt>Description</dt>
  <dd>Setting whether a comment can be edited after it has been created.</dd>
</dl>

#### emailbroadcaster
<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>empty</code></dd>
  <dt>Description</dt>
  <dd>Setting whether the EmailBroadcaster can be enabled per site in Site Settings. --> Edit Settings --> Modules</dd>
</dl>

#### enabledynamiccontent

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Enable usage of script, object, applet, embed, layer, ilayer, frameset, param, meta, base, xss, marquee in content.</dd>
</dl>

#### enablemuratag

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Configure whether the content in the [m] tag is parsed. This is a global setting; you can overwrite this setting per site in the contentRenderer.cfc.</dd>
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
  <dd>A placholder for developers to store an application-wide encryption key</dd>
</dl>

#### encryptpasswords

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Configure whether to encrypt the passwords for the users in the database.</dd>
</dl>

#### errortemplate

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>/muraWRM/config/error.html</code></dd>
  <dt>Description</dt>
  <dd>When <code>debuggingenabled=false</code> then the template in this path is used to display an error in the browser</dd>
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

#### filebrowsereditlist

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>txt,html,htm,css,less,scss</code></dd>
  <dt>Description</dt>
  <dd>Configure which file extensions can be edited in the File Browser of the Masa CMS Admin.</dd>
</dl>

#### filebrowserimagelist

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>gif,jpg,jpeg,png</code></dd>
  <dt>Description</dt>
  <dd>Configure which file extensions are treated like images in the File Browser of the Masa CMS Admin</dd>
</dl>

#### filedir

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Configurable option to set where to store Masa CMS files.</dd>
</dl>


#### filestore

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>filedir</code></dd>
  <dt>Description</dt>
  <dd>Configuration where to store the files for Masa CMS. Default is 'filedir', the other option is 's3'.</dd>
</dl>

#### filestoreaccessinfo

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty</code></dd>
  <dt>Description</dt>
  <dd>Configuration string used when filestore='s3'. This is a string with all the access info for S3.</dd>
</dl>

#### filestoreendpoint

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>http://s3.amazonaws.com</code></dd>
  <dt>Description</dt>
  <dd>Configuration string used when filestore='s3'. This is a string with the endpoint for the S3 buecket to store the files.</dd>
</dl>

#### fmcaseinsensitive
New in 7.4.4
{: .label .label-orange }
{: .no_toc }

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Make the sorting of files in the FileManager case-insensitive.</dd>
</dl>

#### fmshowapplicationroot

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Configurable option whether the application root is shown in the File Manager</dd>
</dl>

#### fmshowsitefiles

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Configurable option whether the site files are shown in the File Manager</dd>
</dl>

#### fmallowedextensions

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>a long list of extensions</code></dd>
  <dt>Description</dt>
  <dd>Comma seperated list of file extensions that are valid to upload using the FileManager in the Masa CMS Admin.</dd>
</dl>


#### fmpublicallowedextensions

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>also a long list of extensions</code></dd>
  <dt>Description</dt>
  <dd>Comma seperated list of file extensions that are valid to upload in the public front-end of Masa CMS, like in a Form.</dd>
</dl>

#### forceadminssl

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Force Masa CMS Admin to use <code>https://</code></dd>
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
  <dd>Configurable option whether an URL in Masa CMS had hashed directory names in it.</dd>
</dl>

#### haslockablenodes

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Configurable option to lock a content node when it is being edited; e.g. only one content manager at the time can edit one specific content item.</dd>
</dl>

#### hstsmaxage

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>1200</code></dd>
  <dt>Description</dt>
  <dd>HTTP Strict Transport Security setting</dd>
</dl>

#### htmleditortype

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty</code></dd>
  <dt>Description</dt>
  <dd>Default is empty. Other two options are 'none' and 'fckeditor'.</dd>
</dl>

#### imageinterpolation

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>highQuality</code></dd>
  <dt>Description</dt>
  <dd>Specify which algoritms is used to resize the images in Masa CMS. Valid options are: highestQuality, highQuality, mediumQuality, highestPerformance, highPerformance, mediumPerformance, nearest, bilinear, bicubic, bessel, blackman, hamming, hanning, hermite, lanczos, mitchell, quadratic.
  </dd>
</dl>

#### imagequality

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>.95</code></dd>
  <dt>Description</dt>
  <dd>Setting for the quality of the images uploaded in Masa CMS. Value between 0 and 1. </dd>
</dl>

#### indexfile

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty</code></dd>
  <dt>Description</dt>
  <dd>Setting for which index file to use with Masa CMS. </dd>
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

#### javaenabled

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Configure if Java is enabled in the current Masa Instance. Needed for loading Java Libraries</dd>
</dl>

#### javasettingsloadcoldfusionclasspath

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Application.cfc variable</dd>
</dl>

#### javasettingsloadpaths

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>/requirements/lib</code></dd>
  <dt>Description</dt>
  <dd>Application.cfc variable</dd>
</dl>

#### javasettingswatchextensions

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>jar,class</code></dd>
  <dt>Description</dt>
  <dd>Application.cfc variable</dd>
</dl>

#### javasettingswatchinterval

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>60</code></dd>
  <dt>Description</dt>
  <dd>Application.cfc variable</dd>
</dl>

#### locale

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>server</code></dd>
  <dt>Description</dt>
  <dd>Used for rendering dates and times. Two valid optons: server and client</dd>
</dl>


#### lockablenodes

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Setting whether the Allow Content Locking can be enabled per site in Site Settings.</dd>
</dl>

#### loginstrikes

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>4</code></dd>
  <dt>Description</dt>
  <dd>Number of login attempts a user has before being locked out</dd>
</dl>

#### mailserverip

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>SMTP server IP</dd>
</dl>

#### mailserverpassword

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>SMTP Server password</dd>
</dl>

#### mailserverpopport

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>110</code></dd>
  <dt>Description</dt>
  <dd>SMTP Server POP port</dd>
</dl>

#### mailserversmtpport

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>25</code></dd>
  <dt>Description</dt>
  <dd>SMTP Server port</dd>
</dl>

#### mailserverssl

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Whether to use SSL or not when connecting to the SMTP server</dd>
</dl>

#### mailservertls

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Whether to use TLS or not when connecting to the SMTP server</dd>
</dl>

#### mailserverusername

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Username for the SMTP Server</dd>
</dl>

#### mailserverusernameemail

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Email address for the username for the SMTP Server</dd>
</dl>

#### managelinks
<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>When moving links in Masa CMS then references to this link are automatically updated.</dd>
</dl>

#### managesessioncookies
<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Allows that sessions are managed through an Id set in the cookie of the brower.</dd>
</dl>


#### maxarchivedversions

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>50</code></dd>
  <dt>Description</dt>
  <dd>Configurable option of how many versions of a content item to store.</dd>
</dl>

#### maxportalitems

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>1000</code></dd>
  <dt>Description</dt>
  <dd>The maximum number of items to use for pagination in Folder display</dd>
</dl>

#### maxsourceimagewidth

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>4000</code></dd>
  <dt>Description</dt>
  <dd>The maxium width of uploaded images that Masa CMS tries to store. Anything beyond this size will be resized.</dd>
</dl>

#### mfa

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Legacy: not a production feature. Multi factor authentication</dd>
</dl>

#### mfaperdevice

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Legacy: not a production feature. Multi factor authentication</dd>
</dl>

#### mfasendauthcode

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Legacy: not a production feature. Multi factor authentication</dd>
</dl>

#### mysqlengine
<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>InnoDB</code></dd>
  <dt>Description</dt>
  <dd>Set which MySQL Engine to use when dbtype='MySQL'</dd>
</dl>

#### notifywithversionlink

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Send a notification with a link for review. Either with a link to the version history page or to the version edit form.</dd>
</dl>

#### ormautomanagesession

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>CFML ORM setting</dd>
</dl>

#### ormcfclocation

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>CFML ORM setting</dd>
</dl>

#### ormdatasource

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>CFML ORM setting</dd>
</dl>

#### ormdbcreate

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>update</code></dd>
  <dt>Description</dt>
  <dd>CFML ORM setting</dd>
</dl>

#### ormenabled

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>CFML ORM setting</dd>
</dl>

#### ormeventhandling

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>CFML ORM setting</dd>
</dl>

#### ormflushatrequestend

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>CFML ORM setting</dd>
</dl>

#### ormsavemapping

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>CFML ORM setting</dd>
</dl>

#### ormskipcfcwitherror

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>CFML ORM setting</dd>
</dl>

#### ormusedbformapping

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>CFML ORM setting</dd>
</dl>

#### ping

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Controles whether Masa CMS attempts to create Scheduled Tasks voor scheduled content, scheduled notifications, etc. Not all CFML servers allow Scheduled Tasks to be created programmatically.</dd>
</dl>

#### plugindir

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Configurable option to tell Masa CMS where the plugin directory is.</dd>
</dl>

#### port

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>${cgi.SERVER\_PORT</code></dd>
  <dt>Description</dt>
  <dd>HTTP Port that Masa CMS runs on</dd>
</dl>

#### postbundles

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Display a warning about 'posting' site bundles via direct upload, rather then placeing them on the webserver and then importing them.</dd>
</dl>

#### productionassetdir

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>-</dd>
</dl>

#### productionassetpath

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>-</dd>
</dl>

#### productiondatasource

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>-</dd>
</dl>

#### productionfiledir

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>-</dd>
</dl>

#### productionwebroot

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>-</dd>
</dl>


#### proxypassword

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Settings for setting up a proxy</dd>
</dl>

#### proxyport

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>${cgi.SERVER\_PORT</code></dd>
  <dt>Description</dt>
  <dd>Settings for setting up a proxy</dd>
</dl>

#### proxyserver

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Settings for setting up a proxy</dd>
</dl>

#### proxyauthtype

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Settings for setting up a proxy. Can be empty or 'NTLM'</dd>
</dl>

#### proxyuser

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Settings for setting up a proxy</dd>
</dl>

#### purgedrafts

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Configurable option whether to remove all drafts if a new active version is published</dd>
</dl>


#### razuna

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Enable the usage of Razuna in Masa CMS. Disabled by default.</dd>
</dl>

#### readonlydatasource

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Set a readonly datasource</dd>
</dl>

#### readonlydbpassword

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Set a password for the readonly database</dd>
</dl>


#### readonlydbusername

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Set a username for the readonly database</dd>
</dl>

#### recaptchasitekey

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Site Key for Google reCAPTCHA. Used when Site Settings are empty.</dd>
</dl>

#### recaptchasecret

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Secret for Google reCAPTCHA. Used when Site Settings are empty.</dd>
</dl>

#### recaptchalanguage

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>en</code></dd>
  <dt>Description</dt>
  <dd>Language setting for Google reCAPTCHA. Used when Site Settings are empty.</dd>
</dl>

#### remoteipheader

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty</code></dd>
  <dt>Description</dt>
  <dd>Set the remote IP header</dd>
</dl>

#### rendermuraalerts

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Configurable option whether to display alerts in the Masa CMS Admin</dd>
</dl>

#### requesttimeout

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>1000</code></dd>
  <dt>Description</dt>
  <dd>Application.cfc variable</dd>
</dl>

#### sameformfieldsasarray

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Application.cfc variable</dd>
</dl>

#### scriptprotect

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Application.cfc variable</dd>
</dl>

#### scriptprotectexceptions

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>body,source,params</code></dd>
  <dt>Description</dt>
  <dd>Comma seperated list of field to ignore for scriptprotection</dd>
</dl>

#### securecookies

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Application.cfc variable</dd>
</dl>

#### sessioncookiesexpires

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>never</code></dd>
  <dt>Description</dt>
  <dd>Application.cfc variable</dd>
</dl>

#### sendfrommailserverusername

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Configurable option whether to send email via the username in the <code>mailserverusername</code> setting</dd>
</dl>

#### sendloginbcc

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Send a BCC mail when a user requests a login link.</dd>
</dl>

#### serverport

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>emtpy</code></dd>
  <dt>Description</dt>
  <dd>Set the serverport for Masa CMS.</dd>
</dl>


#### sharableremotesessions

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Enable or disable shareable remote sessions</dd>
</dl>

#### sessionhistory

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>0</code></dd>
  <dt>Description</dt>
  <dd>Number of days to store sessionhistory</dd>
</dl>

#### sessiontimeout

<dl>
  <dt>Type</dt>
  <dd>integer</dd>
  <dt>Default</dt>
  <dd><code>180</code></dd>
  <dt>Description</dt>
  <dd>Application.cfc variable</dd>
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

#### sitedir

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>sites</code></dd>
  <dt>Description</dt>
  <dd>Directory in which the sites are created. The default is 'sites'</dd>
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
  <dd>Configurable option whether a user has the permission to sort content. Two valid options: editor,author</dd>
</dl>


#### strictextendeddata

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Check the datatype and value for when submitting extended data. (e.g. like in an extended attribute)</dd>
</dl>

#### strictfactory

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Masa CMS uses the DI/1 Framework. This controls the <code>strict</code> setting for this framework.</dd>
</dl>

#### stricthtml

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Configurable option whether to allow HTML syntax in class extension attributes. Works together with the setting <code>stricthtmlexclude</code></dd>
</dl>

#### stricthtmlexclude

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>List of excluded extended attributes that allow HTML Syntax. Does not apply when type is set to HTMLEditor of the extended attribute.</dd>
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


#### stub

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>emtpy</code></dd>
  <dt>Description</dt>
  <dd>Set the stub in Masa CMS</dd>
</dl>

#### tempdir

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Configurable option for location where uploaded files are temporarely stored</dd>
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

#### tracksessioninnewthread

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Use a new thread when using session tracking. Can be disabled for performance reasons / locking issues.</dd>
</dl>


#### urltitledelim

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>-</code></dd>
  <dt>Description</dt>
  <dd>Delimeter used in creating the title for each page.</dd>
</dl>

#### usedefaultsmtpserver

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>true</code></dd>
  <dt>Description</dt>
  <dd>Configurable option whether to use the SMTP Settings in de CFML / Lucee Administrator or the SMTP Settings in Masa CMS</dd>
</dl>

#### usefilemode

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Configurable option whether to let Masa CMS set file permissions. Only applies to *nix based systems</dd>
</dl>


#### uselegacysessions

<dl>
  <dt>Type</dt>
  <dd>boolean</dd>
  <dt>Default</dt>
  <dd><code>false</code></dd>
  <dt>Description</dt>
  <dd>Configurable option whether to use legacy sessions or not.</dd>
</dl>

#### windowdocumentdomain

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Configurable option to set the <code>document.domain</code> for the Masa CMS Admin.  Useful for cross-domain issues.</dd>
</dl>

#### wordfilter
New in 7.4.4
{: .label .label-orange }
{: .no_toc }

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty string</code></dd>
  <dt>Description</dt>
  <dd>Customize the scriptProtectionFilter.</dd>
</dl>

#### version

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>The number of the version in use.</code></dd>
  <dt>Description</dt>
  <dd>Version number</dd>
</dl>

#### webroot

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>empty</code></dd>
  <dt>Description</dt>
  <dd>Configures the webroot</dd>
</dl>

#### webrootmap

<dl>
  <dt>Type</dt>
  <dd>string</dd>
  <dt>Default</dt>
  <dd><code>muraWRM</code></dd>
  <dt>Description</dt>
  <dd>Used for old Coldfusion MX 7 mapping. Do not use.</dd>
</dl>