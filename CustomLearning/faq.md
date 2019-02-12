---
author: karuanag
ms.author: karuanag
title:  Frequently Asked Questions for Custom Learning for Office 365 solutions
ms.date: 02/10/2019
description: Frequently asked questions information for Custom Learning for Office 365 
---

# Frequently Asked Questions

### 1. What are the requirements for installing Custom Learning for Office 365 into my tenant environment?

- SharePoint Online and Communication Sites enabled.
- The individual that will be provisioning CLO365 must be the tenant administrator of the target tenant for install.
- A tenant 'App Catalog' must be available within the 'Apps' option of the SharePoint Admin Center.
- The individual that will be provisioning CLO365 must be a site collection administrator of the app catalog in the target tenant for install.

### 2. What languages is Custom Learning for Office 365 available in?

Custom Learning for Office 365 is currently available only in English. Automatic end-to-end provisioning only works with English tenants. Additional languages may be added at in future releases.

### 3. How long will it take to install the site in our tenant environment?

Based on our testing of the installation, it should take less than 15 minutes. This does not include time required to customize the site to your requirements.

### 4. Can we make the Custom learning for Office 365 a subsite of our primary SharePoint site collection?

No. The site is based on a communication site template, which is always meant to be a root site collection.

> [!NOTE]
> It is important to consider the permissions your end users will need to access the site. Most organizations have defined security or user groups. You must add the appropriate security groups to your new training portal once you are ready to launch it to your employee community.

### 5. I need to reinstall the site; what should I do?

Follow the installation instructions published [here](installsitepackage.md).

> [!NOTE]
> If you had disabled telemetry in your prior installation and would like to continue with telemetry disabled, you will need to follow the instructions for disabling the telemetry here.

### 6. We made updates to our implementation of Custom Learning for Office 365. Will we lose these updates (made to site template, playlists) if we reinstall the site?

Customizations to individual pages and custom playlists will be lost if you reinstall the site over your current installation.  