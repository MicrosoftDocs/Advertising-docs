---
title: FAQ: Expanded Text Ads
description: Expanded Text Ads give you additional content to make your ads more eye-catching and helpful.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# FAQ: Expanded Text Ads

## What are Expanded Text Ads?
Expanded Text Ads are a new, mobile-optimized ad format that enables you to craft longer ad copy and optimize your ad text to better engage with potential customers before they click on your ads. Expanded Text Ads work seamlessly on mobile, tablet, and desktop devices, giving you a way to create more compelling calls to action for consumers and drive higher conversions to your business.

Here's how Expanded Text Ads compare to standard text ads:

|Ad part|Standard text ads|Expanded Text Ads|
|---|---|---|
|Ad title|25 characters|90 characters: Supports three headlines, up to 30 characters each, separated by a space, vertical bar, and space (" | ")|
|Ad text|71 characters|180 characters: Supports two descriptions, up to two 90 characters each|
|Display URL|35 characters, manually entered and error-prone|Domain and subdomain automatically generated from your final URL (preserving capitalization) plus two customizable URL paths|

## How do I set up Expanded Text Ads?
1. From the **Ads** tab, click **Create ad** and then select an ad group (or from the main menu on the left, click **All campaigns** > **Ad groups**. Then, click **Ads &amp; extensions**).
1. For **Ad type**, select **Expanded Text Ad**.
1. Enter your landing page URL in the **Final URL** box. **Note** : Your final URL — including prefix (e.g., "www."), suffix (e.g., ".com"), and any [tracking templates](./hlp_BA_CONC_GoogleAnalytics.md)&nbsp;— must be no longer than 2048 characters. However, your final URL **domain** (everything in your final URL before the first slash or tracking template) must be no longer than 67 characters.
1. Unlike standard text ads, you can then enter three parts of your ad title, each up to 30 characters long. The third title is optional.
1. Unlike standard text ads, you can have two parts of your description, each up to 90 characters long. The second description is optional.
1. Similarly, you can also enter two parts of the URL path customers will see in your ad.
1. Fill in the ad text to appear below the path.
1. Click **Save**.

## What are the character limits for Expanded Text Ads?
|Text field|Character limit|
|---|---|
|Final URL|2048 characters, including prefix (e.g., "www."), suffix (e.g., ".com"), and tracking templates|
|Titles|30 characters each, up to three ad titles|
|Ad text|90 characters each, up to two ad descriptions|
|Paths|15 characters each**Note** : All together, the final URL domain (everything in your final URL before the first slash or tracking template) and paths cannot exceed 67 characters.|

**Note** : Keep in mind the total length of the potential dynamic text, including Param1, Param2, Param3, and DKIs. It is possible to create ad titles, ad text, and URLs that fit within our character limits when you create them, but that become too long when the dynamic text is applied. In such cases, the system may consider a total length check of 90 characters for the Title, 67 characters for the display URL, and 180 characters for the Description text (excluding separators), or use the default text as what is deemed fit based on predicted responses, device length limits, and more.

> [!IMPORTANT]
> Double-width characters — such as Chinese characters — count as two characters each.

## Are Upgraded URLs required in order to use Expanded Text Ads?
Upgraded URLs are now generally available for all customers worldwide but it is not required to migrate all your existing URLs, which include standard text ad URLs, keyword destination URLs, and Sitelink Extension URLs, to start taking advantage of Expanded Text Ads. You are still able to manage and optimize standard text ads using destination URLs and set up new Expanded Text Ads using final URLs. We do recommend setting up an account-level tracking template to ensure that you can properly track and report your ad clicks.

[Learn more about Upgraded URLs](./hlp_BA_CONC_UpgradeURL_MigrateFAQ.md)

## Will Expanded Text Ads appear in the same ad positions as standard text ads?
Yes, Expanded Text Ads will appear in all of the ad positions that standard text ads currently do.

## What can I do to maximize Expanded Text Ads impressions?
Once your Expanded Text Ads are set up, there should not be any immediate action on your side.

