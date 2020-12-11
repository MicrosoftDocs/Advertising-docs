---
title: TargetRoasBiddingScheme Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that represents the target ROAS bid strategy type.
---
# TargetRoasBiddingScheme Data Object - Campaign Management
Defines an object that represents the target ROAS bid strategy type. 

> [!NOTE]
> The target ROAS bid strategy is available for Dynamic Search Ads, Search, and Shopping campaigns.

With the TargetRoas (return on ad spend) bid strategy, you don't need to set ad group or keyword bids. You set your budget and your target 30-day average ROAS, and Microsoft Advertising automatically sets your bids in real time to get you to this average. Some conversions may cost more than your target and some may cost less, but Microsoft Advertising will try to make sure your return on ad spend is in line with your target.

Microsoft Advertising will always respect your overall budget limit, but if you want greater control over your bids while using Target ROAS, you can also set a maximum CPC (cost per click). This is an optional limit you can set to make sure that Microsoft Advertising never pays more than a certain amount for each individual click.

You need to have conversion tracking (a UET tag and a conversion goal) set up (offline conversions are supported too) in order to use the Target ROAS bid strategy. Also you must be tracking revenue and have non-zero revenue over the last 30 days. If your campaign falls below 15 conversions or has zero revenue over any 30-day period, Target ROAS will stop optimizing your bids. If this happens with regularity, we recommend switching to a different bid strategy.

> [!IMPORTANT] 
> For some bid strategy types your bid and ad rotation settings are ignored and conversion tracking (via [Universal Event Tracking](../guides/universal-event-tracking.md) tag and a conversion goal) is required. For more information including supported locations, see [Let Microsoft Advertising manage your bids with bid strategies](https://help.ads.microsoft.com/#apex/3/en/56786/1). 

> [!TIP] 
> You can set your campaign's bid strategy to EnhancedCpc, MaxClicks, MaxConversions, TargetRoas, or TargetRoas and then, at any time, set an individual ad group's or keyword's bid strategy to ManualCpc.  

## Syntax
```xml
<xs:complexType name="TargetRoasBiddingScheme" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:BiddingScheme">
      <xs:sequence>
        <xs:element minOccurs="0" name="MaxCpc" nillable="true" type="tns:Bid" />
        <xs:element minOccurs="0" name="TargetRoas" nillable="true" type="xs:double" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [TargetRoasBiddingScheme](targetroasbiddingscheme.md) object has the following elements: [MaxCpc](#maxcpc), [TargetRoas](#targetroas).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="maxcpc"></a>MaxCpc|The maximum cost per click that you want to spend.<br/><br/>**Add:** Optional<br/>**Update:** Optional|[Bid](bid.md)|
|<a name="targetroas"></a>TargetRoas|The target return on ad spend (ROAS) that you want used by Microsoft Advertising to maximize conversions.<br/><br/>The supported target ROAS values range from 0.01 (1 percent) to 1,000.00 (100,000 percent).<br/><br/>**Add:** Required<br/>**Update:** Optional|**double**|

The [TargetRoasBiddingScheme](targetroasbiddingscheme.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsbiddingscheme"></a>Inherited Elements from BiddingScheme
The [TargetRoasBiddingScheme](targetroasbiddingscheme.md) object derives from the [BiddingScheme](biddingscheme.md) object, and inherits the following elements: [Type](#type). The descriptions below are specific to [TargetRoasBiddingScheme](targetroasbiddingscheme.md), and might not apply to other objects that inherit the same elements from the [BiddingScheme](biddingscheme.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|Reserved for future use.|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

