---
title: TargetCpaBiddingScheme Data Object
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# TargetCpaBiddingScheme Data Object
Defines an object that represents the target CPA bid strategy type.

Use this bid strategy to maximize conversions at the target cost per acquisition (CPA).

> [!IMPORTANT]
> If the campaign bid strategy type is set to *MaxClicks*, *MaxConversions*, or *TargetCpa*, the behavior of existing features will change unless you set an individual ad group?s or keyword?s bid strategy to *ManualCpc*. For more details, see [Budget and Bid Strategies](~/guides/budget-bid-strategies.md).
 -  You can continue to set the ad group and keyword bids; however they will not be used by Bing Ads.
 -  Bing Ads will periodically change your stored ad group or keyword bid settings. You can continue to set new bids, however Bing Ads may change them at any type using this bid strategy type.
 -  You can continue to set bid adjustments e.g. for age, gender, or location; however with one exception they will not be used by Bing Ads. Bing Ads will not honor any bid adjustments, unless you have set a bid adjustment of -100% (opt out).
 -  Whether you chose the *DailyBudgetAccelerated* or *DailyBudgetStandard* budget type, Bing Ads will use the *DailyBudgetStandard* budget type.

Also note that you must have conversion tracking (a UET tag and a conversion goal) set up for the *EnhancedCpc*, *MaxConversions*, and *TargetCpa* bid strategy types to work. See [Universal Event Tracking](~/guides/universal-event-tracking.md) for more information.

To set the *MaxConversions* or *TargetCpa* bid strategy types, the campaign must have at least 15 conversions in the last 30 days. If you try to add or update a campaign to use one of these strategy types, the requested operation will fail if there is not enough conversion history. If an active campaign uses one of these bid strategy types, and then ceases to meet the minimum conversion history requirement at any time, Bing Ads will stop auto bidding but will continue to use the *DailyBudgetStandard* budget type. For a new campaign we recommend that you start with *EnhancedCpc* and then when the campaign has enough conversion history, you can update it to use either the *MaxConversions* or *TargetCpa* bid strategy.

> [!NOTE]
> Not everyone has this feature yet. If you don?t, don?t worry. It?s coming soon.
> 
> The *TargetCpa* bid strategy is available only to advertisers from the following countries: Australia, Canada, France, Germany, United Kingdom, and United States.

## Syntax
```xml
<xs:complexType name="TargetCpaBiddingScheme" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:BiddingScheme">
      <xs:sequence>
        <xs:element minOccurs="0" name="MaxCpc" nillable="true" type="tns:Bid" />
        <xs:element name="TargetCpa" nillable="true" type="xs:double" />
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
|<a name="type"></a>Type|The type of the bidding scheme. This value is *TargetCpaBiddingScheme* when you retrieve a target CPA bidding scheme. For more information about bidding scheme types, see the [BiddingScheme Data Object Remarks](../campaign-management/biddingscheme.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

