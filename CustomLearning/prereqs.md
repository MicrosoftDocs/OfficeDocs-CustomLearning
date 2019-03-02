---
author: karuanag
ms.author: karuanag
title:  Prerequisites for Installation
ms.date: 02/11/2019
description: Decisions and pre-requisite information for Custom Learning installation and setup 
---

# Getting Started

Custom Learning for Office 365 provides the flexibility to set up the solution in a couple different ways. The following sections outline the options available.

## Provision with the PnP Provisioning Service - Recommended
The PnP Provisioning Service provides the fastest, easiest, and recommended method for setting up Custom Learning. With the PnP Provisioning Service, an Office 365 tenant admin signs into the site, makes a few choices, and clicks **Add to Tenant** to provision the SharePoint Online Custom Learning Site, and the Custom Learning Web part. When its done, the Tenant Admin receives an email that the site is ready to go. To get started, go here.    

    Custom Learning for Office 365 provides a complete training solution for your organization, including a SharePoint communication site and a Custom Learning web part that delivers up-to-date content from a Microsoft online catalog. Custom Learning can be easily provisioned from the SharePoint Online Provisioning Service. Before provisioning Custom Learning, it's important to review the pre-requisites and decide on your best options for provisioning Custom Learning in your organization.

The following instructions outline how to provision Custom Learning for Office 365 (CLO365), including the installation of the CLO365 communication site template and the Custom Learning web part, into your tenant environment. These instructions cover the installation of CLO365 via the SharePoint Online Provisioning Service at https://provisioning.sharepointpnp.com    If you are interested in installing just the Custom Learning web part for use on an existing SharePoint Online communication site, see [installing the custom webpart](installwebpart.md). 

## Prerequisites
 
To successfully install CLO365 via the [SharePoint Online Provisioning Service](https://provisioning.sharepointpnp.com) you must meet the following pre-requisites: 
 
- The individual provisioning Custom Learning must be the Tenant Administrator of the tenant where Custom Learning will be installed.  
- A tenant App Catalog must be available within the Apps option of the SharePoint Admin Center. If you do not have an App catalog,refer to the [SharePoint Online documentation](https://docs.microsoft.com/en-us/sharepoint/use-app-catalog) to provision this feature.  
- The individual provisioning Custom Learning must be a Site Collection Owner of the App Catalog in the target tenant for install. If the person provisioning Custom Learning is not a Site Collection Owner of the App Catalog [complete these instructions](addappadmin.md) and continue.  

### Next Steps - [Service Decisions](servicedecisions.md)
