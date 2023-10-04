---
author: pkrebs
ms.author: bpardi
title: Set-up option for learning pathways
ms.date: 07/16/2020
description: Setup option for learning pathways
ms.service: sharepoint-online
manager: bpardi
ms.topic: article
audience: admin
---

# Configuration options for multilingual learning pathways
With the release of multilingual features for SharePoint Online communications sites, learning pathways now offers support for multiple languages. You can set up learning pathways in different kinds of ways to meet the needs of your organization. To help you decide the best path for your organization, we’ve outlined the setup options. 

## New install scenarios
The "new install scenarios" explain the options for installing a new instance of the learning pathways using the Microsoft 365 look book service. 

### Scenario 1: We have not installed learning pathways and need learning pathways multilingual support 
If you have not installed learning pathways and need it multiple languages, you can use the Microsoft 365 look book service to install a new learning pathways solution with support for nine languages. English will be the default language and cannot be changed. 
- To provision a new learning pathways solution with English as the default language for the site, see [Provision a new learning pathways solution](custom_provision.md).

### Scenario 2: We installed learning pathways but aren’t currently using it and/or haven’t made any customization to the site or playlists 
If you installed learning pathways but aren’t actively using it, or you haven’t made any customizations to the site or playlists, you can use the Microsoft 365 look book service to install a new solution with support for nine languages. English will be the default language and cannot be changed. 
- To provision a new learning pathways solution with English as the default language for the site, see [Provision a new learning pathways solution](custom_provision.md).

### Scenario 3: We haven't installed learning pathways and don’t need multilingual support 
If you have not installed learning pathways and don’t need multilingual support, you can install it from the Microsoft 365 look book service. English will be the default language. After install, you need to turn off multilingual support. 
- To provision a new learning pathways solution without multilingual support, see [Provision a new learning pathways solution](custom_provision.md).

## Update learning pathways (with a web part upload) scenarios
If you have an existing version of learning pathways installed, you can upload the learning pathways web part to the SharePoint App Catalog to enable multilingual support. 

### Scenario 1: We need to upgrade an existing version of learning pathways but don't need multilingual support
You can update learning pathways version 4.0 without multilingual support. With the update, you get a couple of new features, including an image selector for custom playlists and subcategories. 

- To update an existing learning pathways solution without multilingual support, see [Update learning pathways for multilingual support](custom_update.md). The upgrade process for no multilingual support is the same as with multilingual support, but with fewer steps. 

### Scenario 2: We need to upgrade to multilingual support and the default language of the site collection is our default language
Learning pathways version 4.O will support multilingual pages in your site collection. In addition to multilingual support, you get a couple of new features, including an image selector for custom playlists and subcategories. 
- To update an existing learning pathways site multilingual support, see [Update learning pathways for multilingual support](custom_update.md). 

## Update learning pathways for multilingual support with manual install 
The following outlines the scenarios for updating an existing instance of the learning pathways solution to the version 4.0 multilingual version by manually installing the learning pathways web part. 

### Scenario 1: We need multilingual support and the default language of the site collection is not our default language – no custom content 
Learning pathways version 4.0 will support this scenario. However, this scenario assumes you don’t have custom content or playlists on the existing site. For this scenario, you can create a new SharePoint Online communication site with your default language, upload the web part, then manually set up learning pathways with a PowerShell Script. 
- To set up learning pathways for multilingual support with your default language, see [Manual Install of Learning Pathways for multilingual support](custom_manualsetup.md).

### Scenario 2: We need multilingual support and the default language of the site collection is not our default language – plus we have custom content 
For this scenario, you can create a new SharePoint Online communication site with your default language, upload the web part, then manually set up learning pathways with a PowerShell Script. 

After you reestablish your learning pathways site by following the steps above, you will need to move the contents of your **CustomPlaylists** list and your **CustomAssets** list. You can also, optionally, move the actual custom pages that make up your custom assets if they live in the existing learning pathways site, and your intent is to delete it. The task can be difficult because  for all the items in the **CustomPlaylists** list, the ID of the list item in the **CustomAssets** list is buried in the JSONData field of each playlist list item. Therefore, simply moving the contents of the **CustomPlaylists** list from one site to the other will not be sufficient. Further, the **CustomAssets** list contains the absolute URL to the custom asset's page in the JSONData field of the list item. If the assets aren't moved and the site isn't renamed (thus changing the absolute URL to the asset's page), then **CustomAssets** can remain. But you will need to manually correct the entries. Given the complexity of this type of migration we suggest you consider enlisting one of our learning pathways partners to assist you in making this transition.
- To set up learning pathways for multilingual support with your default language, see [Manual Install of Learning Pathways for multilingual support](custom_manualsetup.md).