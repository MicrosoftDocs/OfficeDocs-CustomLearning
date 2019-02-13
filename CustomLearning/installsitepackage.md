---
author: karuanag
ms.author: karuanag
title:  Provision the Custom Learning site
ms.date: 02/10/2019
description: Provision the Custom Learning for Office 365 site via the SharePoint Provisioning Engine
---

# Provision the Custom Learning Site

1. Go to http://provisioning.sharepointpnp.com and **sign in** from the upper right hand corner of the home page.  Sign in with the  credentials for the targeted tenant where you plan to install the site template.

![pnphome.png](media/inst_signin.png)

2. Clear the **Consent on behalf of your organization** and select **Accept**.

![in](media/inst_perms.png)

3. Select **Custom Learning for Office 365** from the solution gallery.

![in](media/inst_select.png)

4. From the solution home page select **Add to your Tenant**

![inst_select.png](media/inst_add.png)

5. Complete the fields on the provisioning information page as appropriate for your installation. At a minimum enter the email address where you wish to get notifications about the provisioning process and the destination URL for your site to be provisioned to.  

> [!NOTE]
> Make the destination URL for your site something friendly to your employees such as "/sites/MyTraining" or "/teams/LearnOffice365".

![inst_options.png](media/inst_options.png)

6. Select **Provision** when ready to install CLO365 into your tenant environment.  The provisioning process will take up to 15 minutes. You will be notified via email (to the notification email address you entered on the Provisioning page) when the site is ready for access.

7. When you have been notified that provisioning is complete browse to the destination URL you entered in the Provisioning page.

8. Favorite the site in the upper right hand corner and bookmark the URL for future reference.  

### Next Steps
- Explore the [default content](sitecontent.md) included in the webpart.
- [Customize](customization.md) the training experience for your organization.
- [Drive adoption](driveadoption.md) of your training solution.
