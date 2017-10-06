---
title: CriterionBid Data Object
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a base class for criterion bids.
---
# CriterionBid Data Object
Defines a base class for criterion bids.

Do not try to instantiate a *CriterionBid*. You can create the following object that derives from it.
-   [BidMultiplier](../campaign-management-service/bidmultiplier.md)  
-   [FixedBid](../campaign-management-service/fixedbid.md)  

For a list of criterion bids that you can use with [BiddableCampaignCriterion](../campaign-management-service/biddablecampaigncriterion.md), see the [CampaignCriterionType](../campaign-management-service/campaigncriteriontype.md) value set.

For a list of criterion bids that you can use with [BiddableAdGroupCriterion](../campaign-management-service/biddableadgroupcriterion.md), see the [AdGroupCriterionType](../campaign-management-service/adgroupcriteriontype.md) value set.

## Syntax
```xml
<xs:complexType name="CriterionBid" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Type" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of criterion bid. For more information, see [Remarks](#remarks).|**string**|

## <a name="remarks"></a>Remarks
For Java and the .NET languages, do not set the *Type* element because the value is determined by whether you instantiate a bid multiplier or fixed bid.

If you generate the SOAP manually, use the *type* attribute of the `<CriterionBid>` node (as shown in the following example) to specify the type of criterion.

```xml
<CriterionBid i:type="BidMultiplier" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
     . . .
</CriterionBid>
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[BiddableAdGroupCriterion](biddableadgroupcriterion.md)  
[BiddableCampaignCriterion](biddablecampaigncriterion.md)  
