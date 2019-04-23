---
title: TargetCpaBiddingScheme Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that represents the target CPA bid strategy type.
---
# TargetCpaBiddingScheme Data Object - Campaign Management
Defines an object that represents the target CPA bid strategy type.

> [!NOTE]
> The *TargetCpa* bid strategy is available only for search ad campaigns.
> 
> The *TargetCpa* bid strategy is available only to advertisers targeting the following countries: Australia, Canada, France, Germany, United Kingdom, and United States.

With the *TargetCpa* (cost per acquisition) bid strategy, you don't need to set ad group or keyword bids. You set your budget and your target 30-day average CPA, and Bing Ads automatically sets your bids in real time to get you to this average. Some conversions may cost more than your target and some may cost less, but Bing Ads will try to make sure your average cost per conversion is in line with your target.

Bing Ads will always respect your overall budget limit, but if you want greater control over your bids while using Target CPA, you can also set a maximum CPC (cost per click). This is an optional limit you can set to make sure that Bing Ads never pays more than a certain amount for each individual click.

You need to have conversion tracking (a UET tag and a conversion goal) set up and have had at least 15 conversions in the last 30 days in order to use the Target CPA bid strategy. If your campaign falls below 15 conversions over any 30-day period, Target CPA will stop optimizing your bids. If this happens with regularity, we recommend switching to a different bid strategy.

> [!IMPORTANT] 
> If the campaign bid strategy type is set to *MaxClicks*, *MaxConversions*, or *TargetCpa*, the behavior of existing features will change unless you set an individual ad group's or keyword's bid strategy to *ManualCpc*. For more details, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md). 
> - You can continue to set the ad group and keyword bids; however they will not be used by Bing Ads.
> - Bing Ads will periodically change your stored ad group or keyword bid settings. You can continue to set new bids, however Bing Ads may change them at any time using this bid strategy type.
> - You can continue to set bid adjustments e.g. for age, gender, or location; however, the multiplier will inform rather than directly modify or override the automated bid. For auto bidding the multiplier is used as a weighted percentage to inform Bing Ads about how much you value the criterion relative to other criteria. For example, a -50% bid multiplier for a mobile device criterion with the Max Conversions bid strategy to indicate that you value conversions from mobile traffic half as much as other device types. The same bid multiplier with the Max Clicks bid strategy would indicate that you value clicks on mobile half as much as other device types. The valid range of values that you can use to inform auto bidding is -100.00 through 30.00.
> - Even if the [AdRotation](adgroup.md#adrotation) is set to *RotateAdsEvenly*, it will be ignored as these bid strategies prioritize better-performing ads.

Also note that you must have conversion tracking (via [Universal Event Tracking](../guides/universal-event-tracking.md) tag and a conversion goal) set up for the *MaxConversions* and *TargetCpa* bid strategy types to work. To set the *MaxConversions* or *TargetCpa* bid strategy types, the campaign must have at least 15 conversions in the last 30 days. If you try to add or update a campaign to use one of these strategy types, the requested operation will fail if there is not enough conversion history. If an active campaign uses one of these bid strategy types, and then ceases to meet the minimum conversion history requirement at any time, Bing Ads will stop auto bidding but will continue to use the *DailyBudgetStandard* budget type. For a new campaign we recommend that you start with *EnhancedCpc* and then when the campaign has enough conversion history, you can update it to use either the *MaxConversions* or *TargetCpa* bid strategy.

## Syntax
```xml
<xs:complexType name="TargetCpaBiddingScheme" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:BiddingScheme">
      <xs:sequence>
        <xs:element minOccurs="0" name="MaxCpc" nillable="true" type="tns:Bid" />
        <xs:element minOccurs="0" name="TargetCpa" nillable="true" type="xs:double" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="maxcpc"></a>MaxCpc|The maximum cost per click that you want to spend.<br/><br/>**Add:** Optional<br/>**Update:** Optional|[Bid](bid.md)|
|<a name="targetcpa"></a>TargetCpa|The target cost per acquisition (CPA) that you want used by Bing Ads to maximize conversions.<br/><br/>**Add:** Required<br/>**Update:** Optional|**double**|

The [TargetCpaBiddingScheme](targetcpabiddingscheme.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsbiddingscheme"></a>Inherited Elements from BiddingScheme
The [TargetCpaBiddingScheme](targetcpabiddingscheme.md) object derives from the [BiddingScheme](biddingscheme.md) object, and inherits the following elements. The descriptions below are specific to [TargetCpaBiddingScheme](targetcpabiddingscheme.md), and might not apply to other objects that inherit the same elements from the [BiddingScheme](biddingscheme.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the bidding scheme. This value is *TargetCpaBiddingScheme* when you retrieve a target CPA bidding scheme. For more information about bidding scheme types, see the [BiddingScheme Data Object Remarks](biddingscheme.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

