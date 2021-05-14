---
title: Automotive ads: Showcase your models and inventory
description: Showcase real-time inventory of new and used cars to nearby shoppers who are in the comparison and transcation stages.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Automotive ads: Showcase your models and inventory

> [!NOTE]
> This feature is currently available in an open beta for the US and UK.

Showcase real-time inventory of new and used cars to nearby shoppers who are in the comparison and transcation stages. Your ads are dynamically created to feature vehicle photos, special prices, and other relevant details. From third-party sites and auto dealers displaying their new and used inventory to automotive manufacturers advertising their new models, Automotive ads drive performance.

![Automotive inventory ad examples.](../images/hlp_BA_CONC_AutomotiveAds.png)

## The benefits of using Automotive ads

- **Customized ads.** Submit and schedule your feed and based on the attributes you provide, we’ll create relevant, personalized ads.
- **Improved return on ad spend.** See more volume, increased click-through rates (CTR), and lower cost per click (CPC) rates.
- **Save time with automation.** With no keywords required, the ads are created by feed files that use Microsoft AI automation and are fully equipped for bulk upload.

## Create Automotive ads with business data feeds

Once you have your campaign(s) set up, you can upload and schedule your feed.

A dynamic feed file is a spreadsheet that contains attributes. This file tells Microsoft Advertising the information you want inserted in your ads and under which condition each attribute should be inserted. Some attributes will be featured in the ad itself.

Note that if you’d like to target specific campaigns or ad groups, you should fill out the Target ad group and Target campaign (see “Optional attributes”); otherwise, we will apply your feed to every campaign in your account.

Your feed file should be tab-delimited plain text with any of the following extensions: CSV, TSV, XLSX, or ZIP.

## Required attributes
Your dynamic data feed file must include the following attributes:

<table>
  <tr>
    <th>Attribute</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td>```Final URL```</td>
    <td>The same domain as your website. Must begin with http:// or https://.
									</td>
    <td>```http://www.contoso.com/seattle/id ```</td>
  </tr>
  <tr>
    <td>```Image URL```</td>
    <td>The single URL for the image used in your ad. Must begin with http:// or https://.
                                    <para></para>
                                    We support JPEG, PNG, or GIF. Both JPG and GIF must be saved in RGB color code with an ICC profile.
                                     
                                     The recommended minimum resolution is 300x300 pixels and 72 DPI.
                                    </td>
    <td>```http://www.contoso.com/image1.png```</td>
  </tr>
  <tr>
    <td>```Make```</td>
    <td>The make of the vehicle.</td>
    <td>```Contoso```</td>
  </tr>
  <tr>
    <td>```Model```</td>
    <td>The model of the vehicle.</td>
    <td>```Contoso Model```</td>
  </tr>
  <tr>
    <td>```Price```</td>
    <td>The cost of the vehicle. Provide the number followed by the currency code (ISO 4217 standards). Use "." as the decimal mark regardless of the local currency.</td>
    <td>```25000.00 USD ```</td>
  </tr>
  <tr>
    <td>```Title```</td>
    <td>The full name of the vehicle.</td>
    <td>```Subaru Outback Limited Automatic AWD```</td>
  </tr>
  <tr>
    <td>```Vehicle ID```</td>
    <td>Unique ID of the listing comprised of any sequence of letters and digits.
                                     
                                      This will not be shown in the ad.</td>
    <td>```1234XYZ```</td>
  </tr>
</table>

## Recommended attributes
Your dynamic data feed file may include any of the following attributes, which are highly recommended:

<table>
  <tr>
    <th>Attribute</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td>```Body style```</td>
    <td>The body style of the vehicle.</td>
    <td>```SUV```</td>
  </tr>
  <tr>
    <td>```Drivetrain```</td>
    <td>The drivetrain of the vehicle.</td>
    <td>```AWD```</td>
  </tr>
  <tr>
    <td>```Engine```</td>
    <td>The engine capacity of the vehicle.</td>
    <td>```4 Cyl 2.4 L```</td>
  </tr>
  <tr>
    <td>```Exterior color```</td>
    <td>The exterior color of the vehicle.</td>
    <td>```Black```</td>
  </tr>
  <tr>
    <td>```Fuel type```</td>
    <td>The fuel type of the vehicle.</td>
    <td>```Gasoline```</td>
  </tr>
  <tr>
    <td>```Interior color```</td>
    <td>The interior color of the vehicle.</td>
    <td>```Gray```</td>
  </tr>
  <tr>
    <td>```Trim```</td>
    <td>The trim of the vehicle.</td>
    <td>```Limited```</td>
  </tr>
  <tr>
    <td>```Year```</td>
    <td>The year the vehicle was launched in yyyy format.</td>
    <td>```2020```</td>
  </tr>
