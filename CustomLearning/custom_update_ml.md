---
author: pkrebs
ms.author: pkrebs
title:  Update learning pathways for multilingual support
ms.date: 05/20/2019
description: Update learning pathways for multilingual support
ROBOTS: NOINDEX, NOFOLLOW
---
# Update learning pathways for multilingual support
If you have an existing Learning Pathways site, you can update it for multilingual support. To update learning pathways to the multilingual 4.0 version, you upload the web part package, customlearning.sppkg, to the SharePoint tenant App Catalog. When you update learning pathways:  

- Any previously created custom playlists and assets are maintained
- Settings to hide or show content are maintained
- The learning pathways SharePoint template is left unchanged
- The learning pathways site pages aren't translated. This work must be done manually

## Read the learning pathways multilingual overview
To learn about how multilingual support works for learning pathways, read the [Learning pathways multilingual overview](custom_overview_ml.md)). 

## Prerequisites to update
Before updating learning pathways, the following prerequisite must be met:
- The person updating learning pathways must be a site collection owner of the tenant App Catalog. If the person provisioning learning pathways isn't a site collection owner of the App Catalog, [complete these instructions](addappadmin.md) and continue. 

## Set language settings 
Before updating learning pathways, set the site language settings. To enable multilingual support for the learning pathways site, you can set the **Enable pages and news to be translated into multiple languages** to **On**, and then add the languages you want to support for the site.
1.	From the Learning Pathways site, select **Settings** from the top right, and then select **Site information**.
2.	At the bottom of the site information pane, select **View all site settings**.
3.	Under **Site Administration**, select **Language settings**.
4.	Under **Enable pages and news to be translated into multiple languages**, set the toggle switch. 
- For a multiligual site, slide the toggle to **On**, and then proceed to the Add Languages section. 
- For an English-only site, slide the toggle to **Off**.

### Add languages
Learning pathways supports nine languages, you should add only the languages you need. In the examples used in this documentation, Italian will be added. 
- Under **Add or remove site languages**, start typing a language name in **Select or type a language**, or choose a language from the dropdown. You can repeat this step to add multiple languages. You can add or remove languages from your site at any time by going back to this page.
 
### Assign translators
When defining Language settings for learning pathways, you can assign translators. Translators should have a foreign language profile set up. For more information about foreign language profiles, see [Create multilingual communication sites, pages, and news](https://support.office.com/article/2bb7d610-5453-41c6-a0e8-6f40b3ed750c).  
- For a supported language, click **Select or type a translator** and then select a translator. 

## Update the learning pathways web part package
In this step, you upload the learning pathways 4.0 web part to the SharePoint App Catalog, and then navigate to the learning pathways Administration page to start the update process.

### Upload the web part package
1.	Go to the multilingual share location in Teams and download **customlearning.sppkg** to a local drive on your PC. 
2.	If you’re not already signed in, sign into your tenant with a Tenant Admin or Site Collection Admin account. 
3.	Click **Admin** > **Show All** > **SharePoint** > **More Features**. 
4.	Under **Apps**, click **Open**. 
5.	Click **App Catalog** > **Distribute Apps for SharePoint**. 
6.	Click **Upload** > **Choose Files**. 
7.	Select the **customlearning.sppkg** file you downloaded, click **OK** > **Deploy**. 

### Complete the update
1.	From the Learning Pathways site, select **Learning pathways administration** from the **Home** menu. 
2.	You’ll see a prompt asking if you want to update. 
![custom_update_adminprompt_ml.png](media/custom_update_adminprompt_ml.png)
3.	Click **Start**. 
4. When the update is complete, click **Close**. 

### Next Steps
- Explore the [default content](custom_exploresite.md) provided in the site and web part.
- For more information about translating site pages, see [Translate site pages](custom_translate_page_ml.md). 

