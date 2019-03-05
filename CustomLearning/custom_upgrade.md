---
author: pkrebs
ms.author: pkrebs
title:  Custom Learning Upgrade
ms.date: 02/10/2019
description: Custom Learning for Office 365 manual web part setup
---
# Manual web part setup

Custom Learning for Office 365 provides a manual upgrade process for organizations that have participated in earlier pilots. With the upgrade process, organizations can continue to use their current Custom Learning site and upgrade by adding the new, enhanced, Custom Learning web part to their SharePoint App Catalog, and then running a PowerShell script. The following provides an overview of the upgrade process: 

- Validate that the person responsible for uploading the new web part and running the Powershell script has the required permissions
- Upload the web part, customlearning.sppkg file, to your Office 365 Tenant App Catalog
- Execute a PowerShell script that will configure your tenant with the appropriate artifacts required for Custom Learning
- Navigate to the CustomLearningAdmin.aspx page in the Custom Learning site to to initialize the Custom Ccontent configuration.

## Prerequisites
To ensure a successful upgrade of Custom Learning, the following prerequisites must be met. 

- You must have set up a tenant-wide App Catalog. If you don't have a Tenant App Catalog, please see [Set up your Office 365 tenant](https://docs.microsoft.com/en-us/sharepoint/dev/spfx/set-up-your-developer-tenant#create-app-catalog-site) and follow the Create app catalog site section. 
- If your tenant-wide App Catalog has already been provisioned, you need access to an account that has rights to upload a package to it. Generally this is an account with the SharePoint Administrator role. 
- If an account with the SharePoint Administrator's role doesn't work: Go to the SharePoint Admin Center, select the App Catalog, click Owners, and sign in as one of the Site Collection Administrators or add the SharePoint Administrator account that failed to the Site Collection Administrators list. 

## Step 1 - Get the web part package and setup script from GitHub
As part of the setup process, you'll need the Custom Learning Web part package and the PowerShell Setup Script.

