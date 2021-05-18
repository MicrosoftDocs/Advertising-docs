---
title: Set up UET tags using Google Tag Manager
description: Third-party tag managers allow you to manage your website tags in one place. Learn how to set up UET tags using Google Tag Manager.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Set up UET tags using Google Tag Manager

> [!NOTE]
> This article shows how to do a basic setup of UET tags with Google Tag Manager. Google Tag Manager offers several advanced features to customize when and how your tags are fired. Please refer to Google's [Tag Manager Help](https://go.microsoft.com/fwlink?LinkId=2010586) for more information.
> Microsoft Advertising is not responsible for Google Tag Manager's processes or documentation, nor for changes made to Google Tag Manager's processes or documentation.

Tag managers replace static tags with dynamic tags that are easier to implement and update. The dynamic tag is a container, a small snippet of code that allows you to dynamically insert tags into your website. You can think of the container tag as a bucket that holds other types of tags.

## Implementing UET using Google Tag Manager
To send information from Google Tag Manager to Microsoft Advertising, you need to create a "container" in Google Tag Manager and then add the Microsoft Advertising UET tag to it. Here's how:
1. When you set up an account in Google Tag Manager, enter your website's URL in the **Container name** box.
1. From the **Overview** page of this container's workspace, click the container ID (formatted like "GTM-XXXXXX") in the toolbar. You will see the Google Tag Manager container code and instructions.
1. Copy the container code and paste it into the head or body section of **every page** of your website.
1. Back on the **Overview** page of your container's workspace, click **New tag**.
1. In the **Tag Configuration** pane, click the pencil icon.
   1. Under **More**, select **Bing Ads Universal Event Tracking**.
   1. Enter your **Bing Ads UET Tag ID**. You can find the tag ID in Microsoft Advertising by selecting **Conversion Tracking**&nbsp;&gt;&nbsp;**UET tags**.
   1. If you have more than one UET tag tracking code on a webpage, enter the **global event tracking object name** within the UET tag script that you want Google Tag Manager to track into the **UETQ Variable ID** box. Otherwise, use the default "uetq" value. Learn more about [reasons for creating more than one UET tag](./hlp_BA_CONC_UETv2MutliTags.md) and [how to rename the uetq event tracker](./hlp_BA_CONC_UETv2OverrideUetTag.md).
> [!NOTE]
> If you don't use a different uetq variable, the [UET Tag Helper](./hlp_BA_CONC_UET_TagHelper.md) will return the "Multiple UET tags on this webpage use the same event name" issue. If you have multiple tags placed on the site and one of those is implemented through Google Tag Manager, it's possible that the UET Tag Helper will fail to detect the "Multiple UET tag on this webpage use the same event name" issue.

   1. For **Event Type**, select **Page Load**.

1. In the **Triggering** pane, click the pencil icon and select **All pages**.  A tag must have at least one trigger for it to fire. Triggers are evaluated during runtime and are fired when the trigger conditions are met.
1. Click **Save**, enter a **Tag Name**, and then click **Save**.
1. In the toolbar of your container's workspace, click **Submit** and then **Publish** to enable the tag and add a version.
1. In Microsoft Advertising, select **Conversion Tracking**&nbsp;&gt;&nbsp;**UET tags** to verify that you are receiving conversions. It typically takes up to 24 hours for a tag to be verified.
1. Using the [UET Tag Helper](./hlp_BA_CONC_UET_TagHelper.md), browse your website and confirm that all pages fire the UET page load event.

## Advanced: UET custom event and variable revenue reporting using Google Tag Manager
> [!IMPORTANT]
> To set up [custom events](./hlp_BA_CONC_UETv2CustomEvent.md) and/or [revenue variables](./hlp_BA_CONC_UETv2RevenueVariables.md) using Google Tag Manager, you must have added your UET tag to Google Tag Manager as described in the previous section.

Custom events and revenue variables are dynamic values, so you need to tell Google Tag Manager how to read them.

