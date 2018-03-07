---
title: ManualCpcBiddingScheme Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that represents the manual CPC bid strategy type.
---
# ManualCpcBiddingScheme Data Object - Campaign Management
Defines an object that represents the manual CPC bid strategy type. 

This is the default bid strategy type for your campaigns. Use the manual CPC bid strategy type if you will set your ad group and keyword bids, and Bing Ads will use these bids every time. 

> [!TIP]
> You can set your campaign's bid strategy to [EnhancedCpcBiddingScheme](enhancedcpcbiddingscheme.md), [MaxClicksBiddingScheme](maxclicksbiddingscheme.md), [MaxConversionsBiddingScheme](maxconversionsbiddingscheme.md), or [TargetCpaBiddingScheme](targetcpabiddingscheme.md) and then, at any time, set an individual ad group's or keyword's bid strategy to Manual CPC.

## Syntax
```xml
<xs:complexType name="ManualCpcBiddingScheme" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:BiddingScheme">
      <xs:sequence />
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [ManualCpcBiddingScheme](manualcpcbiddingscheme.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsbiddingscheme"></a>Inherited Elements from BiddingScheme
The [ManualCpcBiddingScheme](manualcpcbiddingscheme.md) object derives from the [BiddingScheme](biddingscheme.md) object, and inherits the following elements. The descriptions below are specific to [ManualCpcBiddingScheme](manualcpcbiddingscheme.md), and might not apply to other objects that inherit the same elements from the [BiddingScheme](biddingscheme.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the bidding scheme. This value is *ManualCpcBiddingScheme* when you retrieve a manual CPC bidding scheme. For more information about bidding scheme types, see the [BiddingScheme Data Object Remarks](biddingscheme.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

