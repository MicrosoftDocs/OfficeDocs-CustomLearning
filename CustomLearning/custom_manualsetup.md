---
author: pkrebs
ms.author: pkrebs
title:  Stand alone web part setup
ms.date: 02/10/2019
description: Microsoft 365 learning pathways manual web part setup
---
# Stand alone web part setup

Microsoft 365 learning pathways offers a manual, stand-alone web part setup for those organizations that already have an established SharePoint Online modern communication site dedicated to training, or that just want to set up the learning pathways web part in their own communication site. Note that the manual setup requires experience working with Windows PowerShell and the SharePoint Online Management Shell. The steps for a manual set up of the learning pathways Web part as as follows:

- Validate that you have met all the prerequisites.
- Install the customlearning.sppkg file in your SharePoint Tenant App Catalog.
- Provision/Identify a modern communication site to act as your Microsoft 365 learning pathways home site.
- Execute a PowerShell script that will configure your tenant with the appropriate artifacts that learning pathways depends on.
- Navigate to the CustomLearningAdmin.aspx site page to load the admin web part to initialize the custom content configuration.

> [!NOTE]
> If you are looking for a fast, easy way to set up learning pathways, see [Provision Microsoft 365 learning pathways](custom_provision.md).

## Prerequisites
To ensure a successful manual setup of the learning pathways web part, the following prerequisites must be met. 

- You must have set up and configured the tenant-wide App Catalog. Please see [Set up your Office 365 tenant](https://docs.microsoft.com/en-us/sharepoint/dev/spfx/set-up-your-developer-tenant#create-app-catalog-site) and follow the Create app catalog site section. 
- If your tenant-wide App Catalog has already been provisioned you will need access to an account that has rights to upload a package to it to complete this setup process. Generally this is an account with the SharePoint administrator role. 
- If an account with that role does not work, go to the SharePoint admin center and find the Site Collection Administrators for the app catalog site collection and either log in as one of the Site Collection Administrators, or add the SharePoint administrator account that failed to the Site Collection Administrators. 
- You will also need access to an account that is a SharePoint Tenant Admin.

## Step 1 - Get the web part package and setup script from GitHub
As part of the setup process, you'll need the Microsoft 365 learning pathways Web part package and the PowerShell Setup Script.

- Go the the [learning pathways GitHub Repository](https://github.com/pnp/custom-learning-office-365).
- Click **Download** to save the web part package and script to a local drive. You'll be using the script and the web part package in later steps of this process.

## Step 2 - Upload the web part to the Tenant App Catalog
To set up Microsoft 365 learning pathways, you upload the customlearning.sppkg file to the tenant-wide App Catalog and deploy it. Please see [Use the App Catalog to make custom business apps available for your SharePoint Online environment](https://docs.microsoft.com/en-us/sharepoint/use-app-catalog) for detailed instructions on how to add an app to the app catalog.

## Step 3 - Provision/identify a modern communication site
Either identify an existing SharePoint communication site or provision a new one in your SharePoint Online tenant. For more information about how to provision a communication site see [Create a communication site in SharePoint Online](https://support.office.com/en-us/article/create-a-communication-site-in-sharepoint-online-7fb44b20-a72f-4d2c-9173-fc8f59ba50eb) and follow the steps to create a communication site.

## Step 4 - Add the Microsoft 365 learning pathways app to the site

1. From the SharePoint site, click the System menu, then click **Add an App**. 
2. Under **Your Apps**, click **From Your Organization**, and then click **learning pathways for Office 365**. 

## Step 5 - Set permissions for the site
Ensure the following permissions are set for the site:
- **Site Collection Administrator or part of the Owners group** - Permissions required to  initialize the CustomConfig list item that sets up learning pathways for its first use. 
- **Members group** - permissons required to Administer learning pathways, including hiding and showing content and administering custom playlists
- **Visitors group** - permissions required to view site content. 

## Step 6- Execute PowerShell Configuration Script
A PowerShell script `M365lpConfiguration.ps1` is included that you will need to execute to create three [tenant properties](https://docs.microsoft.com/en-us/sharepoint/dev/spfx/tenant-properties) that the solution uses. In addition the script creates two [single part app pages](https://docs.microsoft.com/en-us/sharepoint/dev/spfx/web-parts/single-part-app-pages) in the site pages library to host the admin and user web parts at a known location.

1. If you haven't already downloaded the SharePoint Online Management Shell, download it now. See [SharePoint Online Management Shell Download](https://go.microsoft.com/fwlink/p/?LinkId=255251).
2. You may need to set a PowerShell execution policy to run the script. For more information, see [About Execution Policies](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-6).
3. Execute the `CustomLearningConfiguration.ps1` script. In addition to your Tenant Admin credentials, the script will prompt you for your tenant name and site name. Considering the following example for your site URL, `https://contoso.sharepoint.com/sites/O365CL`, `contoso` is the tenant name and `O365CL` is the site name. 

### Disabling Telemetry Collection
Part of this solution includes anonymized telemetry tracking opt in, which by default is set to on. If you are performing a manual install and you would like to turn telemetry tracking off, please change the `CustomlearningConfiguration.ps1` script to set the $optInTelemetry variable to $false and run the script.

## Validate Provisioning Success and Initialize the CustomConfig List

After the PowerShell script is successfully run, you navigate to the site, initialize the **CustomConfig** list item that sets up learning pathways for its first use, and validate the site is working.

- Go to `<YOUR-SITE-COLLECTION-URL>/SitePages/CustomLearningAdmin.aspx`. Opening **CustomLearningAdmin.aspx** initializes the **CustomConfig** list item that sets up learning pathways for first use. You should see a page that looks like this:

![cg-adminapppage.png](media/cg-adminapppage.png)

## Add Owners to Site
As the Tenant Admin, it's unlikely you'll be the person customizing the site, so you'll need to assign a few owners to the site. Owners have administrative privileges on the site so they can modify site pages and rebrand the site. They also have the ability to hide and show content delivered through the learning pathways Web part. In addition, they'll have the ability to build custom playlist and assign them to custom subcategories.  

1. From the SharePoint **Settings** menu, click **Site Permissions**.
2. Click **Advanced Permission Settings**.
3. Click **learning pathways for Office 365 Owners**.
4. Click **New** > **Add Users to this group**, and then add the people you want to be Owners. 
5. Add a link to [Explore the Site](https://docs.microsoft.com/en-us/Office365/CustomLearning/custom_explore) in the Share message, and then click **Share**.

### Next Steps
- [Customize](custom_overview.md) the training experience for your organization.

