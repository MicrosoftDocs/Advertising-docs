---
title: FAQ: Expanded text ads
description: Expanded Text Ads give you additional content to make your ads more eye-catching and helpful.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# FAQ: Expanded text ads

## What are Expanded text ads?

Expanded text ads are a mobile-optimized ad format that enables you to craft longer ad copy and optimize your ad text to better engage with potential customers before they click on your ads. Expanded text ads work seamlessly on mobile, tablet, and desktop devices, giving you a way to create more compelling calls to action for consumers and drive higher conversions to your business.

Here's how expanded text ads compare to standard text ads:

|Ad part|Standard text ads|Expanded Text Ads|
|---|---|---|
|Ad title|25 characters|90 characters: Supports three headlines, up to 30 characters each, separated by a space, vertical bar, and space (" | ")|
|Ad text|71 characters|180 characters: Supports two descriptions, up to two 90 characters each|
|Display URL|35 characters, manually entered and error-prone|Domain and subdomain automatically generated from your final URL (preserving capitalization) plus two customizable URL paths|

## How do I set up expanded text ads?

1. [!INCLUDE [AdsExtensionsAds](./includes/AdsExtensionsAds.md)]
1. Select **Create ad**.
1. Choose an ad group for which you want to create an ad.
1. For **Ad type**, select **Expanded text ad**.
1. Enter your landing page URL in the **Final URL** box.
**Note:** Your **Final URL** — including prefix (e.g., "www."), suffix (e.g., ".com"), and any [tracking templates](./hlp_BA_CONC_GoogleAnalytics.md)&nbsp;— must be no longer than 2048 characters. However, your final URL **domain**, or everything in your final URL before the first slash or tracking template, must be no longer than 67 characters.

1. Enter your **Title**. You can enter three parts of your ad title, each up to 30 characters long. The third title is optional.
1. Enter your **Ad text**. You can have two parts of your ad text description, each up to 90 characters long. The second ad text description is optional.
1. Enter your **Mobile URL** if you have one.
1. Select the **Ad URL options** dropdown menu unless you choose to stick with the default options.
1. Select **Save**.

## What are the character limits for expanded text ads?

|Text field|Character limit|
|---|---|
|Final URL|2048 characters, including prefix (e.g., "www."), suffix (e.g., ".com"), and tracking templates|
|Titles|30 characters each, up to three ad titles|
|Ad text|90 characters each, up to two ad descriptions|
|Paths|15 characters each**Note:** All together, the final URL domain (everything in your final URL before the first slash or tracking template) and paths cannot exceed 67 characters.|

**Note**: Keep in mind that the total length of the potential dynamic text, includes Param1, Param2, Param3, and DKIs. It is possible to create ad titles, ad text, and URLs that fit within our character limits when you create them, but that could become too long when the dynamic text is applied. In such cases, the system may consider a total length check of 90 characters for the **Title**, 67 characters for the **Display URL**, and 180 characters for the **Ad text** (excluding separators) or it may use the default text as what is deemed fit based on predicted responses, device length limits, and more.

> [!IMPORTANT]
> Double-width characters—such as Chinese characters — count as two characters each.

## Are Upgraded URLs required in order to use expanded text ads?

Upgraded URLs are now generally available for all customers worldwide; but, it is not required to migrate all your existing URLs, which include standard text ad URLs, keyword destination URLs, and Sitelink Extension URLs, to start taking advantage of expanded text ads. You are still able to manage and optimize standard text ads using destination URLs and set up new expanded text ads using final URLs. We do recommend setting up an account-level tracking template to ensure that you can properly track and report your ad clicks.

[Learn more about Upgraded URLs](./hlp_BA_CONC_UpgradeURL_MigrateFAQ.md)

## Can I import only my expanded text ads from Google Ads?

Yes, if you want to import only expanded text ads from Google Ads, Microsoft Advertising Editor is the right tool. In Microsoft Advertising Editor, you can either:

1. Run **Import** from Google Ads to stage all your Google Ads changes locally.
1. Revert all changes except those related to expanded text ads.
1. Post only changes to expanded text ads.

## Can I use {param1}, {param2}, and {param3} for keyword tracking in expanded text ads?

Yes, you can add a {param} to a domain in the Final URL box, but you cannot have your Final URL be only a {param}. In other words, in the Final URL box, “contoso.com/{param1}” is allowed, but just “{param1}” is not. {param1}, {param2}, and {param3} are also still allowed in ad titles and descriptions.

## Will expanded text ads work with all my existing ad extensions?

Yes, all ad extensions and automated extensions will continue to work as expected. We recommend setting up expanded text ads in the same campaigns and ad groups as your existing standard text ads so you can use your existing ad extensions. [Learn more about ad extensions](./hlp_BA_CONC_AboutAdExtensions.md)

## Which part of my domain is auto-generated from the Final URL?

Microsoft Advertising will automatically use the domain of the URL that is entered, including its subdomains. See the table below for examples.

|Advertiser-entered final URL|Microsoft Advertising will display|
|---|---|
|http://contoso.com/contact.html|contoso.com|
|http://www.contoso.com/contact.html|www.contoso.com|
|http://ContosoStore.com/contact.html|ContosoStore.com|
|http://www.ContosoStore.com/contact.html|www.ContosoStore.com|
|http://Store.Contoso.com/contact.html|Store.Contoso.com|

> [!NOTE]
> Your final URL’s domain—including prefix (e.g., "www.") and suffix (e.g., ".com")—must be no longer than 67 characters.

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
> Your final URL’s domain—including prefix (e.g., "www.") and suffix (e.g., ".com")—must be no longer than 67 characters.

## How does Microsoft Advertising auto-generate display URL domains with expanded text ads?

|Advertiser-entered final URL|Microsoft Advertising will display|
|---|---|
|http://contoso.com/contact.html|contoso.com|
|http://www.contoso.com/contact.html|www.contoso.com|
|http://ContosoStore.com/contact.html|ContosoStore.com|
|http://www.ContosoStore.com/contact.html|www.ContosoStore.com|
|http://Store.Contoso.com/contact.html|Store.Contoso.com|

> [!NOTE]
> Your final URL’s domain—including prefix (e.g., "www.") and suffix (e.g., ".com")—must be no longer than 67 characters.

## Which reports have columns for Ad Title 1, Ad Title 2, and Ad Title 3 for expanded text ads?

The Ad performance report shows these columns by default. They are also available in the Ad dynamic text and Ad extension by ad report.


