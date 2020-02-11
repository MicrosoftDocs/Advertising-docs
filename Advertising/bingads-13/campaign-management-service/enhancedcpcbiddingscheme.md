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

With the *EnhancedCpc* (enhanced cost per click) bid strategy, you set your ad group and keyword bids, and Microsoft Advertising will automatically adjust your bids in real time to increase your chances for a conversion. Your bid will go higher on searches that are more likely to convert and lower on searches less likely to convert (up or down, this change will be made after we apply any bid adjustments you have set). Over the long haul, though, we will try to make sure that your average CPC is not higher than your bid. If you haven't optimized your campaign yet, Enhanced CPC should reduce your cost per conversion and increase your total conversion count while respecting your current budget.  

Differing from the *MaxClicks*, *MaxConversions*, *TargetCpa*, and *TargetRoas* bid strategies, with the *EnhancedCpc* bid strategy, Microsoft Advertising will not actually change your stored ad group or keyword bid settings. You can continue to set new bids, and we will use the new values as a starting point next opportunity.

> [!TIP] 
> You can set your campaign's bid strategy to EnhancedCpc, MaxClicks, MaxConversions, TargetCpa, or TargetRoas and then, at any time, set an individual ad group's or keyword's bid strategy to ManualCpc.  

> [!NOTE]
> For search ad and dynamic search ad campaigns, the *EnhancedCpc* bid strategy is available to all advertisers worldwide. Note that we will only "enhance" your bids when your ads serve in the following countries/regions: Australia, Canada, France, Germany, India, Italy, Netherlands, Spain, Sweden, Switzerland, United Kingdom, and United States. When your ads serve outside of these countries/regions, your manual bids are unaffected.  
> 
> For Microsoft Shopping Campaigns, the *EnhancedCpc* bid strategy is available to advertisers in Australia, Canada, France, Germany, India, United Kingdom, and United States.

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
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

