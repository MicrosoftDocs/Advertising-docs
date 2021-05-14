---
title: Tours and Activities ads: Highlight specific tours and activities
description: Tours and Activities ads are interactive premium ad types in which you can include images, current prices, reviews, and other relevant details to make your ads inviting and engaging.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Tours and Activities ads: Highlight specific tours and activities

> [!NOTE]
> Not everyone has this feature yet. If you don't, don't worry—it's coming soon!

Tours and Activities ads are interactive premium ad types in which you can include images, current prices, reviews, and other relevant details to make your ads inviting and engaging. These ads are created dynamically after uploading a unique feed file that may contain additional details such as sale price, videos, and ratings. The more details you provide into the feed file, the more information we’ll include into your ads.

## The benefits of using Tours and Activities ads

- **Customized ads.** Submit and schedule your feed and based on the attributes you provide, we’ll create relevant, personalized ads.
- **Improved return on ad spend.** See more volume, increased click-through rates (CTR), and lower cost per click (CPC) rates.
- **Save time with automation.** With no keywords required, the ads are created by feed files that use Microsoft AI automation and are fully equipped for bulk upload.

## Create Tours and Activities ads with business data feeds

To get started with Tours and Activities ads, you should first create a search ad campaign with a single placeholder ad group, keyword, and ad. Once you have your campaign(s) set up, you can upload and schedule your feed.

A dynamic feed file is a spreadsheet that contains attributes. This file tells Microsoft Advertising the information you want inserted in your ads and under which condition each attribute should be inserted. Some attributes will be featured in the ad itself.

Your feed file should be tab-delimited plain text with any of the following extensions: CSV, TSV, XLSX, or ZIP.

## Required attributes
Your dynamic data feed file must include the following attributes:

<table>
  <tr>
    <th scope="col">Attribute</th>
    <th scope="col">Description</th>
    <th scope="col">Example</th>
  </tr>
  <tr>
    <td>```Final URL```</td>
    <td>The same domain as your website. Must begin with http:// or https://.
									 
									 This will not be shown in the ad.
									</td>
    <td>```http://www.contoso.com/seattle/id```</td>
  </tr>
  <tr>
    <td>```ID```</td>
    <td>Unique ID of the item comprised of any sequence of letters and digits.
									 
									 This will not be shown in the ad.</td>
    <td>```AB1234```</td>
  </tr>
  <tr>
    <td>```Starting Price```</td>
    <td>Starting price for the item. Numeric value followed by currency code (ISO 4217 standard). Use “.” as the decimal mark regardless of the local currency.</td>
    <td>```200.00 USD```</td>
  </tr>
  <tr>
    <td>```Title```</td>
    <td>The title of the item.
									</td>
    <td>```Contoso Wine Tour```</td>
  </tr>
</table>

## Recommended attributes
Your dynamic data feed file may include the following attributes, which we highly recommend:

<table>
  <tr>
    <th scope="col">Attribute</th>
    <th scope="col">Description</th>
    <th scope="col">Example</th>
  </tr>
  <tr>
    <td>```Duration```
									</td>
    <td>The duration of the item in DD:HH:MM format.</td>
    <td>```02:03:30```</td>
  </tr>
  <tr>
    <td>```Image URLs```
									</td>
    <td>The URLs for the image used in your ad. Must begin with http:// or https://. 
									 
									 We support BMP, GIF, EXIF, JPG, PNG (recommended), or TIFF. Both JPG and GIF must be saved in RGB color code with an ICC profile. 
									 
									 The recommended image size: 1200 x 628 pixels.
									 
									 The recommended aspect ratio: 1.91:1.
									 
									 The minimum image size: 476 x 249 pixels. We recommend that you upload the largest possible image. </td>
    <td>```http://www.contoso.com/image1.png```</td>
  </tr>
  <tr>
    <td>```Num of reviews```</td>
    <td>The number of reviews for the item in numerical value.</td>
    <td>```12500```</td>
  </tr>
  <tr>
    <td>```Primary categories```
									</td>
    <td>Categories and subcategories that the item belongs to. Multiple categories can be provided, separated by “;”.</td>
    <td>```Food &amp; Wine; Wine Tasting```</td>
  </tr>
  <tr>
    <td>```Provider```
									</td>
    <td>The name of the provider or seller of the item.</td>
    <td>```Contoso Winery```</td>
  </tr>
  <tr>
    <td>```Rating```
									</td>
    <td>The rating for the item on a scale of 0-5.</td>
    <td>```4.5```</td>
  </tr>
  <tr>
    <td>```Target ad group```</td>
    <td>The name of the targeted Tours and Activities ad group.
									 
									 This will not be shown in the ad.</td>
    <td>```Tours-Activities-Ads-Placement_AdGroup1```</td>
  </tr>
  <tr>
    <td>```Target campaign```</td>
    <td>The name of the targeted Tours and Activities campaign.
									 
									 This will not be shown in the ad.</td>
    <td>```EMDB_Tours```</td>
  </tr>
</table>

## Optional attributes
Your dynamic data feed file may include the following optional attributes:

