---
author: pkrebs
ms.author: pkrebs
title:  Provision a new learning pathways multilingual site
ms.date: 02/10/2019
description: Provision the Microsoft 365 learning pathways site via the SharePoint Provisioning Service
---

# Provision a new learning pathways multilingual site
Organizations that that don’t have learning pathways already provisioned in their tenant can add the multilingual learning pathways solution to their tenant. With this option, the learning pathways SharePoint template is translated into nine languages and can be used with a minimum of modification. 

> [!IMPORTANT]
> If you already have learning pathways provisioned in your tenant, it's recommended that you follow the upgrade path for learning pathways. If you install learning pathways over an existing instance in your tenant, any changes made to the the learning pathways site template or playlists will be lost.

## Prerequisites for multilingual support
 
To successfully set up Microsoft 365 learning pathways with the Provisioning Service, the person doing the provisioning must meet the following pre-requisites: 
 
- The person provisioning learning pathways must be a Tenant Administrator of the tenant where learning pathways will be provisioned.  
- A tenant App Catalog must be available within the Apps option of the SharePoint Admin Center. If your organization does not have an SharePoint tenant App catalog, refer to the [SharePoint Online documentation](https://docs.microsoft.com/en-us/sharepoint/use-app-catalog) to create one. Note that you must wait at least two hours after creating the app catalog before provisioning learning pathways.  
- The person provisioning learning pathways must be a Site Collection Owner of the Tenant App Catalog. If the person provisioning learning pathways is not a Site Collection Owner of the App Catalog [complete these instructions](addappadmin.md) and continue. 

## Ensure the Tenant Admin account does not have a language selected
Before you provision Learning Pathways, ensure that the Admin Account for the tenant does not have a language selected. Here’s how to verify if the Admin account does not have a language selected. 
1.	With your Edge Admin profile, go to office.com.
2.	Enter the user credentials (if necessary).
3.	In Microsoft 365, click **All Apps** > Delve. 
4.	Click **Me** > **Update Profile**.
5.	Scroll down the page and click **How can I change language and regional settings**.
6.	Click **here**, and then click the ellipses **...**.
7.	Under **My Display Languages**, you should see **No languages selected**. If a language is selected, unselect it.


### To provision learning pathways

1. Go to the [Microsoft 365 learning pathways solution page](https://provisioning.sharepointpnp.com/details/3df8bd55-b872-4c9d-88e3-6b2f05344239).
2. Click **Add to your tenant**. If you are not signed into to your tenant, the Provisioning Service will ask for your Tenant Admin credentials. 
3. From the Permissions requested dialog box, select **Consent on behalf of your organization** and then select **Accept**.

The provisioning service requires these permissions to create the tenant app catalog, install the application into the tenant app catalog and provision the site template. There is no overall impact on your tenant and these permissions are explicitly used for the purpose of the solution installation. You must accept these permissions to proceed with the installation.

4. Complete the fields on the provisioning information page as appropriate for your installation. At a minimum, enter the email address where you wish to get notifications about the provisioning process and the destination URL for your site to be provisioned to.  
> [!NOTE]
> Make the destination URL for your site something friendly to your employees such as "/sites/MyTraining" or "/teams/LearnMicrosoft365".

![inst_options.png](media/inst_options.png)

6. Click **Provision** when ready to install learning pathways into your tenant environment.  The provisioning process will take up to 15 minutes. You will be notified via email (to the notification email address you entered on the Provisioning page) when the site is ready for access. 

> [!IMPORTANT]
> The Tenant Admin who provisions the learning pathways site must go to the site, and then open **CustomLearningAdmin.aspx** to initialize learning pathways Admin properties. At this time, the Tenant Admin should also assign Owners to the site. 

## Validate Provisioning Success and Initialize the CustomConfig List

When provisioning is complete, the Tenant Admin who provisioned the site, receives an email from the PnP Provisioning Service. The email contains a link to the site. At this point, the Tenant Admin should go to the site using the link provided in the email and set up the site for first use:

- Go to `<YOUR-SITE-COLLECTION-URL>sites/<YOUR-SITE-NAME>/SitePages/CustomLearningAdmin.aspx`. Opening **CustomLearningAdmin.aspx** initializes the **CustomConfig** list item that sets up learning pathways for first use. You should see a page that looks like this:

![cg-adminapppage.png](media/cg-adminapppage.png)

## Add Owners to Site
As the Tenant Admin, it's unlikely you'll be the person customizing the site, so you'll need to assign a few owners to the site. Owners have administrative privileges on the site so they can modify site pages and rebrand the site. They also have the ability to hide and show content delivered through the learning pathways Web part. In addition, they'll have the ability to build custom playlist and assign them to custom subcategories.  

1. From the SharePoint **Settings** menu, click **Site Permissions**.
2. Click **Advanced Permission Settings**.
3. Click **Microsoft 365 learning pathways Owners**.
4. Click **New** > **Add Users to this group**, and then add the people you want to be Owners. 
5. Add a link to [Explore the Site](custom_exploresite.md) in the Share message, and then click **Share**.

## Add translators to the site
Translators require member permissions or higher on the site. They also require a foreign language user profile. Go <here> for more information about setting up translators and foreign language profiles.

### Next Steps
- Explore the [default content](custom_exploresite.md) provided in the site and web part.
- Go <here> to get started with information about the translation process for learning pathways.
