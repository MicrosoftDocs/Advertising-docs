---
title: About ad extensions
description: Add additional information about your business to your ads with ad extensions.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# About ad extensions

Ad extensions are additional pieces of information about your business that you can add to your ads, such as a phone number or a link to a specific page on your website. Ad extensions are free to add and only charge for any clicks you get. Including ad extensions can improve the visibility of your ads, which can lead to more clicks and improve your return on investment.

Our algorithms optimize and balance the needs of users, advertisers, and constraints of the search results page. Our algorithms choose the best layout for each ad by evaluating hundreds of possible combinations based on all available extension data, allocated space, and the positive impact it can provide for advertiser and user. Standard performance reports are also available for all extensions. Learn how to [create a report](./hlp_BA_PROC_CreateReport.md).

Even if an ad extension is eligible to serve, it's not always guaranteed to serve. Whether an extension serves depends on a number of factors. Here are a few listed below:

- The relevance and quality of your ad
- The relevance and quality of the extension data provided
- Ad space availability on the page
- User signals, like location, device used, etc.
- Other extensions you enabled for your ad
- Availability of extension data for competing ads

> [!NOTE]
> **Best practice:**  Providing extension data allows our algorithms to evaluate all the possible layouts for your ad. It increases the chances of additional space being allocated and increasing clicks for your ad.

## Ad extension types

Microsoft Advertising supports the ad extension types as summarized below. See the **Learn more**  links for details about each extension and availability per market.

- **Action extension:**  An action extension is a call-to-action button in your text ad. You can select from a preset list of action types, which will then add a button to your ad that allows customers to interact with the ad to place an order, send a message, and more. [Learn more](./hlp_BA_PROC_AddActionExtension.md)
- **App extension:**  Add an app extension to promote your apps across PCs, tablets, and smartphones from your ad. Promoting app installs in your ad increases downloads and usage of your apps, as well as website visits. Unlike sitelink extensions, app extensions automatically detect a customer's device and operating system and take them directly to the correct app store. [Learn more](./hlp_BA_CONC_AdExtensionAppExtension.md)
- **Call extension:**  By using a call extension, you can provide a phone number that is not associated with a particular location, but is appropriate for all locations where your ads display. [Learn more](./hlp_BA_PROC_AddCallExtension.md)
- **Callout extension:**  Callout extensions provide an extra snippet of text that highlights your website’s products or offers. This extension is not clickable and can appear in addition to your ad’s description. Providing additional details about your website can make your ad more relevant to potential customers. [Learn more](./hlp_BA_PROC_AddCalloutExtension.md)
- **Dynamic data sitelink extension:**  Dynamic data sitelink extensions make showcasing your products and services automatic—even when your inventory changes frequently. This extension makes it easy to update your search ads with one feed file to display up-to-date product information specific to customer searches. [Learn more](./hlp_BA_PROC_AddDynamicDataSitelinkExtension.md)
- **Filter link extension:**  Use filter link extensions to list multiple categories of products or features with unique links to each of these offerings. Easily combined with other extensions, filter link extensions can enlarge your ad format even further and present multiple avenues to different parts of your site, in addition to your final URL. [Learn more](./hlp_BA_PROC_AddFilterLinkExtension.md)
- **Image extension:**  Add visual elements to your ad with image extensions. Providing visual elements to your ads helps them stand out and also gives customers a better idea of what to expect when they click your ad. [Learn more](./hlp_BA_PROC_AddImageExtension.md)
- **Location Extension:**  When you enable a location extension, you can choose to show the address of your business location that is closest to the customer and also include a local phone number. Better yet, if the customer is viewing your ad on a smartphone, they can click that number to give you a call. [Learn more](./hlp_BA_PROC_AddLocationExtension.md)
- **Price extension:**  Price extensions are pay-per-click extensions that display your products or services with their corresponding prices to potential customers on PC and mobile devices. [Learn more](./hlp_BA_PROC_AddPriceExtension.md)
- **Promotion extension:**  Use promotion extensions to highlight deals for holidays and other special occasions. If you, for instance, want to highlight a Summer Sale using promotion extensions, you can include a promotion code along with the offer and expiration date. [Learn more](./hlp_BA_PROC_AddPromotionExtension.md)
- **Review extension:**  Potential customers like to know about other customers’ experiences when searching for products or services. Share positive reviews from a reputable third-party source about your website in your ads with a review extension. You can paraphrase or use a direct quote from the source. [Learn more](./hlp_BA_PROC_AddReviewExtension.md)
- **Sitelink extension:**  Sitelink extensions are additional links in your ads that take customers to specific pages on your website. This allows you to promote certain products, services, or sections of your website and take potential customers to the exact information they were searching for. This can increase both click-through-rate and conversions. [Learn more](./hlp_BA_PROC_AddSitelinkExtension.md)
- **Structured snippet extension** : Give potential customers more context on a specific aspect of your products and services. [Learn more](./hlp_BA_PROC_AddStructuredSnippetExtension.md)
- **Video extension** : Video extensions are an interactive way to demonstrate products, services, and brand messages. [Learn more](./hlp_BA_PROC_AddVideoExtension.md)

