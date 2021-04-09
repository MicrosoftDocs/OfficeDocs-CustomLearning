---
author: karuanag
ms.author: karuanag
title: Frequently Asked Questions for Microsoft 365 learning pathways
ms.date: 02/10/2019
description: Frequently asked questions information for Microsoft 365 learning pathways 
ms.service: sharepoint-online
---

# Frequently Asked Questions

### I recently saw a blog post that Custom Learning for Office 365 is being renamed to Microsoft 365 learning pathways. Are there other changes being added to the solution as part of the renaming effort? Should I update the solution in my organization?

The Microsoft 365 learning pathways release is a rebranding effort dedicated to changing the name of the solution to align with Microsoft 365 branding. If you have Custom Learning for Office 365 currently running successfully in your organization, it’s not necessary to update the solution at this time.  

### What are the requirements for installing Microsoft 365 learning pathways into my tenant environment?

- SharePoint Online and Communication Sites enabled.
- The individual that will be provisioning CLO365 must be the tenant administrator of the target tenant for install.
- A tenant 'App Catalog' must be available within the 'Apps' option of the SharePoint Admin Center.
- If a new App Catalog is created, a wait time of 30 minutes or more is required for the App Catalog to be fully provisioned. Attempting to provision Microsoft 365 learning pathways directly after creating the tenant App Catalog will result in a provisioning error of the learning pathways solution. 
- The individual that will be provisioning CLO365 must be a site collection administrator of the app catalog in the target tenant for install.

### Why is Microsoft asking for tenant permissions when installing Microsoft 365 learning pathways 

- The SharePoint Online Provisioning service uses the permissions to provision the Learning Pathways SharePoint site, create the pages of the site, and to install the Microsoft 365 learning pathways application within their tenant. That is the only reason for us requesting the permissions. Without the requested permissions the SharePoint Provision Service cannot execute the commands that automatically install the learning pathways site template and web part. 

### What are the implications of Microsoft 365 learning pathways being in a Beta Preview? 

Microsoft 365 learning pathways is currently in Beta Preview. Please consider the following as you evaluate, plan and implement Microsoft 365 learning pathways:

- As with any Beta solution our service management team reserves the right to make changes to the service and its components. As we are actively resolving bugs and UX issues you would likely need to update the WebPart.
- To update the web part you will need to download it from our GitHub repository and upload it into your tenant app catalog. Please see the "Updating the solution" section of the Microsoft 365 learning pathways [Readme](https://github.com/pnp/custom-learning-office-365/blob/master/README.md) file. 

### What languages is Microsoft 365 learning pathways available in?

Microsoft 365 learning pathways is currently available only in English. Automatic end-to-end provisioning only works with English tenants. We plan on rolling out multilingual support for the following languages in the second quarter of 2020. 

- Chinese (Simplified) 
- French  
- German 
- Italian (Italy) 
- Japanese (Japan)  
- Portuguese (Brazilian) 
- Russian (Russian)  
- Spanish 

> Support for the Dutch language will not be included in the upcoming release of multi-language support for learning pathways. We will continue to evaluate new language options in the future.

### How long will it take to install the site in our tenant environment?

Based on our testing of the installation, it should take less than 15 minutes. This does not include time required to customize the site to your requirements.

### Is Microsoft 365 learning pathways an open source solution and what are the implications?

Microsoft 365 learning pathways is an Open Source Software (OSS) solution and as such carries a set of benefits and considerations germane to OSS:

#### Benefits 
- **Microsoft 365 learning pathways is a free solution:** Customers can install the solution in their tenant, customize it and make it available to end users
- **OSS enables rapid development and collaboration:**  All open source solutions are available to a broad community of contributors.  Microsoft is committed to this method of driving innovation.  To ensure we are delivering an experience that benefits the widest set of our customers our core service management team will reserve the right to determine what contributions are merged into our official build.  
- **OSS enables collaboration with partners:** Microsoft is working with several learning partners to support their efforts for future extensions and contributions to Microsoft 365 learning pathways. We will provide more information as these plans become finalized. 
	
#### Implications
- **OSS is not a commercially available product:** Commercial products include updating and patching and are included in fee-based support contracts. While Microsoft currently offers documentation, updating and patching for Microsoft 365 learning pathways it is based on our commitment to improving this particular business scenario. Our plans are to continue investing in learning pathways, but customers should be aware that our service management team may change strategies in the future. Any future changes to Microsoft 365 learning pathways will be communicated in advance of taking effect. 
- **As OSS, Microsoft 365 learning pathways is supported through an online issues list on GitHub**: Microsoft 365 learning pathways is not covered by any existing Microsoft support contract. Submitted issues are triaged by Microsoft 365 learning pathways service owners and the community. Issue resolution service levels are NOT at the same level as a paid Microsoft support contract.  

### Can we make the Microsoft 365 learning pathways a subsite of our primary SharePoint site collection?

No. The site is based on a communication site template, which is always meant to be a root site collection.

> [!NOTE]
> It is important to consider the permissions your end users will need to access the site. Most organizations have defined security or user groups. You must add the appropriate security groups to your new training portal once you are ready to launch it to your employee community.

### I need to reinstall the site; what should I do?

Follow the installation instructions published [here](custom_provision.md).

> [!NOTE]
> If you had disabled telemetry in your prior installation and would like to continue with telemetry disabled, you will need to follow the instructions for disabling the telemetry here.

### We made updates to our implementation of Microsoft 365 learning pathways. Will we lose these updates (made to site template, playlists) if we reinstall the site?

Customizations to individual pages and custom playlists will be lost if you reinstall the site over your current installation.  