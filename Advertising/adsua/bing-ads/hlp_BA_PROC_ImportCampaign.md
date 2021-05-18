---
title: Import campaigns directly from Google Ads
description: You can import entire campaigns into Microsoft Advertising from Google Ads.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Import campaigns directly from Google Ads

![Directional arrow from left to right](../images/BA_Conc_Import.svg)
If you already are using Google Ads to advertise on Google, you can import these campaigns into Microsoft Advertising so that you can run the same ads on Bing. This is an easy way to expand your online advertising reach.

> [!NOTE]
> To import one Google Ads account at a time follow the steps in the **Import from Google Ads** section below. To import multiple Google Ads accounts into Microsoft Advertising follow the steps in the **Import multiple accounts from Google Ads** section further below.
> Some items and settings require special attention during import. Make sure to review [What gets imported from Google Ads](./hlp_BA_CONC_ImportWhatInfo.md).

## Import from Google Ads

1. From the global menu at the top of the page, select **Import** and then select **Import from Google Ads**.
1. Select **Sign in to Google** and follow the prompts to give Microsoft Advertising permission to import campaigns from your Google Ads account.
1. Under **Choose accounts**, select the account that you want to import from Google Ads and then select **Next**.
Select **Customize your import** if you want to choose which items are imported, adjust bids, bid strategies, and budgets, associate UET tags, and more.

1. If you don't require customizations then you can enter the import name, set the schedule, and then select **Start import** to finish the setup. We'll fine tune the import settings and automate the schedule so that your campaigns do their best on Microsoft Advertising.

## Customize your import

If you selected **Customize your import** in the steps above, you can choose which items are imported, adjust bids, bid strategies, and budgets, associate UET tags, and more.

Under **Which campaigns and ad groups do you want to import?**, select the campaigns and ad groups that you want to import from Google Ads and then select **Next**. If you select all ad groups in a campaign, but the **Show paused ad groups** check box is not selected, we will only import active ad groups in the campaign. Select **Show paused ad groups** to import all active and paused ad groups in the campaign.

If the currencies you set for your Google Ads and Microsoft Advertising account do not match, you can either convert your currency data to match Microsoft Advertising or opt out. If you choose to opt out, you can manually adjust your bids and budgets using the import options or after your import is complete.

Under **Choose which items to import and the options to set for them**, choose the items that you want to import and customize. You can delete items that have been removed from your Google Ads account by selecting **What to import** and selecting **Delete items that have been removed from your Google Ads account**. Then select **Next**.

Enter the import name, set the schedule, and then select **Save** to finish the setup. If you leave the schedule set to **Auto** we'll automate the schedule to best optimize your campaigns in Microsoft Advertising.

> [!NOTE]
> On **Import schedule &amp; history** page you can run the import again, modify the import schedule, and review logs to see what entities were newly added, updated, or couldn’t be imported. From the global menu at the top of the page, select **Import **** > ** **Import schedule &amp; history**.

## Import multiple accounts from Google Ads

> [!NOTE]
> At this time, you can import up to 10 Google Ads accounts at once.
> This feature is only available if you have multiple accounts in Google Ads and Microsoft Advertising. Learn more about [creating additional accounts](./hlp_BA_PROC_CreateAcctSelfServe.md).

1. From the global menu at the top of the page, navigate to your manager account.
1. From the global menu at the top of the page, select **Import** and then select **Import from Google Ads**.
1. Choose the Microsoft Advertising accounts that you want your Google Ads accounts to be imported to. Then select **Continue**.
1. Select **Sign in to Google** and follow the prompts to give Microsoft Advertising permission to import campaigns from your Google Ads account.
1. Under **Google Ads account name**, select the accounts that you want to import. Then select the drop down menu under **          Microsoft Advertising account name** and choose which Microsoft Advertising accounts they are imported to. Then select **Continue**.
1. Under **Choose Google Ads campaigns**, select the campaigns that you want to import from Google Ads and then select **Continue**.
Under **Choose import options**, choose the items that you want to import and customize. You can delete items that have been removed from your Google Ads account by selecting **What to import** and selecting **Delete items that have been removed from your Google Ads account**. Then select **Continue**.

Enter the import name, set the schedule, and then select **Schedule** or **Import** to finish the setup.

1. Optional: Under **Choose import options**, select **View import schedule**.

> [!NOTE]
> On **Import schedule &amp; history** page you can run the import again, modify the import schedule, and review logs to see what entities were newly added, updated, or couldn’t be imported. From the global menu at the top of the page, select **Import **** > ** **Import schedule &amp; history**.

## Few key items to check after import

Most items from Google Ads import seamlessly into Microsoft Advertising. However, there are items that we recommend you review after your import to make sure your campaigns are set up the way you want.

## Bids and budgets
Both Microsoft Advertising and Google Ads offer you the ability to limit your campaign spend on a daily basis.

Microsoft Advertising has different minimum bid and budget requirements than Google Ads. To help you import all of your data quickly, we will, by default, raise any bids and budgets that are too low to meet our minimums. During import setup, you can opt out of these increases, but we won’t import campaigns that are below the default minimums.

## Targeting options
Targeting options, such as location targeting and time of day targeting, are significantly different in each platform. You definitely will want to review your targeting settings in each platform. The settings used in one product will very likely not be appropriate for the other product. To learn more, see [How can I get my ads in front of my customers?](./hlp_BA_CONC_Targeting.md)

## Negative keywords
Microsoft Advertising does not use broad match negative keywords. If you have set up broad match negative keywords in Google Ads, those will be treated as phrase match negative keywords when importing to Microsoft Advertising. To find out where you can review the location options, see [How to add keywords that won't trigger my ads (Negative keywords)](./hlp_BA_PROC_AddNegativeKeywords.md).

Quality score is another area that can be different. The means of determining your quality score, and how it is used in determining the performance of your keywords and ads are different between the products. As you examine your quality score in one product and determine ways to optimize, realize those same optimization strategies might not be applicable in the other product. To learn more about the Microsoft Advertising quality score, take a look at [Quality score in depth](./hlp_BA_CONC_AboutQualityScore.md).

For a full list of what does and doesn't get imported from Google Ads, see [What gets imported from Google Ads](./hlp_BA_CONC_ImportWhatInfo.md)

> [!NOTE]
> Microsoft Advertising does not use your Google Ads sign-in information for any purpose other than the import process.
> If you exceed the limits when importing your campaigns from Google Ads, try importing your campaigns in groups. This will ensure that you don't exceed the maximum limits for import.
> If you want to learn the limits for accounts, campaigns, and ad groups, see [How should I organize my accounts and campaigns?](./hlp_BA_CONC_AboutAccts.md)
> Some Microsoft Advertising users are currently unable to import campaigns directly from Google Ads. If you have Google 2-step verification, you need to create an application-specific password for Microsoft Advertising. If you're still unable to import directly after several attempts, follow the steps to import campaigns using an import file.
> The update count reports all existing items that are fetched from Google Ads. It may be higher than the actual number of updates because it includes items that may not have been updated since the previous import.
> Change history reports the actual number of updates in Microsoft Advertising. It may be lower than the update count as it excludes items that do not have updates.
> Scheduled imports will fetch items that have changed in Google Ads since your last import. To re-import items that haven’t changed in Google Ads but have changed in Microsoft Advertising, select **Import campaigns** > **Import schedule and history** > **Run now**.
> It is highly recommended that you import a single Google Ads account to a single Microsoft Advertising account. Importing multiple accounts to a single one increases the risk of maxing out your account-level keyword limits.


