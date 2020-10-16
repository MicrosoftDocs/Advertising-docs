---
title: "Dynamic Search Ads"
ms.service: "bing-ads"
ms.topic: "article"
author: Matt-UX
ms.author: mattrob
description: Setup Dynamic Search ads with the Bing Ads API.
---
# Dynamic Search Ads
Dynamic search ads provide a streamlined, low-touch way to make sure customers searching on the Microsoft Advertising Network find your products or services.

> [!NOTE]
> This feature is currently available in the following countries: Australia (AU), Austria (AT), Belgium (BE), Canada (CA), France (FR), Germany (DE), Ireland (IE), Italy (IT), Netherlands (NL), New Zealand (NZ), Spain (ES), Sweden (SE), Switzerland (CH), United Kingdom (UK), and United States (US).  

Dynamic search ads automatically target relevant search queries based on the content of your website, and are dynamically created to respond to these search queries. Using them will:

-  Create targeted and relevant ads automatically: New, dynamically-created ads for every search query based on your website content, or specific pages or categories of your website.
-  Reduce your workload: No need to maintain keyword lists, manage bids, or update and customize ad titles.
-  Find missed opportunities: Automatically adapt to new queries to drive additional conversions.

Dynamic search ads are most appropriate for two types of advertisers:

-  Advertisers who have a large catalog of webpages and a changing mix of products, making it difficult to manage search ads for each product.
-  Advertisers who are not familiar with search advertising, but who want to quickly and easily try it out.