Note that, if you have chosen "maximize clicks" as the Ad Rotation option for an ad group, Expanded Text Ads and standard text ad will not have equal chance of getting an impression since our algorithms are still learning about the your newly created Expanded Text Ads.

## Will my Expanded Text Ads and standard text ads compete against each other? Will it impact my cost per click?
Different ad formats will naturally compete with each other and, depending on your choice for Ad Rotation, one of them will go to auction. Your cost per click for Expanded Text Ads should not be impacted.

## I use a third-party tool provider or agency. Will they support Expanded Text Ads?
If you are using a third-party tool provider or agency to aid in your campaign and URL management, check with them to find out their plans for upgrading before planning your URL upgrades.

## Can I download and upload Expanded Text Ads in bulk?
To bulk download and upload Expanded Text Ads, use Microsoft Advertising Editor v11.3 or later (if you are participating in the Microsoft Advertising Editor for Mac beta, use v0.93 or later). You can make sure you have the latest version of Microsoft Advertising Editor by clicking **Help**&nbsp;&gt;&nbsp;**Check for updates**.

## What version of Microsoft Advertising Editor do I need to have to work with Expanded Text Ads?
Microsoft Advertising Editor v11.3 or later (if you are participating in the Microsoft Advertising Editor for Mac beta, use v0.93 or later). You can make sure you have the latest version of Microsoft Advertising Editor by clicking **Help**&nbsp;&gt;&nbsp;**Check for updates**.

## Can I import only my Expanded Text Ads from Google Ads?
Yes, if you want to import only Expanded Text Ads from Google Ads, Microsoft Advertising Editor is the right tool. In Microsoft Advertising Editor, you can either:

1. Run **Import from Google Ads** to stage all your Google Ads changes locally.
1. Revert all changes except those related to Expanded Text Ads.
1. Post only changes to Expanded Text Ads.

Or:

1. Export only Expanded Text Ads from your Google Ads account using AdWords Editor.
1. Using File Import, stage changes locally in Microsoft Advertising Editor.
1. Post only changes to Expanded Text Ads.

> [!IMPORTANT]
> You must have at least Microsoft Advertising Editor version 11.3 for Windows or version 0.93 for Mac.

## Can I use {param1}, {param2}, and {param3} for keyword tracking in Expanded Text Ads?
Yes, you can add a {param} to a domain in the Final URL box, but you cannot have your Final URL be only a {param}. In other words, in the Final URL box, “contoso.com/{param1}” is allowed, but just “{param1}” is not. {param1}, {param2}, and {param3} are also still allowed in ad titles and descriptions.

## Will Expanded Text Ads work with all my existing ad extensions?
Yes, all ad extensions and Automated Extensions will continue to work as expected. We recommend setting up Expanded Text Ads in the same campaigns and ad groups as your existing standard text ads so you can use your existing ad extensions. [Learn more about ad extensions](./hlp_BA_CONC_AboutAdExtensions.md)

## Will Expanded Text Ads get preference over standard text ads?
Our engine will choose the ad that is the most relevant to the search results page. Over time, as Expanded Text Ads adoption grows, we expect that there will be changes in our algorithms to continue to deliver the best ROI for our advertisers.

## Which part of my domain is auto-generated from the final URL?
Microsoft Advertising will automatically use the domain of the URL that is entered, including its subdomains. See the table below for examples.

|Advertiser-entered final URL|Microsoft Advertising will display|
|---|---|
|http://contoso.com/contact.html|contoso.com|
|http://www.contoso.com/contact.html|www.contoso.com|
|http://ContosoStore.com/contact.html|ContosoStore.com|
|http://www.ContosoStore.com/contact.html|www.ContosoStore.com|
|http://Store.Contoso.com/contact.html|Store.Contoso.com|

> [!NOTE]
> Your final URL’s domain — including prefix (e.g., "www.") and suffix (e.g., ".com") — must be no longer than 67 characters.

## How does Microsoft Advertising handle capitalization for display URLs?
Microsoft Advertising will preserve the capitalization you enter in the final URL. See the table below for examples.