See the sections below for the steps to create and associate ad extensions with accounts, campaigns, and ad groups.

## Create a new ad extension

Ad extensions can be created at the **Account**, **Campaign**, and **Ad Group** levels. As described in the steps below, choose **Account** to associate the extension with your account, and then you can associate the extension with campaigns and ad groups later as needed.

The steps to create ad extensions is the same for each ad extension type, with this exception: Call extensions can only be associated with campaigns and aren't shown at the account or ad group level. Follow the example steps below to associate a promotion extension.

1. [!INCLUDE [AdsExtensionsExtensions](./includes/AdsExtensionsExtensions.md)]
1. Select **Account** to associate the extension with your account.
**Note:** You can associate extensions with campaigns and ad groups later as needed.

1. From the extensions dropdown list box, select **Promotion Extensions**.
1. Select **Create Ad Extension** > **Add new Promotion Extension**.
1. Enter the extension details in the **Add new Promotion Extension** panel that opens on the right.
1. Select **Save**. The new extension is added and shown in the **Selected Promotion Extensions** list.
1. On the main page, select **Save** to finish adding the extension to your account.

> [!NOTE]
> On the same page, you can select the checkbox next to an ad extension and then edit or delete it.

## Associate an ad extension with accounts, campaigns, and ad groups

Associations at the lowest level of account, campaign, and ad group hierarchy will be honored. For example, if you associate promotion extension 123 at the account level and then associate promotion extension 456 at the campaign level, the account level association is outranked. If you associate promotion extension 789 at the ad group level it will be used instead of the account or campaign level associations.

As described in the steps below, choose the **Campaign** or **Ad Group** level to associate an ad extension with campaigns or ad groups.

> [!NOTE]
> Call extensions can only be associated with campaigns and they are only shown at the **Campaign** level.

1. [!INCLUDE [AdsExtensionsExtensions](./includes/AdsExtensionsExtensions.md)]
1. Select **Campaign** to associate an extension with campaigns or you can select **Ad Group** to associate an extension with ad groups.
1. From the extensions dropdown list box, select **Promotion Extensions**.
1. Select **Create Ad Extension** and then select the campaign(s) or ad group(s) you want to add the extension(s) to.
1. Select **Done**.
1. From the **Available Promotion Extensions** list, select the extension(s) that you want to associate with the campaign(s) or ad group(s). Optionally, you can create a new extension and then select it from the list.
1. Select **Save** to apply the association.

## Ad extension association limits

An account can contain up to 200,000 sitelink extensions and can contain up to 150,000 ad extensions of all other types combined. The entity (account, campaign, or ad group) to ad extension association limit varies by the extension type.

|Ad extension type|Association limit per entity|
|---|---|
|Action extension|20|
|App extension|Up to the total number of app extensions in your account|
|Call extension|1|
|Callout extension|20|
|Filter link extension|20|
|Image extension|6|
|Location extension|Up to the total number of location extensions in your account|
|Price extension|20|
|Promotion extension|20|
|Review extension|20|
|Sitelink extension|20|
|Structured snippet extension|20|

> [!NOTE]
> Want expert advice on your ads? [Schedule a no-cost session with a personal Microsoft Advertising consultant](https://go.microsoft.com/fwlink?LinkId=837456)


