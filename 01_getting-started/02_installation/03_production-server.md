---
layout: default
title: Production/Server
nav_order: 3
grand_parent: Getting started
parent: Installation
last_modified_date: 20-10-2021 13:00
permalink: /getting-started/installation/production-server/
---

# Production/Server

## Requirements
- Must have ColdFusion 10+, Lucee 4.5.1.000+, installed
- Access to a MySQL 5+, PostgreSQL 8+, Microsoft SQL 2000+ or Oracle 10g+ database server and the ability to add a new database
- Ability to add a Datasource (DSN) to ColdFusion/Lucee administrator

## Installation
Installing Masa CMS couldn't be easier. Follow the instructions below and you'll be up and running in minutes.

1. Create an empty database (e.g., dbMasaCMS).

2. Copy the contents of the Masa CMS .zip file into your webroot (the directory where your site will live).

{: .warning}
NOTE: Do NOT place the files into a directory named "mura" since this is already used as a ColdFusion mapping and may cause issues.

3. Go to the ColdFusion or Lucee Administrator, and create a Datasource (DSN) connecting to the database you created in the step above (e.g., dsnMasaCMS). While creating the DSN, also complete the following under Advanced Settings:
  1. Enable CLOB (enable long text retrieval)
  2. Under Allowed SQL, at a minimum, enable "SELECT, CREATE, INSERT, DROP, UPDATE, ALTER, DELETE."

4. Browse to the url where your Masa CMS site is installed and complete the form using the information created above.

5. Once you've successfully set up Masa CMS, click the "Finish Set Up and Take Me to the Masa CMS Admin" button. Keep in mind that once you do this, the Masa CMS Set Up page will no longer be available (for security reasons). If you need to change any settings in the future, they will need to be made directly in  the "/config/settings.ini.cfm" file.

6. Login to the Masa CMS admin using the username and password chosen in the Masa CMS Set Up page. It is highly recommended you utilize a complex password.

7. If you would like to send scheduled emails or have scheduled content publishing when caching is turned on (caching is highly recommended for increased performance) you must change the "Ping" attribute in the \config\setting.ini.cfm to 1. On start up, Masa CMS will attempt to create a scheduled task to check for event reminders, scheduled emails and to flush its cache for scheduled content.

{: .warning}
NOTE: Enabling this scheduled task may cause performance problems in some shared hosting environments.      

8. You're done installing Masa CMS. Enjoy!