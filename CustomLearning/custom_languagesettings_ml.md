---
author: pkrebs
ms.author: pkrebs
title:  Change language settings for learning pathways
ms.date: 02/10/2019
description:  Change language settings for learning pathways
---

# Change language settings for learning pathways

When you provision the learning pathways solution:
- the learning pathways SharePoint template is provisioned to your tenant. The template pages are translated into 9 languages, including English, which is the default language. 
- The Microsoft 365 learning pathways web part package is installed in the tenant app catalog.  
- The learning pathways web part is added to several learning pathways SharePoint template pages as part of the provisioning process. The web part will appear in the language of the user's profile language. 

## Language settings recommendations
The SharePoint Site Language settings let you determine the languages to support for the Learning Pathways site. The following recommendations apply:   

- Turn off the languages you don’t want to support for the site. This applies to organizations that only support one language, in additon to the default English language.
- If you are not supporting a multilingual site, turn of the multi-lingual feature completely. 

### To remove languages

1.	From the learning pathways site, select the SharePoint **Settings** icon at the top right of the site, and then select **Site information**.
2.	At the bottom of the site information pane, select **View all site settings**.
3.	Under **Site Administration**, select **Language settings**.
4.	Under **Enable pages and news to be translated into multiple languages**, slide the toggle to **On** if it's not already on.
5.	Under **Add or remove site languages**, click **Remove** to remove the languages that you don't want to support for the site. The following shows an example of the Language Settings page to show Italian supported for the site, in addition to the default English language.
<image goes here..>
 
### To turn off the multilanguage feature for the site
1. Follow Steps 1-3 above
2. Under **Enable pages and news to be translated into multiple languages**, slide the toggle to **Off**.  

### Assign a translator
- If you're going to translate pages, optionally assign one or more translators for each language.  In the Translator column, start typing the name of a person you want to be a translator, and then select the name from the list. Note this person should have a foreign language profile set up. (See previous instructions).

Note: Anyone in your organization's Active Directory can be assigned as a translator. People assigned as translators will not automatically be given appropriate permissions. When someone without edit permissions to a site tries to access the site, they will be directed to a web page where they can request access.

 
### Next Steps
- Explore the [default content](custom_exploresite.md) provided in the site and web part.
