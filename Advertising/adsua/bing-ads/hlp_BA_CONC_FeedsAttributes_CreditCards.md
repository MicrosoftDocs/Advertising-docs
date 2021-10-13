---
title: Credit card ads' dynamic data feeds
description: Get details about required, recommended, and optional Credit card ads feed attributes.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Credit card ads' dynamic data feeds

A dynamic feed file is a spreadsheet that contains attributes. This file tells Microsoft Advertising the information you want inserted in your ads and under which condition each attribute should be inserted. Some attributes will be featured in the ad itself.

**Upload a feed file**
1. [!INCLUDE [BusinessDataDynamicDataFeeds](./includes/BusinessDataDynamicDataFeeds.md)]
1. Select **Upload** > **Credit cards**.
1. Enter the **Name** and select the feed file to upload.
1. [!INCLUDE [UploadPreviewUploadApply](./includes/UploadPreviewUploadApply.md)]

[!INCLUDE [ScheduleYourFeedFile](./includes/ScheduleYourFeedFile.md)]
## Dynamic feed file attributes

Your dynamic feed file is a spreadsheet comprised of attributes, which we use to generate your ads. Below is a list of required, recommended, and optional attributes for [Credit card ads'](./hlp_BA_CONC_Feeds_CreditCards.md) feed files.

Your feed file should be tab-delimited plain text saved as any of the following file types: CSV, TSV, XLSX, or ZIP.

## Required attributes

Your dynamic data feed file must include the following attributes:

|Attribute|Description|Example|
|---|---|---|
|```Card issuer```|The issuer of the credit card.|Contoso Bank|
|```Card network```|The credit card network.|```VISA```|
|```Card title```|The full title of the card type.|```Citi Simplicity Card```|
|```Final URL```|The same domain as your website. Must begin with http:// or https://.This will not be shown in the ad.|```http://www.contoso.com/seattle/id```|
|```ID```|Unique ID of the item comprised of any sequence of letters and digits.This will not be shown in the ad.|```AB1234```|
|```Target campaign```|The name of the targeted Credit card ads campaign.In addition to targeting a campaign, you can also target a specific ad group within the campaign. See Target ad group below.This will not be shown in the ad.|```Contoso_Card```|

## Recommended attributes

Your dynamic data feed file may include any of the following attributes, which we highly recommend:

|Attribute|Description|Example|
|---|---|---|
|```Annual fee```|The annual fee for the card.|```0 USD```|
|```Card callout```|Can be used to call out special attributes about the product.|Earn cash back TWICE. Earn 2% on purchases with 1% cash back when you buy, plus an additional 1% as you pay for those purchases.|
|```Card category```|List of categories for the item (if applicable), separated by “;”.|```Rewards; Cash back```|
|```Card description```|The overall description of the card.|Build your own credit with responsible use. Refundable deposit of $49 required.|
|```Cash back percent```|Percent of cash back offered for the credit card.|3% in the category of your choice|
|```Credit level needed```|The necessary credit level.|```Excellent```|
|```Intro balance APR```|Introduction balance transfer APR.|```0.1099```|
|```Intro balance transfer APR months```|Months that have intro balance transfer APR.|```14```|
|```Intro purchase APR```|Introduction purchase APR.|```0%```|
|```Intro purchase APR months```|The number of months that have introduction purchase APR.|```12```|
|```Regular balance transfer APR```|Balance transfer APR.|```0.1099```|
|```Regular purchase APR```|A range of regular purchase APR depending on credit level.|```15.99%-24.99% variable APR```|
|```Rewards```|An explanation of the rewards.|Earn double ThankYou® Points at supermarkets and gas stations for the first $6,000 per year—and earn a 10% bonus on the first 100,000 ThankYou® Points you redeem each year.|
|```Sign up bonus```|A description of the benefits of signing up for the credit card offers.|15,000 bonus points after qualifying purchase|
|```Target ad group```|The name of the targeted ad group.If you don't specify a target ad group, we will apply this feed to all ad groups in your targeted campaign. See Target campaign above.This will not be shown in the ad.|```Credit-Cards-Placement-AdGroup1```|

## Optional attributes

Your dynamic data feed file may include any of the following optional attributes:

|Attribute|Description|Example|
|---|---|---|
|```Contextual keywords```|Any sequence of letters and digits separated by ";". If provided, the information in this column will help the Microsoft AI create more relevant ads for your campaign.|```Contoso card, Contoso travel credit card, travel credit card```|
|```Custom parameters```|Include up to three key and value pairs, which automatically fill up in the click URL.List the key and value pairs within braces. Each term should be set in quotation marks. Separate each phrase of the pair with a colon and separate key and value pairs with commas and without any spaces.The maximum limit is 16 characters or 200 bytes.This will not be shown in the ad.|```{“pcategory”:”cashback”}```|
|```Description```|A short description of the item that appears in the ad.|```Contoso card```|
|```Final mobile URL```|The item’s mobile-optimized landing page when you have a different URL for mobile and desktop traffic.This will not be shown in the ad.|```http://www.m.contoso.com/asp/sp.asp?id=abc123```|
|```Image URLs```|The URLs for the image used in your ad. Must begin with http:// or https://.We support BMP, GIF, JPG, or PNG (recommended), all of which must be saved in RGB color code with an ICC profile.The recommended aspect ratio: 1.59:1.The minimum image size: 476 x 249 pixels. We recommend that you upload the largest possible image.|```http://www.contoso.com/image1.png```|
|```Min credit```|The minimum credit limit for the card.This will not be shown in the ad.|```500```|
|```Max credit```|The maximum credit limit for the card.This will not be shown in the ad.|```850```|
|```Num of reviews```|The number of reviews for the item in numerical value.|```12500```|
|```Rating```|The rating for the item on a scale of 0-5.|```4.5```|
|```Tracking template```|Include any tracking parameters, custom parameters, or tracking redirects for your item URL.This will not be shown in the ad.|```http://www.trackingtool.com/?source=Microsoft&amp;pcategory={_pcategory}&amp;city={_city} ```|
|```Video URLs```|The URL for the video used in your ad. Must begin with http:// or https://.We support: MPG, MP4, AVI, etc.|```http://www.contoso.com/video1.mpg```|


