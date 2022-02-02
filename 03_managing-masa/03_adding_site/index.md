---
layout: default
title: Adding a New Site
nav_order: 3
parent: Managing Masa CMS
last_modified_date: 20-10-2021 13:00
permalink: /managing-masa/adding-site/
---
# Adding a New Site

Follow the next steps to add an new Masa CMS webiste.

1. Go to the Masa CMS Admin, then go to **Global Settings** from the left menu, and choose **Add New Site**.

    ![](/assets/03_managing-masa/03_adding_site/adding_site_1.png)

2. Now a form is displayed; **"Site ID"** is the only mandatory field. The Site ID will be created as a directory in the Masa {context}.
Best practice is to keep it simple and create a siteID which isn't too long or complex.
    
    ![](/assets/03_managing-masa/03_adding_site/adding_site_2.png)

3. It's good practice to also fill in the fields **"Site Name"** and **"Primary Domain"** so that the site has a label and a domain is linked to the site.

    ![](/assets/03_managing-masa/03_adding_site/adding_site_3.png)

4. Click the **Add** button. All the directories and files in `{context}/default/` are copied into the new directory (again, named after the Site ID).

    ![](/assets/03_managing-masa/03_adding_site/adding_site_4.png)

5. Under **Global Settings** you can now see your newly created site!

    ![](/assets/03_managing-masa/03_adding_site/adding_site_5.png)
