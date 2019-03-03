---
author: pkrebs
ms.author: pkrebs
title:  Stand alone web part setup
ms.date: 02/10/2019
description: Custom Learning for Office 365 manual web part setup
---
# Manual web part setup

Custom Learning offers a stand alone web part setup for those organizations that already have an established SharePoint Online modern communication site dedicated to training, or that just want to set up the Custom Learning web part in their own communication site. Note that the manual setup requires experience working with Windows PowerShell and the SharePoint Online Management Shell. The steps for a manual set up of the Custom Learning Web part as as follows:

- Validate that you have met all the prerequisites.
- Install the customlearning.sppkg file in your Office 365 Tenant App Catalog.
- Provision/Identify a modern communication site to act as your Custom Learning for Office 365 home site.
- Execute a PowerShell script that will configure your tenant with the appropriate artifacts that Custom Learning depends on.
- Navigate to the CustomLearningAdmin.aspx site page to load the admin web part to initialize the custom content configuration.

> [!NOTE]
> If you are looking for a fast, easy way to set up Custom Learning, see [Provision Custom Learning](installsitepackage.md).

## Prerequisites
To ensure a successful manual setup of the Custom Learning web part, the follow prerequisites must be met. 

- You must have set up and configured the tenant-wide App Catalog. Please see [Set up your Office 365 tenant](https://docs.microsoft.com/en-us/sharepoint/dev/spfx/set-up-your-developer-tenant#create-app-catalog-site) and follow the Create app catalog site section. 
- If your tenant-wide App Catalog has already been provisioned you will need access to an account that has rights to upload a package to it to complete this setup process. Generally this is an account with the SharePoint administrator role. 
- If an account with that role does not work, go to the SharePoint admin center and find the Site Collection Administrators for the app catalog site collection and either log in as one of the Site Collection Administrators, or add the SharePoint administrator account that failed to the Site Collection Administrators. 
- You will also need access to an account that is a SharePoint Tenant Admin.

## Step 1 - Get the web part package and setup script from GitHub
As part of the setup process, you'll need the Custom Learning Web part package and the PowerShell Setup Script.

- Go the the [Custom Learning GitHub Repository](https://github.com/pnp/custom-learning-office-365).
- Click **Download** to save the web part package and script to a local drive. You'll be using the script and the web part package in later steps of this process.

## Step 2 - Upload the web part to the Tenant App Catalog
To set up Custom Learning for Office 365, you upload the customlearning.sppkg file to the tenant-wide App Catalog and deploy it. Please see [Use the App Catalog to make custom business apps available for your SharePoint Online environment](https://docs.microsoft.com/en-us/sharepoint/use-app-catalog) for detailed instructions on how to add an app to the app catalog.

## Step 3 - Provision/identify a modern communication site
Either identify an existing SharePoint communication site or provision a new one in your SharePoint Online tenant. For more information about how to provision a communication site see [Create a communication site in SharePoint Online](https://support.office.com/en-us/article/create-a-communication-site-in-sharepoint-online-7fb44b20-a72f-4d2c-9173-fc8f59ba50eb) and follow the steps to create a communication site.

## Step 4 - Set permissions for the site
Ensure the following permissions are set for the site:
- **Site Collection Administrator or part of the Owners group** - Permissions required to  initialize the CustomConfig list item that sets up custom learning for its first use. 
- **Members group** - permissons required to Administer Custom Learning, including hiding and showing content and administering custom playlists
- **Visitors group** - permissions required to view site content. 

## Step 5- Execute PowerShell Configuration Script
A PowerShell script `CustomLearningConfiguration.ps1` is included that you will need to execute to create three [tenant properties](https://docs.microsoft.com/en-us/sharepoint/dev/spfx/tenant-properties) that the solution uses. In addition the script creates two [single part app pages](https://docs.microsoft.com/en-us/sharepoint/dev/spfx/web-parts/single-part-app-pages) in the site pages library to host the admin and user web parts at a known location.

### Disabling Telemetry Collection
Part of this solution includes anonymized telemetry tracking opt in, which by default is set to on. If you are performing a manual install and you would like to turn telemetry tracking off, please change the `CustomlearningConfiguration.ps1` script to set the $optInTelemetry variable to $false.

If you are not performing a manual install and would like to turn telemetry tracking off, a seperate script `TelemetryOptOut.ps1` has been included that when run will disable telemetry tracking.

## Step 6 - Initialize web part custom configuration
After the PowerShell script is successfully run, navigate to `<YOUR-SITE-COLLECTION-URL>/SitePages/CustomLearningAdmin.aspx`. This initializes the CustomConfig list item that sets up Custom Learning for its first use.

The configuration is now complete. To learn more about how to tailor the Custom Learning site and web part for your environment, see [Customize the training experience](custom_overview.md).

### Next Steps
- [Customize](custom_overview.md) the training experience for your organization.

