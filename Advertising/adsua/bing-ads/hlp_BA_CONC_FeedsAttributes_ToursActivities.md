---
title: Tours and activities ads' dynamic data feeds
description: Get details about required, recommended, and optional feed attributes for Tours and activities ads.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Tours and activities ads' dynamic data feeds

A dynamic feed file is a spreadsheet that contains attributes. This file tells Microsoft Advertising the information you want inserted in your ads and under which condition each attribute should be inserted. Some attributes will be featured in the ad itself.

**Upload a feed file**
1. [!INCLUDE [BusinessDataDynamicDataFeeds](./includes/BusinessDataDynamicDataFeeds.md)]
1. Select **Upload** > **Tours and activities**.
1. Enter the **Name** and select the feed file to upload.
1. [!INCLUDE [UploadPreviewUploadApply](./includes/UploadPreviewUploadApply.md)]

[!INCLUDE [ScheduleYourFeedFile](./includes/ScheduleYourFeedFile.md)]
## Dynamic feed file attributes

Your dynamic feed file is a spreadsheet comprised of attributes, which we use to generate your ads. Below is a list of required, recommended, and optional attributes for [Tours and activities ads'](./hlp_BA_CONC_Feeds_ToursActivities.md) feed files.

Your feed file should be tab-delimited plain text saved as any of the following file types: CSV, TSV, XLSX, or ZIP.

## Required attributes

Your dynamic data feed file must include the following attributes:

|Attribute|Description|Example|
|---|---|---|
|```Final URL```|The same domain as your website. Must begin with http:// or https://.This will not be shown in the ad.|```http://www.contoso.com/seattle/id```|
|```ID```|Unique ID of the item comprised of any sequence of letters and digits.This will not be shown in the ad.|```AB1234```|
|```Starting Price```|Starting price for the item. Numeric value followed by currency code (ISO 4217 standard). Use “.” as the decimal mark regardless of the local currency.|```200.00 USD```|
|```Target campaign```|The name of the targeted Tours and activities ads campaign.In addition to targeting a campaign, you can also target a specific ad group within the campaign. See Target ad group below.This will not be shown in the ad.|```EMDB_Tours```|
|```Title```|The title of the item.|```Contoso Wine Tour```|

## Recommended attributes

Your dynamic data feed file may include the following attributes, which we highly recommend:

|Attribute|Description|Example|
|---|---|---|
|```Duration```|The duration of the item in DD:HH:MM format.|```02:03:30```|
|```Image URLs```|The URLs for the image used in your ad. Must begin with http:// or https://.If you are listing multiple Image URLs, use a semicolon (;) as delimiter.We support BMP, GIF, EXIF, JPG, PNG (recommended), or TIFF. Both JPG and GIF must be saved in RGB color code with an ICC profile.The recommended image size: 1200 x 628 pixels.The recommended aspect ratio: 1.91:1.The minimum image size: 476 x 249 pixels. We recommend that you upload the largest possible image.|```http://www.contoso.com/image1.png```|
|```Num of reviews```|The number of reviews for the item in numerical value.|```12500```|
|```Primary categories```|Categories and subcategories that the item belongs to. Multiple categories can be provided, separated by “;”.|```Food &amp; Wine; Wine Tasting```|
|```Provider```|The name of the provider or seller of the item.|```Contoso Winery```|
|```Rating```|The rating for the item on a scale of 0-5.|```4.5```|
|```Target ad group```|The name of the targeted ad group.If you don't specify a target ad group, we will apply this feed to all ad groups in your targeted campaign. See Target campaign above.This will not be shown in the ad.|```Tours-Activities-Ads-Placement_AdGroup1```|

## Optional attributes

Your dynamic data feed file may include any of the following optional attributes:

|Attribute|Description|Example|
|---|---|---|
|```Attractions```|List of attractions for the item (if applicable), separated by “;”.|```Winery; Wine Cellar; Wine Tour```|
|```Contextual keywords```|Any sequence of letters and digits separated by ";". If provided, the information in this column will help the Microsoft AI create more relevant ads for your campaign.This will not be shown in the ad.|```Woodinville Winery; Wine Tours; Wine Cellar```|
|```Custom parameter```|Include up to 3 key and value pairs, which automatically fill up in the click URL.List the key and value pairs within braces. Each term should be set in quotation marks. Separate each phrase of the pair with a colon and separate key and value pairs with commas and without any spaces.The maximum limit is 16 characters or 200 bytes.This will not be shown in the ad.|```{“city”:”Seattle”, “pcategory”:”daytours”}```|
|```Description```|A short description of the item that appears in the ad.|Sample the Pacific Northwest's most delicious red and white wines.|
|```Destination address```|Either provide the first line of the street address or the full address. If only the street address is provided, fill in the city, state, and zip code as other attributes.|```123 Contoso Ave```or```123 Contoso Ave, Bellevue, WA 98004```|
|```Destination city```|The item's destination city.|```Seattle```|
|```Destination country```|The item's destination country.|```United States```|
|```Destination ID```|A unique ID comprised of any sequence of letters and digits of the destination or geo at the city level.This will not be shown in the ad.|```GEO123```|
|```Destination name```|The name of the location users will be visiting.|```Contoso Wine Garden```|
|```Destination state```|The item's destination state or province.|```Washington```|
|```Final mobile URL```|The item’s mobile-optimized landing page when you have a different URL for mobile and desktop traffic.This will not be shown in the ad.|```http://www.m.contoso.com/asp/sp.asp?id=abc123```|
|```Is best seller```|Use true or false to indicate if the item is best seller.|```TRUE```|
|```Is hotel pickup available```|Use true or false to indicate if hotel pick-up is available.|```FALSE```|
|```Is likely to sell out```|Use true or false to indicate if the item is likely to sell out.|```TRUE```|
|```Related categories```|Other top-level categories that the item might belong to.|```Wine Tasting```|
|```Similar destination IDs```|Similar destination IDs at the city-level related to this item. Multiple destination IDs should be separated by ";".This will not be shown in the ad.|```GEO456; GEO789```|
|```Starting sale price```|The starting sale price for the item. “Starting sale price” values should be less than “Starting price”. If provided, sale price will be used.Numeric value followed by currency code (ISO 4217 standard). Use “.” as the decimal mark regardless of the local currency.|```15.00 USD```|
|```Tracking template```|Include any tracking parameters, custom parameters, or tracking redirects for your item URL.This will not be shown in the ad.|```http://www.trackingtool.com/?source=Microsoft&amp;pcategory={_pcategory}&amp;city={_city}```|
|```Video URLs```|The URL for the video used in your ad. Must begin with http:// or https://.We support: MPG, MP4, AVI, etc.|```http://www.contoso.com/video1.mpg```|


