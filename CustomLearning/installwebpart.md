---
author: pkrebs
ms.author: pkrebs
title:  Stand alone web part setup
ms.date: 02/10/2019
description: Custom Learning for Office 365 stand alone web part setup
---
# Stand alone web part setup

Custom Learning offers a stand alone web part setup for those organizations that already have an established SharePoint Online modern communication site dedicated to training, or that just want to set up the Custom Learning web part in their own communication site. Note that the stand alone setup requires experience working with Windows PowerShell and the SharePoint Online Management Shell. 

> [!NOTE]
> If you are looking for a fast, easy way to set up Custom Learning, see [Provision Custom Learning](installsitepackage.md).

## Prerequisites
To ensure a successful stand alone setup of the Custom Learning web part, the follow prerequisites must be met. 

- The person setting up the Custom Learning web part must be a Tenant Administrator, also known as a Office 365 Global Administrator, of the tenant where Custom Learning will be provisioned.  
- A tenant App Catalog must be available within the Apps option of the SharePoint Admin Center. If your organization does not have an SharePoint tenant App catalog, refer to the [SharePoint Online documentation](https://docs.microsoft.com/en-us/sharepoint/use-app-catalog) to create one.  
- The person provisioning Custom Learning must be a Site Collection Owner of the Tenant App Catalog. If the person provisioning Custom Learning is not a Site Collection Owner of the App Catalog [complete these instructions](addappadmin.md) and continue. 
-  The person handling the web part set up needs to have experience working with Windows PowerShell and the SharePoint Online Management Shell. 

## Step 1 - Get the web part package and setup script from GitHub
As part of the setup process, you'll need the Custom Learning Web part package and the PowerShell Setup Script.

- Go the the [Custom Learning GitHub Repository](https://github.com/pnp/custom-learning-office-365).
- Click **Download** to save the web part package and script to a local drive. You'll be using the script and the web part package in later steps of this process.

## Step 2 - Verify if you have an App Catalog for your site
Before you go through the process of creating an App Catalog for your site, verify that one doesn't already exist. 
1. From the site where you'll add the web part, click the Settings menu, and then click **Site Contents**.
2. Under **Content**, look for **Apps for SharePoint**. This is your App Catalog. 
3. If you have verified that an App Catalog exists, skip to Step 4. If one doesn't exist, go to the following Step 3 - Create an App Catalog.

## Step 3 - Create an App Catalog
In this step, you create a Site Collection App Catalog. For reference, instructions for creating the App Catalog are here: [Site Collection App Catalog](https://docs.microsoft.com/en-us/sharepoint/dev/general-development/site-collection-app-catalog). But we’ve provided explicit instructions to guide you through the process. 

1.	Before you can manage site collection app catalogs in your tenant, ensure that you have installed the [SharePoint Online Management Shell](https://www.microsoft.com/en-us/download/details.aspx?id=35588) from November 2017 or newer.
2.	From the Windows Start menu, type **SharePoint Online Management Shell**.
3.	Connect to your SharePoint Online tenant using the Connect-SPOService cmdlet when using the SharePoint Online PowerShell. You’ll need to specify Admin in the URL as shown in the following syntax and replace contoso with your tenant name.

```Connect-SPOService -Url https://contoso-admin.sharepoint.com```

4.	Now you create the site collection app catalog. Use the Add-SPOSiteCollectionAppCatalog cmdlet passing the site collection where the app catalog should be created as the -Site parameter.

```$site = Get-SPOSite https://contoso.sharepoint.com/sites/CustomLearningforOffice365```

```Add-SPOSiteCollectionAppCatalog -Site $site```

## Step 5 - Add the Custom Learning webpart to your tenant 

1. Go to your local drive where you downloaded the web part package and script in [Step 1 - Get the web part package and setup script from GitHub](##Step 1 - Get the web part package and setup script from GitHub).  
2. Navigate to the [Office 365 Admin portal](https://admin.microsoft.com/AdminPortal/Home#/homepage) for your tenant
3. From the left navigation select Admin Centers, SharePoint. This will open in a new tab. 
, In the SharePoint Admin Center select Apps, App Catalog, Apps for SharePoint 
4. Select upload the webpart and choose the "ms-custom-learning.sppkg" file you downloaded
5. For this tenant-wide installation check the box next to "Make this solution available to all sits in the organization."  

## Step 5 - Run the Powershell script
- With Windows Powershell, run the you downloaded in Step 1.CustomLearningConfig.ps1 script.
 



After Custom Learning is installed in your tenant you can add the Web part to a SharePoint page. When you do Office 365 and Windows 10 training is available to your site.

1. Add the Custom Learning webpart in a full width column layout:

![SharePoint Page Layout](media/clo365fullcolumnwidth.png)

2. In the SharePoint page, select Add section and then select full width column.  You'll see the following prompt:

![AddWebpart](media/clo365addfullwidthwebpart.png)

3. Select Microsoft Learning.  You should now see the following: 

![Custom Learning webpart](media/clo365addwebpart.png)

 You can now click on the tiles to explore the default content included in the solution.  

 Along with the SharePoint site, the provisioning service also installs a Custom Learning Web part. Connected to an online catalog of Microsoft content, the Custom Learning Web part can be dropped on any SharePoint page and configured to support  

![Custom Learning for Office 365 site experience](media/clo365homepage.png)

**Option 2**: [The Custom Learning for Office 365 web part ](installwebpart.md)
The Custom Learning web part option is designed for organizations that want to integrate Office 365 training into an existing SharePoint Online communication site. The Custom Learning web part can be installed on any SharePoint Online page and provides an up-to-date feed of the full suite of Office 365 training content from Microsoft's Support.Office.com site. Training content delivered through the web part is organized in easy-to-consume playlists. Administrators can also use the web part to build custom training playlists, combining content from YouTube, locally hosted content like .PDFs, and Office 365 training content, to provide training experiences tailored to the unique needs of the organization.

![Custom Learning for Office 365 webpart](media/clo365customplaylist.png)

### Next Steps
- Explore the [default content](webpartcontent.md) included in the webpart.
- [Customize](customization.md) the training experience for your organization.
- [Drive adoption](driveadoption.md) of your training solution.

