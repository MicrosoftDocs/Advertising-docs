---
title: FAQ: Expanded Text Ads
description: Expanded Text Ads give you additional content to make your ads more eye-catching and helpful.
ms.service: "Bing-Ads-Editor-v11"
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
|Ad title|25 characters|90 characters (supports three headlines, up to 30 characters each, separated by a vertical bar (|).)|
|Ad text|71 characters|180 characters (supports two descriptions, up to two 90 characters each.)|
|Display URL|35 characters, manually entered and error-prone|Domain and subdomain automatically generated from your final URL (preserving capitalization) plus two customizable URL paths.|

## How do I set up Expanded Text Ads?
1. From the **Ads** tab, click **Create ad** and then select an ad group.
1. For **Ad type**, select **Expanded Text Ad**.
1. Enter your landing page URL in the **Final URL** box. **Note** : Your final URL — including prefix (e.g., "www."), suffix (e.g., ".com"), and any tracking templates&nbsp;— must be no longer than 2048 characters. However, your final URL **domain** (everything in your final URL before the first slash or tracking template) must be no longer than 67 characters.
1. Unlike standard text ads, you can then enter three parts of your ad title, each up to 30 characters long.
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

> [!IMPORTANT]
> Keep in mind that double-width characters — such as Chinese characters — count as two characters each.

## Are Upgraded URLs required in order to use Expanded Text Ads?
Upgraded URLs are now generally available for all customers worldwide but it is not required to migrate all your existing URLs, which include standard text ad URLs, keyword destination URLs, and Sitelink Extension URLs, to start taking advantage of Expanded Text Ads. You are still able to manage and optimize standard text ads using destination URLs and set up new Expanded Text Ads using final URLs. We do recommend setting up an account-level tracking template to ensure that you can properly track and report your ad clicks.

## Will standard text ads be migrated to Expanded Text Ads?
No, there is no migration from standard text ads to Expanded Text Ads. Expanded Text Ads are a new, mobile-optimized ad format that enables you to craft longer ad copy and optimize your ad text to better engage with potential customers before they click on your ads.

## Should I run standard text ads in campaigns and ad groups simultaneously with the new Expanded Text Ads?
Yes, we strongly recommend you leave your current ads running as you are onboarding your campaigns to Expanded Text Ads. We recommend a 1:1 ratio of standard text ads to Expanded Text Ads. If you pause your standard text ads, you will see a drop in impressions.

## Will Expanded Text Ads appear in the same ad positions as standard text ads?
Yes, Expanded Text Ads will appear in all of the ad positions that standard text ads currently do.

## What can I do to maximize Expanded Text Ads impressions?
Once your Expanded Text Ads are set up, there should not be any immediate action on your side.

To start with, your Expanded Text Ads will have equal chance of getting an impression as standard text ads. We recommend you create as many Expanded Text Ads as you have standard text ads in each ad group to have a balanced distribution of ad types.

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

**Note** : Keep in mind the length of the potential dynamic text a {param} might cause. It is possible to create ad titles, ad text, and URLs that fit within our character limits when you create them, but that become too long when the dynamic text is applied. In this case, the ad will not be considered for auction.

## Will Expanded Text Ads work with all my existing ad extensions?
Yes, all ad extensions and annotations will continue to work as expected. We recommend setting up Expanded Text Ads in the same campaigns and ad groups as your existing standard text ads so you can use your existing ad extensions.

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

 