For more information see the [Target searches automatically with dynamic search ads](https://help.ads.microsoft.com/#apex/3/en/56794/0) help documentation.

## <a name="bulk"></a>Bulk API for Dynamic Search Ads  
The following Bulk records are available for managing dynamic search ads campaigns.
* [Ad Group Dynamic Search Ad Target](../bulk-service/ad-group-dynamic-search-ad-target.md)
* [Ad Group Negative Dynamic Search Ad Target](../bulk-service/ad-group-negative-dynamic-search-ad-target.md)
* [Campaign Negative Dynamic Search Ad Target](../bulk-service/campaign-negative-dynamic-search-ad-target.md)
* [Dynamic Search Ad](../bulk-service/dynamic-search-ad.md)  

Dynamic search ads can only be created within campaigns that have valid dynamic search ads settings (comprised of the [Domain Language](../bulk-service/campaign.md#domainlanguage), [Page Feed Ids](../bulk-service/campaign.md#pagefeedids), [Source](../bulk-service/campaign.md#source), and [Website](../bulk-service/campaign.md#website) fields).    
- Dynamic search ads campaigns where [Campaign Type](../bulk-service/campaign.md#campaigntype) is set to "DynamicSearchAds". 
- Search campaigns if the account is in the [mixed campaigns](../guides/mixed-campaigns.md) feature pilot, if the [CampaignType](../bulk-service/campaign.md#campaigntype) is set to "Search", if the [ExperimentId](../bulk-service/campaign.md#experimentid) element is not set, and if the [AdGroupType](../bulk-service/ad-group.md#adgrouptype) is set to "SearchDynamic". 

To get started with dynamic search ads, first you'll need to define a [Campaign](../bulk-service/campaign.md) record with the *Campaign Type* field set to *DynamicSearchAds*. When you create the campaign, you'll also need to specify the *Domain Language* and *Website* fields. 

Next, define an [Ad Group](../bulk-service/ad-group.md) within the dynamic search ads campaign. You can add one or more [Ad Group Dynamic Search Ad Target](../bulk-service/ad-group-dynamic-search-ad-target.md) records for the parent ad group that helps determine whether or not to serve dynamic search ads. 

If you want to exclude certain portions of your website, you can add negative targets at the campaign and/or ad group level using the respective [Campaign Negative Dynamic Search Ad Target](../bulk-service/campaign-negative-dynamic-search-ad-target.md) and [Ad Group Negative Dynamic Search Ad Target](../bulk-service/ad-group-negative-dynamic-search-ad-target.md) records. The [Campaign Negative Dynamic Search Ad Target](../bulk-service/campaign-negative-dynamic-search-ad-target.md) at the campaign level applies to all ad groups within the campaign; however, if you define ad group level [Ad Group Negative Dynamic Search Ad Target](../bulk-service/ad-group-negative-dynamic-search-ad-target.md), the campaign target is ignored for that ad group. 

For any of the [Ad Group Dynamic Search Ad Target](../bulk-service/ad-group-dynamic-search-ad-target.md), [Ad Group Negative Dynamic Search Ad Target](../bulk-service/ad-group-negative-dynamic-search-ad-target.md), and [Campaign Negative Dynamic Search Ad Target](../bulk-service/campaign-negative-dynamic-search-ad-target.md) records, you can choose whether you want the target argument to match partial URLs, page content, page title, or categories that Bing thinks applies to your website. To discover the categories that you can use for targets (positive or negative), call the [GetDomainCategories](../ad-insight-service/getdomaincategories.md) operation with the Ad Insight service.

Finally you can define a [Dynamic Search Ad](../bulk-service/dynamic-search-ad.md) record assigned to the ad group. The ad title and display URL are generated automatically based on the website domain and language that you want to target.


## <a name="campaign"></a>Campaign Management API for Dynamic Search Ads  

Dynamic search ads can only be created within campaigns that have a [DynamicSearchAdsSetting](../campaign-management-service/dynamicsearchadssetting.md).  
- Dynamic search ads campaigns where [CampaignType](../campaign-management-service/campaign.md#campaigntype) is set to "DynamicSearchAds". 
- Search campaigns if the account is in the [mixed campaigns](../guides/mixed-campaigns.md) feature pilot, if the [CampaignType](../campaign-management-service/campaign.md#campaigntype) is set to "Search", if the [ExperimentId](../campaign-management-service/campaign.md#experimentid) element is not set, and if the [AdGroupType](../campaign-management-service/adgroup.md#adgrouptype) is set to "SearchDynamic".   

To get started with dynamic search ads, first you'll need to [add](../campaign-management-service/addcampaigns.md) a new [Campaign](../campaign-management-service/campaign.md) with its type set to *DynamicSearchAds*. When you create the campaign, you'll need to include a [DynamicSearchAdsSetting](../campaign-management-service/dynamicsearchadssetting.md) that specifies the target website domain and language. The new *DynamicSearchAds* value is added to the [CampaignType](../campaign-management-service/campaigntype.md) value set. 

Next, [create](../campaign-management-service/addadgroups.md) a new [AdGroup](../campaign-management-service/adgroup.md) within the dynamic search ads campaign. You can add one or more [Webpage](../campaign-management-service/webpage.md) criterion to each ad group that helps determine whether or not to serve dynamic search ads, by calling the [AddAdGroupCriterions](../campaign-management-service/addadgroupcriterions.md) operation. 

If you want to exclude certain portions of your website, you can add negative [Webpage](../campaign-management-service/webpage.md) criterion at the campaign and/or ad group level using the respective [AddCampaignCriterions](../campaign-management-service/addcampaigncriterions.md) and [AddAdGroupCriterions](../campaign-management-service/addadgroupcriterions.md) service operations. The negative [Webpage](../campaign-management-service/webpage.md) criterion at the campaign level applies to all ad groups within the campaign; however, if you define ad group level negative [Webpage](../campaign-management-service/webpage.md) criterion, the campaign criterion is ignored for that ad group. 

Whether the criterion is positive or negative, you can choose whether you want the criterion argument to match partial URLs, page content, page title, or categories that Bing thinks applies to your website. To discover the categories that you can use for [Webpage](../campaign-management-service/webpage.md) criterion (positive or negative), use the [GetDomainCategories](../ad-insight-service/getdomaincategories.md) operation with the Ad Insight service.

Finally you can [add](../campaign-management-service/addads.md) a [DynamicSearchAd](../campaign-management-service/dynamicsearchad.md) into the ad group. The ad title and display URL are generated automatically based on the website domain and language that you want to target.
