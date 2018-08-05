---
title: EnhancedCpcBiddingScheme Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that represents the enhanced CPC bid strategy type.
---
# EnhancedCpcBiddingScheme Data Object - Campaign Management
Defines an object that represents the enhanced CPC bid strategy type.

With the *EnhancedCpc* (enhanced cost per click) bid strategy, you set your ad group and keyword bids, and Bing Ads automatically adjusts your bids in real time to increase your chances for a conversion. Your bid will go up to 30% higher on searches that are more likely to convert and up to 100% lower on searches less likely to convert (up or down, this change will be made after we apply any bid adjustments you have set).

Bing Ads looks for patterns to identify searches that are most likely to result in a conversion. When we see a good opportunity, we increase your bid up to 30% to capitalize on it. On the other hand, if the patterns show that a conversion is less likely, we lower your bid. Up or down, this change will be made after we apply any bid adjustments you have set. If you haven't optimized your campaign yet, Enhanced CPC should reduce your cost per conversion and increase your total conversion count while respecting your current budget.

Differing from the *MaxClicks*, *MaxConversions*, and *TargetCpa* bid strategies, with the *EnhancedCpc* bid strategy, Bing Ads will not actually change your stored ad group or keyword bid settings. You can continue to set new bids, and we will use the new values as a starting point next opportunity; however, assuming the *EnhancedCpc* bid strategy remains in place, we will continue to modify the new bid from negative 100% through positive 30%.

> [!TIP]
> For a new campaign we recommend that you start with *EnhancedCpc* and then when the campaign has enough conversion history, you can update it to use either the *MaxConversions* or *TargetCpa* bid strategy.

> [!NOTE]
> The *EnhancedCpc* bid strategy is available only for Dynamic Search Ads, Search, and Shopping campaigns.
> 
> The *EnhancedCpc* bid strategy is available to all advertisers worldwide. Note that we will only "enhance" your bids when your ads serve in the following countries/regions: Australia, Canada, France, Germany, India, Italy, Netherlands, Spain, Sweden, Switzerland, United Kingdom, and United States. When your ads serve outside of these countries/regions, your manual bids are unaffected.
> 
> For Bing Shopping Campaigns, Enhanced CPC is available only to advertisers in France, Germany, United Kingdom, and United States.

Also note that you must have conversion tracking (a UET tag and a conversion goal) set up for the *EnhancedCpc*, *MaxConversions*, and *TargetCpa* bid strategy types to work. See [Universal Event Tracking](../guides/universal-event-tracking.md) for more information.

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
|<a name="type"></a>Type|The type of the bidding scheme. This value is *EnhancedCpcBiddingScheme* when you retrieve an enhanced CPC bidding scheme. For more information about bidding scheme types, see the [BiddingScheme Data Object Remarks](biddingscheme.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