</table>

## Optional attributes
Your dynamic data feed file may include the following optional attributes:

<table>
  <tr>
    <th>Attribute</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td>```Address```</td>
    <td>Either provide the first line of the street address or the full address. If only the street address is provided, fill in the city, state, and zip code as other attributes.</td>
    <td>```123 Boulevard Street```</td>
  </tr>
  <tr>
    <td>```Availability```</td>
    <td>The status of the vehicle's availability.
                                     
                                     This will not be shown in the ad.</td>
    <td>```Available```</td>
  </tr>
  <tr>
    <td>```City```</td>
    <td>The city of the dealership or the car listing.</td>
    <td>```Seattle```</td>
  </tr>
  <tr>
    <td>```Contextual keywords```</td>
    <td>Specific vehicle details used to power relevancy matching. Use ";" to separate multiple keywords.
                                     
                                     This will not be shown in the ad.</td>
    <td>```Used cars for sale; SUV; Automatic; 5 seats; 4 doors```</td>
  </tr>
  <tr>
    <td>```Condition```</td>
    <td>The condition of the vehicle (e.g., excellent, good, fair, poor, or other).</td>
    <td>```Excellent```</td>
  </tr>
  <tr>
    <td>```Country```</td>
    <td>The country of the dealership or car listing.
                                     
                                     This will not be shown in the ad.</td>
    <td>```USA```</td>
  </tr>
  <tr>
    <td>```Custom parameter```</td>
    <td>Include up to 3 key and value pairs, which automatically fill up in the click URL.
                                     
                                     List the key and value pairs within braces. Each term should be set in quotation marks. Separate each phrase of the pair with a colon and separate key and value pairs with commas and without any spaces.
                                     
                                     Neither one can exceed 16 characters or 200 bytes.
                                     
                                     This will not be shown in the ad.</td>
    <td>```{"Bstyle":"SUV",“state”:”new”,”condition”:”excellent”}```</td>
  </tr>
  <tr>
    <td>```Daily payment```</td>
    <td>The daily payment amount in the local currency. Use "." as the decimal mark regardless of the local currency.</td>
    <td>```12.00 USD```</td>
  </tr>
  <tr>
    <td>```Dealer discount```</td>
    <td>Any discount applied to the selling price of the vehicle in the local currency. Use "." as the decimal mark regardless of the local currency.</td>
    <td>```2500.00 USD```</td>
  </tr>
  <tr>
    <td>```Dealer name```</td>
    <td>The name of the dealer.</td>
    <td>```Contoso Dealername```</td>
  </tr>
  <tr>
    <td>```Description```</td>
    <td>Short text description of the vehicle.</td>
    <td>```Supercharged! Automatic! Gasoline!```</td>
  </tr>
  <tr>
    <td>```Disclaimer```</td>
    <td>Any disclaimer on price, payment, or vehicle features.</td>
    <td>```The price includes cargo nets and roof rails.```</td>
  </tr>
  <tr>
    <td>```Down payment```</td>
    <td>Finance down payment in dollar value. Use "." as the decimal mark regardless of the local currency.</td>
    <td>```2000.00 USD```</td>
  </tr>
  <tr>
    <td>```Due at signing```</td>
    <td>The lease due at signing in dollar value. Use "." as the decimal mark regardless of the local currency.</td>
    <td>```2000.00 USD```</td>
  </tr>
  <tr>
    <td>```Email```</td>
    <td>The dealer's email address.</td>
    <td>```dealername@example.com```</td>
  </tr>
  <tr>
    <td>```Final mobile URL```</td>
    <td>The mobile-optimized URL of the landing page in your website that people reach when they click your ad from mobile devices. Same domain as your website, begins with http:// or https://.</td>
    <td>```http://m.www.contoso.com/seattle/id```</td>
  </tr>
  <tr>
    <td>```Fuel efficiency average```</td>
    <td>The vehicle’s average fuel efficiency between city and highway efficiencies.</td>
    <td>```30.7```</td>
  </tr>
  <tr>
    <td>```Fuel efficiency city```</td>
    <td>The vehicle’s fuel efficiency for the city.</td>
    <td>```29.0```</td>
  </tr>
  <tr>
    <td>```Fuel efficiency highway```</td>
    <td>The vehicle’s fuel efficiency the for the highway.</td>
    <td>```32.5```</td>
  </tr>
  <tr>
    <td>```Fuel efficiency unit```</td>
    <td>The unit of the fuel efficiency: MPG, KPL, or KMPL, etc.</td>
    <td>```MPG```</td>
  </tr>
  <tr>
    <td>```Latitude```</td>
    <td>Latitude of the dealership or car listing.
                                     
                                     List in the DDD.DDDDD format.
                                     
                                     This will not be shown in the ad.</td>
    <td>```37.94```</td>
  </tr>
  <tr>
    <td>```Longitude```</td>
    <td>Longitude of the dealership or car listing.
                                     
                                     List in the DDD.DDDDD format.
                                     
                                     This will not be shown in the ad.</td>
    <td>```-121.69```</td>
  </tr>
  <tr>
    <td>```Mileage unit```</td>
    <td>Mileage units. We support values of MI or KM.</td>
    <td>```MI```</td>
  </tr>
  <tr>
    <td>```Mileage value```</td>
    <td>For used vehicles, this is the mileage of the vehicle in miles or kilometers. For new vehicles, use “zero”.</td>
    <td>```1200```</td>
  </tr>
  <tr>
    <td>```Monthly payment```</td>
    <td>The monthly payment dollar amount. Use "." as the decimal mark regardless of the local currency.</td>
    <td>```350.00 USD```</td>
  </tr>
  <tr>
    <td>```Payment term```</td>
    <td>The length of the agreement in months.</td>
    <td>```60 months```</td>
  </tr>
  <tr>
    <td>```Payment type```</td>
    <td>The payment deal type (e.g., lease, finance, balloon).</td>
    <td>```Finance```</td>
  </tr>
  <tr>
    <td>```Phone number```</td>
    <td>The phone number of the dealership following ITU E.123 format.</td>
    <td>```+1 (425) 111-2222```</td>
  </tr>
  <tr>
    <td>```Sale price```</td>
    <td>The sale or special price. Use "." as the decimal mark regardless of the local currency.</td>
    <td>```22000.00 USD```</td>
  </tr>
  <tr>
    <td>```State```</td>
    <td>The state of the dealership or car listing.</td>
    <td>```WA```</td>
  </tr>
  <tr>
    <td>```State of vehicle```</td>
    <td>The current state of the vehicle (e.g., new, used, CPO).</td>
    <td>```New```</td>
  </tr>
  <tr>
    <td>```Target ad group```</td>
    <td>The ad group name. If you set limits here, you will need to set limits for the campaign as well (see “Target campaign” below).
                                     
                                     This will not be shown in the ad.</td>
    <td>```AutosAdGroup```</td>
  </tr>
  <tr>
    <td>```Target campaign```</td>
    <td>The campaign name you want to limit the feed to.
                                     
                                     This will not be shown in the ad.</td>
    <td>```AutosCampaign```</td>
  </tr>
  <tr>
    <td>```Tracking template```</td>
    <td>Upgraded URLs. Include ```ValueTrack``` parameters, custom parameters, or tracking redirects for your item URL.
                                     
                                     This will not be shown in your ad.</td>
    <td>```http://www.trackingtool.com/?source```</td>
  </tr>
  <tr>
    <td>```Video URL```</td>
    <td>The single URL for the video used in your ad. MP4 format only. http:// or https:// only.</td>
    <td>```http://www.contosoexample.com/video.mp4```</td>
  </tr>
  <tr>
    <td>```VIN```</td>
    <td>The VIN number of the vehicle.</td>
    <td>```V285N34S543T674```</td>
  </tr>
  <tr>
    <td>```Zip code```</td>
    <td>The postal code of the dealership or car listing.
                                     
                                     This will not be shown in your ad.</td>
    <td>```98007```</td>
  </tr>
</table>

## Upload a dynamic data feed file

1. [!INCLUDE [BusinessDataDynamicDataFeeds](./includes/BusinessDataDynamicDataFeeds.md)]
1. Select **Upload** > **Autos** > **Listing inventory**.
1. Enter the **Name** and select the feed file to upload.
1. You can select **Upload and preview** to view your changes or select **Upload and apply** to create the feed.

1. [!INCLUDE [BusinessDataDynamicDataFeeds](./includes/BusinessDataDynamicDataFeeds.md)]
1. Select the feed file you want to create a schedule for.
1. Select the **Schedules** tab.
1. Select the **Schedule feed uploads** and enter the scheduling information and URL for your feed.
1. Select **Save**.


