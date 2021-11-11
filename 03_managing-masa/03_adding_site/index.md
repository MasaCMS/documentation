---
layout: default
title: How to Add a New Site
nav_order: 3
parent: Managing Masa CMS
last_modified_date: 20-10-2021 13:00
permalink: /managing-masa/adding-site/
---
# How to Add a New Site

Masa can host multiple websites under a single installation. This makes it easy to host both a public-facing website, and a company-facing intranet, and/or additional web properties owned and managed by your organization.

To add a new Masa site, follow the instructions below.

1. From the back-end administration area of Masa, select **Global Settings** from the main navigation, and click **Add New Site**.

    ![](/assets/03_managing-masa/03_adding_site/adding_site_1.png)

2. The only required form field is the **"Site ID"** field. Please keep in mind the text you enter here will become the directory name under Masa's {context}, and as such, you should not use any spaces, punctuation, dots, or file delimiters here.

3. At a minimum, you'll probably also want to enter a **"Site Name"** and **"Primary Domain"** in order to identify, and access the site.

4. Remember, when adding a new site, all directories and files located under `{context}/default/` will be copied and placed into the new SiteID directory.

5. Additional information about adding a new site can be found in the Installation and Setup Guide (coming soon).

6. When you're finished, click the **Add** button, to create your new site.

7. You should now see your new site in the listing of sites on the **Global Settings** screen.