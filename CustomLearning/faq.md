---
author: karuanag
ms.author: karuanag
title:  Frequently Asked Questions for Microsoft 365 learning pathways
ms.date: 02/10/2019
description: Frequently asked questions information for Microsoft 365 learning pathways 
---

# Frequently Asked Questions

### What are the requirements for installing Microsoft 365 learning pathways into my tenant environment?

- SharePoint Online and Communication Sites enabled.
- The individual that will be provisioning CLO365 must be the tenant administrator of the target tenant for install.
- A tenant 'App Catalog' must be available within the 'Apps' option of the SharePoint Admin Center.
- If a new App Catalog is created, a wait time of 30 minutes or more is required for the App Catalog to be fully provisioned. Attempting to provision Microsoft 365 learning pathways directly after creating the tenant App Catalog will result in a provisioning error of the learning pathways solution. 
- The individual that will be provisioning CLO365 must be a site collection administrator of the app catalog in the target tenant for install.

### Why is Microsoft asking for tenant permissions when installing Microsoft 365 learning pathways 

- - The SharePoint Online Provisioning service uses the permissions to provision the Learning Pathways SharePoint site, create the pages of the site, and to install the Microsoft 365 learning pathways application within their tenant. That is the only reason for us requesting the permissions. Without the requested permissions the SharePoint Provision Service cannot execute the commands that automatically install the learning pathways site template and web part. 

### What languages is Microsoft 365 learning pathways available in?

Microsoft 365 learning pathways is currently available only in English. Automatic end-to-end provisioning only works with English tenants. Additional languages may be added at in future releases.

### How long will it take to install the site in our tenant environment?

Based on our testing of the installation, it should take less than 15 minutes. This does not include time required to customize the site to your requirements.

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