<table>
  <tr>
    <th scope="col">Attribute</th>
    <th scope="col">Description</th>
    <th scope="col">Example</th>
  </tr>
  <tr>
    <td>```Attractions```</td>
    <td>List of attractions for the item (if applicable), separated by “;”.</td>
    <td>```Winery; Wine Cellar; Wine Tour```</td>
  </tr>
  <tr>
    <td>```Contextual keywords```</td>
    <td>Any sequence of letters and digits separated by ";". If provided, the information in this column will help the Microsoft AI create more relevant ads for your campaign.
									 
									 This will not be shown in the ad.
									</td>
    <td>```Woodinville Winery; Wine Tours; Wine Cellar```</td>
  </tr>
  <tr>
    <td>```Custom parameter```</td>
    <td>Include up to 3 key and value pairs, which automatically fill up in the click URL. 
									 
									 List the key and value pairs within braces. Each term should be set in quotation marks. Separate each phrase of the pair with a colon and separate key and value pairs with commas and without any spaces. 
									 
									 The maximum limit is 16 characters or 200 bytes.
									 
									 This will not be shown in the ad.
									</td>
    <td>```{“city”:”Seattle”, “pcategory”:”daytours”}```</td>
  </tr>
  <tr>
    <td>```Description```</td>
    <td>A short description of the item that appears in the ad.</td>
    <td>Sample the Pacific Northwest's most delicious red and white wines.</td>
  </tr>
  <tr>
    <td>```Destination address```</td>
    <td>Either provide the first line of the street address or the full address. If only the street address is provided, fill in the city, state, and zip code as other attributes.</td>
    <td>```123 Contoso Ave```
									 or
									 ```123 Contoso Ave, Bellevue, WA 98004```</td>
  </tr>
  <tr>
    <td>```Destination city```</td>
    <td>The item's destination city.</td>
    <td>```Seattle```</td>
  </tr>
  <tr>
    <td>```Destination country```</td>
    <td>The item's destination country.</td>
    <td>```United States```&gt;</td>
  </tr>
  <tr>
    <td>```Destination ID```</td>
    <td>A unique ID comprised of any sequence of letters and digits of the destination or geo at the city level.
									 
									 This will not be shown in the ad.
									</td>
    <td>```GEO123```</td>
  </tr>
  <tr>
    <td>```Destination name```</td>
    <td>The name of the location users will be visiting.</td>
    <td>```Contoso Wine Garden```</td>
  </tr>
  <tr>
    <td>```Destination state```</td>
    <td>The item's destination state or province.</td>
    <td>```Washington```</td>
  </tr>
  <tr>
    <td>```Final mobile URL```</td>
    <td>The item’s mobile-optimized landing page when you have a different URL for mobile and desktop traffic.
									 
									 This will not be shown in the ad.</td>
    <td>```http://www.m.contoso.com/asp/sp.asp?id=abc123```</td>
  </tr>
  <tr>
    <td>```Is best seller```</td>
    <td>Use true or false to indicate if the item is best seller.</td>
    <td>```TRUE```</td>
  </tr>
  <tr>
    <td>```Is hotel pickup available```</td>
    <td>Use true or false to indicate if hotel pick-up is available.</td>
    <td>```FALSE```</td>
  </tr>
  <tr>
    <td>```Is likely to sell out```</td>
    <td>Use true or false to indicate if the item is likely to sell out.</td>
    <td>```TRUE```</td>
  </tr>
  <tr>
    <td>```Related categories```</td>
    <td>Other top-level categories that the item might belong to.</td>
    <td>```Wine Tasting```</td>
  </tr>
  <tr>
    <td>```Similar destination IDs```</td>
    <td>Similar destination IDs at the city-level related to this item. Multiple destination IDs should be separated by ";".
									 
									 This will not be shown in the ad.</td>
    <td>```GEO456; GEO789```</td>
  </tr>
  <tr>
    <td>```Starting sale price```</td>
    <td>The starting sale price for the item. “Starting sale price” values should be less than “Starting price”. If provided, sale price will be used.
									 
									 Numeric value followed by currency code (ISO 4217 standard). Use “.” as the decimal mark regardless of the local currency.</td>
    <td>```15.00 USD```</td>
  </tr>
  <tr>
    <td>```Tracking template```</td>
    <td>Include any tracking parameters, custom parameters, or tracking redirects for your item URL.
									 
									 This will not be shown in the ad.</td>
    <td>```http://www.trackingtool.com/?source=Microsoft&amp;pcategory={_pcategory}&amp;city={_city}```</td>
  </tr>
  <tr>
    <td>```Video URLs```</td>
    <td>The URL for the video used in your ad. Must begin with http:// or https://. 
									 
									 We support: MPG, MP4, AVI, etc.</td>
    <td>```http://www.contoso.com/video1.mpg```</td>
  </tr>
</table>

## Upload a dynamic data feed file

1. [!INCLUDE [BusinessDataDynamicDataFeeds](./includes/BusinessDataDynamicDataFeeds.md)]
1. Select **Upload** > **Tours and Activities**.
1. Enter the **Name** and select the feed file to upload.
1. You can select **Upload and preview** to view your changes or select **Upload and apply** to create the feed.

1. [!INCLUDE [BusinessDataDynamicDataFeeds](./includes/BusinessDataDynamicDataFeeds.md)]
1. Select the feed file you want to create a schedule for.
1. Select the **Schedules** tab.
1. Select the **Schedule feed uploads** and enter the scheduling information and URL for your feed.
1. Select **Save**.


