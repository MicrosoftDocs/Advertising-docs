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

This is the default bid strategy type for your campaigns. Use the manual CPC bid strategy type if you will set your ad group and keyword bids, and Microsoft Advertising will use these bids every time. This is every campaign's default bid strategy via Bing Ads API unless you chose a different strategy when creating your campaign. 

> [!IMPORTANT]
> Starting in April 2021, you can only set the manual CPC bid strategy for audience campaigns. If you attempt to set manual CPC for any other campaign type, the request will be ignored without error and the bid strategy will be set to enhanced CPC. 
> 
> Also starting in April 2021, you cannot set any bid strategies for ad groups or keywords. Bid strategies can only be set at the campaign level. If you attempt to set bid strategies for ad groups or keywords, the request will be ignored without error. Ad groups and keywords will inherit their campaign's bid strategy. 

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
The [ManualCpcBiddingScheme](manualcpcbiddingscheme.md) object derives from the [BiddingScheme](biddingscheme.md) object, and inherits the following elements: [Type](#type). The descriptions below are specific to [ManualCpcBiddingScheme](manualcpcbiddingscheme.md), and might not apply to other objects that inherit the same elements from the [BiddingScheme](biddingscheme.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the bidding scheme. This value is *ManualCpcBiddingScheme* when you retrieve a manual CPC bidding scheme. For more information about bidding scheme types, see the [BiddingScheme Data Object Remarks](biddingscheme.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