1. **Set up Google Tag Manager variables to read dynamic values from your page** : While Google Tag Manager supports many variants (read from html elements, functions, variables, etc.), we'll set up Google Tag Manager variables to read JavaScript variables in this example.
   1. Visit our [Google Tag Manager sample page](https://go.microsoft.com/fwlink?LinkId=2010814) (English only), right-click in the webpage, and then click **View source** or **View page source** depending on your browser. You will see the following variables:
```
<script>   var varEventCategory = "MyCategory";   var varEventAction = "MyAction";   var varEventLabel = "MyLabel";   var varEventValue = 5;   var varRevenue = 6;						</script>
```

> [!IMPORTANT]
> You'll need to make sure that the variables in **your** website's code match the custom event and/or variable revenue values that you set up when you created your conversion goal in Microsoft Advertising. But for the purpose of this example, let's say that you have the above variables in your website, and you want Google Tag Manager to read them.

   1. In your Google Tag Manager container's workspace, click **Variables**.
   1. Under **User-Defined Variables**, click **New**.
   1. In the **Variable Configuration** pane, click the pencil icon.
   1. Under **Page Variables**, select **JavaScript Variable**.
   1. In the **Global variable name** box, enter the variable — in this example, "varEventCategory".
   1. Click **Save**.
   1. In the **Variable Name** box, enter the name you gave this variable when you created the conversion goal. In our example, this would be "MyCategory".
   1. Click **Save**.
   1. Repeat the above process, creating a new variable for each custom event and/or variable revenue that you want to track, making sure to match the values that you set up when you created each conversion goal in Microsoft Advertising.

1. **Set up a trigger** :
   1. In your Google Tag Manager container's workspace, click **Triggers**, and then **New**.
   1. In the **Trigger Configuration** pane, click the pencil icon and select **Custom Event**.
   1. Enter an **Event Name**, and click **Save**.
   1. Enter a **Trigger Name**, and click **Save**.

> [!IMPORTANT]
> **Your triggers in Google Tag Manager must match the possible interactions that are coded on your webpage.**
> Take a look at our [Google Tag Manager sample page](https://go.microsoft.com/fwlink?LinkId=2010814) for an example. On this page, we have coded for a click on a button. Right-click in the webpage, and then click **View source** or **View page source** depending on your browser, and look for the code with "id=btnCustomEvent".

1. **Create a new tag** : This secondary tag will tie together the event variables and trigger you just created.
   1. In your Google Tag Manager container's workspace, click **Tags**, and then **New**.
   1. In the **Tag Configuration** pane, click the pencil icon.
   1. Under **More**, select **Bing Ads Universal Event Tracking**.
   1. Enter your **Bing Ads UET Tag ID**. You can find the tag ID in Microsoft Advertising by selecting **Conversion Tracking**&nbsp;&gt;&nbsp;**UET tags**.
   1. If you have more than one UET tag tracking code on a webpage, enter the **global event tracking object name** within the UET tag script that you want Google Tag Manager to track into the **UETQ Variable ID** box. Otherwise, use the default "uetq" value.
   1. For **Event Type**, select **Custom**.
   1. Add the variables that you created in step 1 within the respective **Event Parameters** boxes.
   1. In the **Triggering** pane, click the pencil icon and select the trigger that you created in step 2.
   1. Click **Save**, enter a **Tag Name**, and then click **Save**.

1. **Publish your changes** : In the toolbar of your Google Tag Manager container's workspace, click **Submit** and then **Publish**.
1. **Check your website's code** : Verify that you have placed the below variables on your website's conversion page (the page where customers complete their transactions). Also, ensure that the variable values match the event values within your goal setup. In our example:
```
<script>   var varEventCategory = "MyCategory";   var varEventAction = "MyAction";   var varEventLabel = "MyLabel";   var varEventValue = 5;   var varRevenue = 6;						</script>
```

1. **Validate your tags** : Use the [UET Tag Helper](./hlp_BA_CONC_UET_TagHelper.md) to confirm that the variable revenue and custom events are being fired from your conversion page.


