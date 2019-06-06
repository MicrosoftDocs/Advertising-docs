---
title: "Page Feeds"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Add page feeds to fine-tune ad copy for Dynamic Search Ads auto-targets. 
---
# Page Feeds
> [!NOTE]
> The Bulk API for feeds and documentation are subject to change.  

> [!NOTE]
> This feature is currently available in Canada, France, Germany, the United Kingdom, and the United States. 

Page feeds allow you to easily upload all the relevant URLs for your dynamic search ads campaigns. This ensures maximum website coverage and enables the labeling and targeting of specific URLs via custom labels.

Why use page feeds?
- Improve page freshness: Each time a feed is uploaded, the pages in the feed automatically recrawled, so if the pages aren't already in the Bing index of your website, they'll be added. This allows your dynamic search ad campaigns to display the most current version of your website.  
- Fine-tune auto-targets and ad copy: You have full control over what pages are included in an auto-target and as a result, can be more descriptive in your ad copy to drive further engagement.  

You can have 100 feeds per account (this maximum number includes all feed types) and the maximum number of feed items (rows) per account is 5 million.  

> [!NOTE]
> Feeds and feed items can only be managed using the Bulk service. You can manage ads and auto targets using either the Bulk or Campaign Management service. 

## <a name="upload-pagefeed"></a>Upload page feeds

You can upload page feeds and feed items with the Bulk service. 
- The [Feed](../bulk-service/feed.md) record defines the name and data type of attributes that are allowed for the corresponding feed items. 
- The [Feed Item](../bulk-service/feed-item.md) record defines additional information about your products or services and under what conditions that information should be inserted into your ads. The Microsoft Advertising system attributes define under what conditions each feed item should be inserted into your ads, whereas the custom attributes define what information about your products or services you want to insert into your ads. Your page feed items can be referenced from all ads in your Microsoft Advertising account by default. 

> [!NOTE]
> The [Feed](../bulk-service/feed.md) and [Feed Item](../bulk-service/feed-item.md) record types are used for both ad customizer feeds and page feeds. When you download feeds and feed items, be sure to check the "Sub Type" column to find out whether the data is applicable for an ad customizer feed or page feed.  

For page feeds you can use attributes named "Page Url" and "Custom Label".  

|Attribute Name|Attribute Data Type|Description|
|-----|-----|-----|
|Page Url|Url|Contains the URLs of your website to include in the feed.<br/><br/>You must include exactly one page URL per feed item.|
|Custom Label|StringList|Labels that allow you to group the URLs within the feed.<br/><br/>You can include between one to ten custom labels per feed item.|

You might visualize the feed column names and field values in a table: 

|Page Url (Url)|Custom Label (StringList)|
|-----|-----|
|https://contoso.com/3001|Label_1_3001|
|https://contoso.com/3001|Label_2_3001|

You could upload the page feed and feed items via the Bulk API as follows:

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Ad Group,Client Id,Modified Time,Start Date,End Date,Device Preference,Keyword,Match Type,Target,Physical Intent,Name,Ad Schedule,Audience Id,Feed Name,Custom Attributes
Format Version,,,,,,,,,,,,,,,,6,,,,
Feed,Active,-20,,PageFeed,,,PageFeedClientIdGoesHere,,,,,,,,,,,,MyPageFeedName,"[{""name"":""Page Url"",""feedAttributeType"":""Url"",""isPartOfKey"":true},{""name"":""Custom Label"",""feedAttributeType"":""StringList""}]"
Feed Item,Active,-200,-20,,,,20;200,,2019/06/22 00:00:00,2019/06/30 00:00:00,,,,,,,,,,"{""Page Url"":""https://contoso.com/3001"",""Custom Label"":[""Label_1_3001"",""Label_2_3001""]}"
```

## <a name="associate-pagefeed"></a>Associate a page feed

Page feeds can be associated at the campaign level, which also applies to all the ad groups within the campaign.

> [!NOTE]
> Currently you can only associate page feed IDs with campaigns via the Microsoft Advertising web application. Support is coming soon via the Bulk API and Campaign Management API.  

You can optionally set each campaign's page feed targeting source via the Bulk API [Source](../bulk-service/campaign.md#source) or Campaign Management API [Source](../campaign-management-service/dynamicsearchadssetting.md#source). You can choose one of the following options:

|Value|Description|
|-----------|---------------|
|AdvertiserSuppliedUrls|Use URLs from my page feed only. Only URLs specified in the feed file will be served from this campaign. We recommend using this option for highly specific campaigns with tailored ad copy.|
|All|Use URLs from both Bing's index of my website and my page feed. Pages from both sources will be used but URLs within the feed file will be given priority.|
|SystemIndex|Use Bing's index of my website. This is the default behavior of dynamic search ad campaigns on Bing.|

## <a name="customlabel-autotarget"></a>Create custom label auto targets

To create a custom label auto target via the Bulk service, you can upload an [Ad Group Dynamic Search Ad Target](../bulk-service/ad-group-dynamic-search-ad-target.md#dynamicadtargetcondition1) record. For example, set the [Dynamic Ad Target Condition 1](../bulk-service/ad-group-dynamic-search-ad-target.md#dynamicadtargetcondition1) field to "CustomLabel" and set the [Dynamic Ad Target Value 1](../bulk-service/ad-group-dynamic-search-ad-target.md#dynamicadtargetvalue1) field to the value of one of the page feed item custom labels e.g., "Label_1_3001". 

To create a custom label auto target via the Campaign Management service, you can add a [BiddableAdGroupCriterion](../campaign-management-service/biddableadgroupcriterion.md) that contains a [Webpage](../campaign-management-service/webpage.md) criterion via the [AddAdGroupCriterions](../campaign-management-service/addadgroupcriterions.md) operation. For example, set the [Operand](../campaign-management-service/webpagecondition.md#operand) element to "CustomLabel" and set the [Argument](../campaign-management-service/webpagecondition.md#argument) element to the value of one of the page feed item custom labels e.g., "Label_1_3001". 

## See Also
[Dynamic Search Ads](dynamic-search-ads.md)  
[Ad Customizer Feeds](ad-customizer-feeds.md)  