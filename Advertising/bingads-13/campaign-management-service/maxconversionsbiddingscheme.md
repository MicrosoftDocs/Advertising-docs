---
title: MaxConversionsBiddingScheme Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that represents the maximum conversions bid strategy type.
---
# MaxConversionsBiddingScheme Data Object - Campaign Management
Defines an object that represents the maximum conversions bid strategy type.

> [!NOTE]
> The *MaxConversions* bid strategy is available for Dynamic Search Ads and Search campaigns. All of your target locations must be within Australia, Canada, France, Germany, Italy, Netherlands, Spain, Sweden, Switzerland, United Kingdom, and/or United States. 

With the *MaxConversions* bid strategy, you don't need to set ad group or keyword bids. Microsoft Advertising automatically sets your bids in real time to get as many conversions as possible within your budget.

Microsoft Advertising will always respect your overall budget limit, but if you want greater control over your bids while using Maximize Conversions, you can also set a maximum CPC (cost per click). This is an optional limit you can set to make sure that Microsoft Advertising never pays more than a certain amount for each individual click.

You need to have conversion tracking (a UET tag and a conversion goal) set up (offline conversions are supported too) in order to use the Maximize Conversions bid strategy. If your campaign falls below 15 conversions over any 30-day period, Maximize Conversions will stop optimizing your bids. If this happens with regularity, we recommend switching to a different bid strategy.

> [!IMPORTANT] 
> For some bid strategy types your bid and ad rotation settings are ignored and conversion tracking (via [Universal Event Tracking](../guides/universal-event-tracking.md) tag and a conversion goal) is required. For more information including supported locations, see [Let Microsoft Advertising manage your bids with bid strategies](https://help.ads.microsoft.com/#apex/3/en/56786/1). 

> [!TIP] 
> You can set your campaign's bid strategy to EnhancedCpc, MaxClicks, MaxConversions, TargetCpa, or TargetRoas and then, at any time, set an individual ad group's or keyword's bid strategy to ManualCpc.  

## Syntax
```xml
<xs:complexType name="MaxConversionsBiddingScheme" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:BiddingScheme">
      <xs:sequence>
        <xs:element minOccurs="0" name="MaxCpc" nillable="true" type="tns:Bid" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [MaxConversionsBiddingScheme](maxconversionsbiddingscheme.md) object has the following elements: [MaxCpc](#maxcpc).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="maxcpc"></a>MaxCpc|The maximum cost per click that you want to spend.<br/><br/>**Add:** Optional<br/>**Update:** Optional|[Bid](bid.md)|

The [MaxConversionsBiddingScheme](maxconversionsbiddingscheme.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsbiddingscheme"></a>Inherited Elements from BiddingScheme
The [MaxConversionsBiddingScheme](maxconversionsbiddingscheme.md) object derives from the [BiddingScheme](biddingscheme.md) object, and inherits the following elements: [Type](#type). The descriptions below are specific to [MaxConversionsBiddingScheme](maxconversionsbiddingscheme.md), and might not apply to other objects that inherit the same elements from the [BiddingScheme](biddingscheme.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the bidding scheme. This value is *MaxConversionsBiddingScheme* when you retrieve a maximum conversions bidding scheme. For more information about bidding scheme types, see the [BiddingScheme Data Object Remarks](biddingscheme.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