1. Go the the [Custom Learning GitHub Repository](https://github.com/pnp/custom-learning-office-365).
2. Click **Clone or download**, and then **Download ZIP**.   
3. Save the **ZIP** file to a location on your local drive.
4. Extract the **ZIP** file on your local drive.

## Step 2 - Upload the web part to the Tenant App Catalog
To set up Custom Learning for Office 365, you upload the customlearning.sppkg file to the tenant-wide App Catalog and deploy it. Please see [Use the App Catalog to make custom business apps available for your SharePoint Online environment](https://docs.microsoft.com/en-us/sharepoint/use-app-catalog) for detailed instructions on how to add an app to the app catalog.

1. In Office 365, click **Admin**.
2. Under **Admin centers**, click **SharePoint**.
3. Click **apps** > **App Catalog** > **Distribute apps for SharePoint.**
4. Click **Upload** > **Choose Files**.
5. In the folder where you saved the ZIP file, select the **webpart** folder, and then select **customlearning.sppkg.**
6. Click **Deploy**.

## Step 5- Execute PowerShell Configuration Script
A PowerShell script `CustomLearningConfiguration.ps1` is included in the ZIP download from GitHub. You need to execute the script to create three [tenant properties](https://docs.microsoft.com/en-us/sharepoint/dev/spfx/tenant-properties) that the solution uses. In addition, the script creates two [single part app pages](https://docs.microsoft.com/en-us/sharepoint/dev/spfx/web-parts/single-part-app-pages) in the site pages library to host the admin and user web parts at a known location. These app pages are:

- CustomAdministration.aspx
- CustomViewer.aspx

### To run the Powershell Script
- Using PowerShell, execute the `CustomLearningConfiguration.ps1` script located in the webpart folder from the GitHub ZIP. If successful, you'll see three key/value pairs and **Custom Learning Admin for Off...** in the Command window.

### Disabling Telemetry Collection
Custom Learning includes anonymized telemetry tracking opt in, which by default is set to on. If you  would like to turn telemetry tracking off, please change the `CustomlearningConfiguration.ps1` script to set the `$optInTelemetry` variable to `$false`.

## Step 6 - Initialize web part custom configuration
After the PowerShell script is successfully run, navigate to `<YOUR-SITE-COLLECTION-URL>/SitePages/CustomLearningAdmin.aspx`. Opening **CustomLearningAdmin.aspx** initializes the **CustomConfig** list item that sets up Custom Learning for first use. You should see a page that looks like this:

![cg-adminapppage.png](media/cg-adminapppage.png)

## Add Owners to Site
As the Tenant Admin, it's unlikely you'll be the person customizing the site, so you'll need to assign a few owners to the site. Owners have administrative privileges on the site so they can modify site pages and rebrand the site. They also have the ability to hide and show content delivered through the Custom Learning Web part. They'll also have the ability to build custom playlist and assign them to custom subcategories.  

1. From the SharePoint **Settings** menu, click **Site Permissions**.
2. Click **Advanced Permission Settings**.
3. Click **Custom learning for Office 365 Owners**.
4. Click **New** > **Add Users to this group**, add the people you want to be Owners, and then click **Share**.

The upgrade is now complete. To learn more about how to tailor the Custom Learning site and web part for your environment, see [Customize the training experience](custom_overview.md).

## Upgrade Instructions for Site Owners
Custom Learning for office 365 has introduced a variety of enhancements to the web part. Working with the web part is covered in detail in the [Customize the learning experience](custom_overview.md) section. For now, the Site Owner should:  

- Verify the Custom Learning for Office 365 Web part is available. 
- Replace the existing web part on pages with the new web part
- Replace any links pointing to the old web part

### Verify the Custom Learning for Office 365 web part is available
1.	From the Custom Learning site, click **Settings**, and then click ***Add a Page**.
2.	Click the **+** icon on the page to add a web part, and then select the **Custom Learning for Office 365** web part. The page should now look similar to the following graphic:

[cg-adminapppage.png](media/cg-adminapppage.png)
 
### Replace the old web part with the new web part
Before replacing the Custom Learning web part or making changes to the site, we recommend you read the [Customize the Learning Experience](custom_overview.md) documentation as it explains how to use the new web part. 

To upgrade the Custom Learning site, replace existing instances of the Web part with the new Web part. While we can’t be sure where the Web part has been added, the guidance for previous pilots was to add the web part to the following pages, so look to replace the web part on these pages:

- Get-started-with-Office-365.aspx
- Get-started-with-Microsoft-Teams.aspx
- Get-started-with-OneDrive.aspx
- Get-started-with-SharePoint.aspx

### Replace existing links to the web part
With the enhancements to the new web part, they way that you link to a playlist has changed. As part of the upgrade, you should replace any links to the web part, including menu items, and links on the Home page. Before replacing the Custom Learning web part or making changes to the site, we recommend you read the [Customize the Learning Experience](custom_overview.md) documentation as it explains how to use the new web part. 

## Recreate existing playlists 
To ensure that playlists work properly, any playlists that have been created with the earlier version of the web part will need to be recreated. Before deleting the playlists, make a list of the custom playlists and associated assets so you can recreate them easily with the new Custom Learning Web part. Make a copy of a playlist and then delete it. You can use the JSONData field to make a copy of the content of a playlist before you delete. This will make it easier to create later.


•	From the Custom Learning site, click Settings > Site Content. 
•	Select a playlist, select the ellipses, select Edit, and then copy the contents of the JSONData field and save in NotePad or a separate document for later reference. Select Cancel.
•	Select the playlist, select the ellipses, and then select Delete.
•	You are now ready to recreate the playlist with the new Web part.
For instructions on using the new Custom Learning for Office 365 Web part, see https://docs.microsoft.com/en-us/office365/customlearning/custom_overview.

## Step 8 - Chan

### Next Steps
- [Customize](custom_overview.md) the training experience for your organization.