|Advertiser-entered final URL|Microsoft Advertising will display|
|---|---|
|http://contoso.com/contact.html|contoso.com|
|http://www.contoso.com/contact.html|www.contoso.com|
|http://ContosoStore.com/contact.html|ContosoStore.com|
|http://www.ContosoStore.com/contact.html|www.ContosoStore.com|
|http://Store.Contoso.com/contact.html|Store.Contoso.com|

> [!NOTE]
> Your final URL’s domain — including prefix (e.g., "www.") and suffix (e.g., ".com") — must be no longer than 67 characters.

## How will Microsoft Advertising auto-generate display URL domains with Expanded Text Ads?
|Advertiser-entered final URL|Microsoft Advertising will display|
|---|---|
|http://contoso.com/contact.html|contoso.com|
|http://www.contoso.com/contact.html|www.contoso.com|
|http://ContosoStore.com/contact.html|ContosoStore.com|
|http://www.ContosoStore.com/contact.html|www.ContosoStore.com|
|http://Store.Contoso.com/contact.html|Store.Contoso.com|

> [!NOTE]
> Your final URL’s domain — including prefix (e.g., "www.") and suffix (e.g., ".com") — must be no longer than 67 characters.

## Which reports have columns for Ad Title 1, Ad Title 2, and Ad Title 3 for Expanded Text Ads?
The Ad performance report shows these columns by default. They are also available in the Ad dynamic text and Ad extension by ad report.

## How do I import Expanded Text Ads with ad customizer feeds?
1. At the top of the page, click **Import Campaigns** and then click **              Import from Google Ads            ** (or from the global menu at the top of the page, click **Import** and then click **              Import from Google Ads            **).
1. If you have imported from Google Ads in the past 90 days, you will see a table that shows you the **Date/Time** and            **              Google Ads account            ** that was imported along with:
|Column Name|Description|
|---|---|
|Summary|Shows how many entities were imported successfully and how many had errors. Click the ellipsis ![ellipse](../images/BA_ScreenCap_DeliveryDetails.png) to see details.|
|Actions|If you had errors, you will see a link to download the error file which you can review.|

1. Click **Sign in to Google**.
1. Enter your Google Ads sign-in information, click **Sign in**. If you’re having trouble signing in to Google Ads:
- Clear your browser's cache and cookies.
- Try another browser.
- [Contact support](https://go.microsoft.com/fwlink?LinkId=398371).

1. Select if you want to import all existing and new campaigns from your Google Ads account or specific campaigns and ad groups in that account. Then click **Continue**.
If the currencies you set for your Google Ads and Microsoft Advertising account do not match, you can either convert your currency data to match Microsoft Advertising or opt out. If you choose to opt out, you can manually adjust your bids and budgets using the import options or after your import is complete.

1. Under **Choose Import Options**, select either **Items not previously imported into Microsoft Advertising** or **Updates to Existing items**.
1. Click **Show advanced options**.
1. Under **Feeds**, select **Ad customizer feeds**.
1. (Optional) You can delete items that have been removed from your Google Ads account by clicking **What to import** and selecting **Delete items that have been removed from your Google Ads account**. Please note that removed Google Ads items will be deleted along with their associated sub-items. For example, if you previously removed a Google Ads campaign, its ads groups, ads, and keywords will also be deleted during this import. Ad extensions removed in Google Ads will not be deleted in Microsoft Advertising during this import.
1. Optional: Under **Schedule Imports**, click **When** and then set the schedule you want, which can be **Once**, **Daily**, **Weekly**, or **Monthly**.
1. Click **Import** or if you want to set a schedule, click **Schedule**.

> [!NOTE]
> Review the **Import summary** to see what entities were were newly added, updated, or skipped (couldn’t be imported).
> If you want to review the details of the campaigns and make changes, click **View imported campaigns**.
> If you want to sync multiple Google Ads accounts into Microsoft Advertising, treat each Google Ads account as a separate import. It is recommended that you wait at least a 2-hour time difference between each import to insure their completion.

Learn more about [ad customizer feeds](./hlp_BA_CONC_Feeds_AdCustomizers.md) and [what gets imported from Google Ads      ](./hlp_BA_CONC_ImportWhatInfo.md).


