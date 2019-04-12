---
title: "Universal Event Tracking"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Universal event tracking is a prerequisite for conversion tracking and remarketing in paid search.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# Universal Event Tracking
UET is a powerful Bing Ads tool. You just need to create one single UET tag and then add it to your website once. This tag records what customers do on your website then Bing Ads starts collecting that data allowing you to track conversions (like purchases or leads) or target audiences using remarketing lists. UET is a prerequisite for conversion tracking and remarketing in paid search.

![Universal Event Tracking](media/universal-event-tracking.png "Universal Event Tracking")

There are a few steps to get this set up. You will need to:
* Create a [UET tag](#uet) once in Bing Ads
* Add the UET tag tracking code to every page of your website
* Depending on what you want to do, either set up [conversion tracking](#conversiongoals) or leverage [audiences](#audience) e.g., [remarketing in paid search](#remarketinglist).

For details please see these API overview sections below:
- [Universal Event Tracking APIs](#uet)
- [Conversion Goal APIs](#conversiongoals)
- [Audience APIs](#audience)

## <a name="uet"></a>Universal Event Tracking APIs

Before you can track conversions or target audiences using a remarketing list, you need to create a UET tag in Bing Ads (web application or API) and then add the UET tag tracking code to every page of your website. This section describes how you can setup UET tags using the Bing Ads API. For information about setting up UET tags using the Bing Ads web application, see [How do I create a UET tag?](https://help.bingads.microsoft.com/#apex/3/en/56682/2-500) and [FAQ: Universal Event Tracking](https://help.bingads.microsoft.com/#apex/3/en/53056/2). 

> [!NOTE]
> For each of the operations described in this section, you must specify the customer identifier in the *CustomerId* header element. 

1. First you should call the [GetUetTagsByIds](../campaign-management-service/getuettagsbyids.md) operation to check whether a tag has already been created. You can leave the *TagIds* element null or empty to request all UET tags available for the customer.
2. You can use one UET tag with all of your conversion goals and remarketing lists. Before you create multiple UET tags, see [Reasons for creating more than one UET tag](https://help.bingads.microsoft.com/#apex/3/en/56685/2). If you do not already have a UET tag that can be used, or if you need another UET tag, call the [AddUetTags](../campaign-management-service/adduettags.md) service operation to create a new UET tag. If the call is successful, the tracking script that you should add to your website is included in a corresponding [UetTag](../campaign-management-service/uettag.md) within the response message. Later as needed you can update the name and description of a [UetTag](../campaign-management-service/uettag.md) with the [UpdateUetTags](../campaign-management-service/updateuettags.md) operation.

After you retrieve the tracking script from the [AddUetTags](../campaign-management-service/adduettags.md) or [GetUetTagsByIds](../campaign-management-service/getuettagsbyids.md) operation, the next step is to add the UET tag tracking code to your website. We recommend that you, or your website administrator, add it to your entire website in either the head or body sections. If your website has a master page, then that is the best place to add it because you add it once and it is included on all pages. For more information, see [How do I add the UET tag to my website?](https://help.bingads.microsoft.com/#apex/3/en/56688/2-500) 

Depending on what you want to do, either set up [conversion tracking](#conversiongoals) or [audiences](#audience).

## <a name="conversiongoals"></a>Conversion Goal APIs

One of the biggest value propositions of UET is that it lets you install one tag on your website to track multiple types of conversions. Once the UET tag tracking code is added to your website, Bing Ads can log page visits and any custom events (such as downloading a white paper, subscribing to a newsletter etc). 

However, not all actions are created equal. You probably have a subset of actions that you consider more important to a successful advertising campaigns. These may include making purchases, filling out a lead form or watching a video. This is where conversion goals can help. Conversion goals allow you to specify which actions (recorded by UET) to count as conversions. For more information about Conversion Goals, see [What are conversion goals and goal types?](https://help.bingads.microsoft.com/#apex/3/en/56709/2-500).

### <a name="conversiongoals-campaign"></a>Conversion Goal Campaign Management APIs

There are five types of conversion goals. The [ConversionGoal](../campaign-management-service/conversiongoal.md) is the base class from which all goals are derived. 
- [AppInstallGoal](../campaign-management-service/appinstallgoal.md)
- [DurationGoal](../campaign-management-service/durationgoal.md)
- [EventGoal](../campaign-management-service/eventgoal.md)
- [InStoreTransactionGoal](../campaign-management-service/instoretransactiongoal.md)
- [OfflineConversionGoal](../campaign-management-service/offlineconversiongoal.md)
- [PagesViewedPerVisitGoal](../campaign-management-service/pagesviewedpervisitgoal.md)
- [UrlGoal](../campaign-management-service/urlgoal.md)

The following operations are added for managing conversion goals.

- [AddConversionGoals](../campaign-management-service/addconversiongoals.md)
- [GetConversionGoalsByIds](../campaign-management-service/getconversiongoalsbyids.md)
- [GetConversionGoalsByTagIds](../campaign-management-service/getconversiongoalsbytagids.md)
- [UpdateConversionGoals](../campaign-management-service/updateconversiongoals.md)


## <a name="audience"></a>Audience APIs
Improve your return on investment by optimizing your campaigns for specific audiences, which are groups of people who have something in common relating to your campaign.

### <a name="audience-types"></a>Audience Types

There are five types of audiences. 
- [CustomAudience](#customaudience)
- [In-Market Audience](#inmarketaudience)
- [Product Audience](#productaudience)
- [Remarketing List](#remarketinglist)
- [Similar Remarketing List](#similarremarketinglist)

#### <a name="customaudience"></a>Custom Audiences
A custom audience is generated by using your own customer data to create richer user segments. You can use custom audiences in conjunction with your remarketing lists, usually through your data management provider (DMP). When your DMP connects to our custom audience feature, you can then import your custom audiences into Bing Ads for search remarketing. You can use custom audiences separately from remarketing, with no UET required. Only first-party audience data (your customer data that you collected from your own website or apps, for example) is allowed for targeting on the Microsoft Advertising network. For more information, see [About custom audiences](https://help.bingads.microsoft.com/#apex/3/en/56849/0).

> [!NOTE]
> You can delete but cannot add a custom audience using the Bing Ads API. Having said that, you can add and delete custom audience associations and exclusions.

At a glance:
* Uses your data. Custom audiences allow you to use the audience data you already have.
* Creates richer audiences. Create richer audience segments using more of your customer data.
* Works like remarketing. Custom audiences can be associated to campaigns and ad groups as target and bid, bid only, or as an exclusion.

To get started with custom audiences, your DMP must:

* Integrate our custom audience APIs into their platform.
* Agree to our data sharing and privacy policy.

Depending on the provider, they'll have their own enablement steps within their software. Be sure to contact your DMP for details on how to enable this feature.

Once the integration has been completed, your custom audiences will appear in the Audiences section of the Shared Library in the Bing Ads web application. You can also download custom audiences via Bulk and Campaign Management APIs as described below.

#### <a name="inmarketaudience"></a>In-Market Audiences
In-market audiences are curated lists of customers who have shown purchase intent signals within a particular category, including searches and clicks on Bing and page views on Microsoft services. Bing Ads supplies the curated list of potential customers, unlike remarketing in paid search, where the advertiser creates the list. You can target and modify bids for these audiences by associating in-market audience lists with campaigns and ad groups, similar to what you do with remarketing lists. For more information, see [About in-market audiences](https://help.bingads.microsoft.com/#apex/3/en/56851/0).

> [!NOTE]
> You cannot add, update, or delete an in-market audience using the Bing Ads API. Having said that, you can add and delete in-market audience associations and exclusions.

> [!NOTE]
> Not everyone has this feature yet. If you don't, don't worry. It's coming soon.

#### <a name="productaudience"></a>Product Audiences
Product audiences are dynamic remarketing lists that pair customers with specific products based on the products they have looked at, considered, or already purchased on your website. You can use product audiences in both search campaigns and audience campaigns. For more information, see [About product audiences](https://help.bingads.microsoft.com/#apex/3/en/56910/0).

> [!NOTE]
> Not everyone has this feature yet. If you don't, don't worry. It's coming soon.

#### <a name="remarketinglist"></a>Remarketing Lists
Remarketing in Paid Search lets you improve your return on investment by optimizing your campaigns for specific audiences, which are the people who have visited your website before. When you create remarketing lists, you specify what user actions on your website qualify them to be part of the remarketing lists. 

When users perform qualifying actions, they are added to the remarketing lists within minutes. If the remarketing list minimum size of 1,000 (minimum cookie pool) is met and you have associated the remarketing list with a campaign or ad group and set a specific bid amount, the ad delivery engine will start serving remarketed ads to those users on the Bing Network. For more information about Remarketing in Paid Search, see [Reach your audience](https://help.bingads.microsoft.com/#apex/3/en/n5022/1) and [FAQ: Remarketing in Paid Search](https://help.bingads.microsoft.com/#apex/3/en/56727/1).  

After you have set up [Universal Event Tracking (UET)](#uet), you can use the Bing Ads API to create remarketing lists and associate them with campaigns or ad groups. 

#### <a name="similarremarketinglist"></a>Similar Remarketing Lists
Bing Ads will automatically generate similar audiences for remarketing lists if you are a pilot participant. You cannot create or edit the similar audience for a remarketing list. Having said that, you can add and delete similar remarketing list associations and exclusions. If you delete the source remarketing list, then the similar audience will also be deleted. If a similar audience is associated with a campaign or ad group, then you cannot delete the source remarketing list.

> [!NOTE]
> Not everyone has this feature yet. If you don't, don't worry. It's coming soon.

### <a name="audience-bulk"></a>Audience Bulk APIs
With the Bulk service you can use the following record types to download and upload audiences:

- [Custom Audience](../bulk-service/custom-audience.md)
- [In Market Audience](../bulk-service/in-market-audience.md)
- [Product Audience](../bulk-service/product-audience.md) 
- [Remarketing List](../bulk-service/remarketing-list.md)   
- [Similar Remarketing List](../bulk-service/similar-remarketing-list.md)   

> [!NOTE]
> With custom audiences, only update of the Name and Description are supported. You can delete but cannot add a custom audience using the Bing Ads API. Having said that, you can add and delete custom audience associations and exclusions.
> 
> You cannot add, update, or delete an in-market audience using the Bing Ads API. Having said that, you can add and delete in-market audience associations and exclusions.
> 
> Bing Ads will automatically generate similar audiences for remarketing lists if you are a pilot participant. You cannot create or edit the similar audience for a remarketing list. Having said that, you can add and delete similar remarketing list associations and exclusions. If you delete the source remarketing list, then the similar audience will also be deleted. If a similar audience is associated with a campaign or ad group, then you cannot delete the source remarketing list.

With the Bulk service you can use the following record types to download and upload audience associations:

- [Ad Group Custom Audience Association](../bulk-service/ad-group-custom-audience-association.md)
- [Ad Group In Market Audience Association](../bulk-service/ad-group-in-market-audience-association.md)
- [Ad Group Negative Custom Audience Association](../bulk-service/ad-group-negative-custom-audience-association.md)
- [Ad Group Negative In Market Audience Association](../bulk-service/ad-group-negative-in-market-audience-association.md)
- [Ad Group Negative Product Audience Association](../bulk-service/ad-group-negative-product-audience-association.md)
- [Ad Group Negative Remarketing List Association](../bulk-service/ad-group-negative-remarketing-list-association.md)
- [Ad Group Negative Similar Remarketing List Association](../bulk-service/ad-group-negative-similar-remarketing-list-association.md)
- [Ad Group Product Audience Association](../bulk-service/ad-group-product-audience-association.md)
- [Ad Group Remarketing List Association](../bulk-service/ad-group-remarketing-list-association.md)
- [Ad Group Similar Remarketing List Association](../bulk-service/ad-group-similar-remarketing-list-association.md)
- [Campaign Custom Audience Association](../bulk-service/campaign-custom-audience-association.md)
- [Campaign In Market Audience Association](../bulk-service/campaign-in-market-audience-association.md)
- [Campaign Negative Custom Audience Association](../bulk-service/campaign-negative-custom-audience-association.md)
- [Campaign Negative In Market Audience Association](../bulk-service/campaign-negative-in-market-audience-association.md)
- [Campaign Negative Product Audience Association](../bulk-service/campaign-negative-product-audience-association.md)
- [Campaign Negative Remarketing List Association](../bulk-service/campaign-negative-remarketing-list-association.md)
- [Campaign Negative Similar Remarketing List Association](../bulk-service/campaign-negative-similar-remarketing-list-association.md)
- [Campaign Product Audience Association](../bulk-service/campaign-product-audience-association.md)
- [Campaign Remarketing List Association](../bulk-service/campaign-remarketing-list-association.md)
- [Campaign Similar Remarketing List Association](../bulk-service/campaign-similar-remarketing-list-association.md)

> [!NOTE]
> Audience targets cannot be set both campaign and ad group level. If you set any biddable campaign level audience criteria, then you cannot set any biddable ad group level audience criteria. Audience exclusions can be set at both campaign and ad group level. Bing Ads applies a union of both campaign and ad group level exclusions.

By default ads in a campaign and ad group can show to everyone, but the bid adjustment will apply to people included in the audience. If you only want the ads to show to people included in the audience, you'll want to set the "target and bid" target setting. You can use the *Target Setting* field in the [Campaign](../bulk-service/campaign.md#targetsetting) or [Ad Group](../bulk-service/ad-group.md#targetsetting) record to determine the target setting that is applicable for all audiences (i.e., custom audiences, in-market audiences, product audiences, remarketing lists, and similar audiences for remarketing lists) that are associated with the campaign or ad group. Each audience can be associated with multiple campaigns and ad groups, and each target setting is applied independently for delivery. 

### <a name="remarketing-campaign"></a>Audience Campaign Management APIs
The [CustomAudience](../campaign-management-service/customaudience.md), [InMarketAudience](../campaign-management-service/inmarketaudience.md), [ProductAudience](../campaign-management-service/productaudience.md), [RemarketingList](../campaign-management-service/remarketinglist.md), and [SimilarRemarketingList](../campaign-management-service/similarremarketinglist.md) objects all derive from the [Audience](../campaign-management-service/audience.md) base class. If you are using the Campaign Management service you can add, get, update, or delete the audience with the respective [AddAudiences](../campaign-management-service/addaudiences.md), [GetAudiencesByIds](../campaign-management-service/getaudiencesbyids.md), [UpdateAudiences](../campaign-management-service/updateaudiences.md), and [DeleteAudiences](../campaign-management-service/deleteaudiences.md) operations.

> [!NOTE]
> With custom audiences, only update of the Name and Description are supported. You can delete but cannot add a custom audience using the Bing Ads API. Having said that, you can add and delete custom audience associations and exclusions.
> 
> You cannot add, update, or delete an in-market audience using the Bing Ads API. Having said that, you can add and delete in-market audience associations and exclusions.
> 
> Bing Ads will automatically generate similar audiences for remarketing lists if you are a pilot participant. You cannot create or edit the similar audience for a remarketing list. Having said that, you can add and delete similar remarketing list associations and exclusions. If you delete the source remarketing list, then the similar audience will also be deleted. If a similar audience is associated with a campaign or ad group, then you cannot delete the source remarketing list.

To add, get, update, or delete the association between your audience and campaign, use the [BiddableCampaignCriterion](../campaign-management-service/biddablecampaigncriterion.md) object with the respective [AddCampaignCriterions](../campaign-management-service/addcampaigncriterions.md), [GetCampaignCriterionsByIds](../campaign-management-service/getcampaigncriterionsbyids.md), [UpdateCampaignCriterions](../campaign-management-service/updatecampaigncriterions.md), and [DeleteCampaignCriterions](../campaign-management-service/deletecampaigncriterions.md) operations. You can use the [NegativeCampaignCriterion](../campaign-management-service/negativecampaigncriterion.md) object with the same operations to set audience exclusions. 

To add, get, update, or delete the association between your audience and ad group, use the [BiddableAdGroupCriterion](../campaign-management-service/biddableadgroupcriterion.md) object with the respective [AddAdGroupCriterions](../campaign-management-service/addadgroupcriterions.md), [GetAdGroupCriterionsByIds](../campaign-management-service/getadgroupcriterionsbyids.md), [UpdateAdGroupCriterions](../campaign-management-service/updateadgroupcriterions.md), and [DeleteAdGroupCriterions](../campaign-management-service/deleteadgroupcriterions.md) operations. You can use the [NegativeAdGroupCriterion](../campaign-management-service/negativeadgroupcriterion.md) object with the same operations to set audience exclusions. 

> [!NOTE]
> Audience targets cannot be set both campaign and ad group level. If you set any biddable campaign level audience criteria, then you cannot set any biddable ad group level audience criteria. Audience exclusions can be set at both campaign and ad group level. Bing Ads applies a union of both campaign and ad group level exclusions.

By default ads in a campaign and ad group can show to everyone, but the bid adjustment will apply to people included in the audience. If you only want the ads to show to people included in the audience, you'll want to set the "target and bid" target setting. You can use the *Settings* element of the [Campaign](../campaign-management-service/campaign.md) or [AdGroup](../campaign-management-service/adgroup.md) object to determine the target setting that is applicable for all audiences (i.e., custom audiences, in-market audiences, product audiences, remarketing lists, and similar audiences for remarketing lists) that are associated with the campaign or ad group. Each audience can be associated with multiple campaigns and ad groups, and each target setting is applied independently for delivery. 

## See Also

[Bing Ads Web Service Addresses](web-service-addresses.md)  
[FAQ: Universal Event Tracking](https://help.bingads.microsoft.com/#apex/3/en/53056/2)  
[FAQ: Remarketing in Paid Search](https://help.bingads.microsoft.com/#apex/3/en/56727/1)  
