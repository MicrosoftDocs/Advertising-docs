---
title: EnhancedCpcBiddingScheme Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that represents the enhanced CPC bid strategy type.
---
# EnhancedCpcBiddingScheme Data Object - Campaign Management

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Defines an object that represents the enhanced CPC bid strategy type.

Use the enhanced CPC bid strategy type to set your ad group and keyword bids, and Bing Ads will automatically adjust your bids in real time so that you bid up to 30% higher on users that are more likely to convert and up to 100% less on users less likely to convert. Bing Ads will still respect your campaign budget limit.

> [!IMPORTANT]
> If the campaign bid strategy type is set to *MaxClicks*, *MaxConversions*, or *TargetCpa*, the behavior of existing features will change unless you set an individual ad group's or keyword's bid strategy to *ManualCpc*. For more details, see [Budget and Bid Strategies](~/guides/budget-bid-strategies.md).
 -  You can continue to set the ad group and keyword bids; however they will not be used by Bing Ads.
 -  Bing Ads will periodically change your stored ad group or keyword bid settings. You can continue to set new bids, however Bing Ads may change them at any type using this bid strategy type.
 -  You can continue to set bid adjustments e.g. for age, gender, or location; however, the multiplier will inform rather than directly modify or override the automated bid. For auto bidding the multiplier is used as a weighted percentage to inform Bing Ads about how much you value the criterion relative to other criteria. For example, a -50% bid multiplier for a mobile device criterion with the Max Conversions bid strategy to indicate that you value conversions from mobile traffic half as much as other device types. The same bid multiplier with the Max Clicks bid strategy would indicate that you value clicks on mobile half as much as other device types. The valid range of values that you can use to inform auto bidding is -100.00 through 30.00.
 -  Whether you chose the *DailyBudgetAccelerated* or *DailyBudgetStandard* budget type, Bing Ads will use the *DailyBudgetStandard* budget type.

Also note that you must have conversion tracking (a UET tag and a conversion goal) set up for the *EnhancedCpc*, *MaxConversions*, and *TargetCpa* bid strategy types to work. See [Universal Event Tracking](~/guides/universal-event-tracking.md) for more information.

To set the *MaxConversions* or *TargetCpa* bid strategy types, the campaign must have at least 15 conversions in the last 30 days. If you try to add or update a campaign to use one of these strategy types, the requested operation will fail if there is not enough conversion history. If an active campaign uses one of these bid strategy types, and then ceases to meet the minimum conversion history requirement at any time, Bing Ads will stop auto bidding but will continue to use the *DailyBudgetStandard* budget type. For a new campaign we recommend that you start with *EnhancedCpc* and then when the campaign has enough conversion history, you can update it to use either the *MaxConversions* or *TargetCpa* bid strategy.

## Syntax
```xml
<xs:complexType name="EnhancedCpcBiddingScheme" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:BiddingScheme">
      <xs:sequence />
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [EnhancedCpcBiddingScheme](enhancedcpcbiddingscheme.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsbiddingscheme"></a>Inherited Elements from BiddingScheme
The [EnhancedCpcBiddingScheme](enhancedcpcbiddingscheme.md) object derives from the [BiddingScheme](biddingscheme.md) object, and inherits the following elements. The descriptions below are specific to [EnhancedCpcBiddingScheme](enhancedcpcbiddingscheme.md), and might not apply to other objects that inherit the same elements from the [BiddingScheme](biddingscheme.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the bidding scheme. This value is *EnhancedCpcBiddingScheme* when you retrieve an enhanced CPC bidding scheme. For more information about bidding scheme types, see the [BiddingScheme Data Object Remarks](../campaign-management-service/biddingscheme.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

