---
title: AdGroupCriterionAction Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the action to apply to a BiddableAdGroupCriterion or NegativeAdGroupCriterion, specifically one that contains a ProductPartition.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# AdGroupCriterionAction Data Object - Campaign Management
Defines the action to apply to a [BiddableAdGroupCriterion](biddableadgroupcriterion.md) or [NegativeAdGroupCriterion](negativeadgroupcriterion.md), specifically one that contains a [ProductPartition](productpartition.md). You can send a group of [AdGroupCriterionAction](adgroupcriterionaction.md) objects, also known as a product group, to the [ApplyProductPartitionActions](applyproductpartitionactions.md) service operation.

## Syntax
```xml
<xs:complexType name="AdGroupCriterionAction" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="Action" type="tns:ItemAction" />
    <xs:element name="AdGroupCriterion" nillable="true" type="tns:AdGroupCriterion" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="action"></a>Action|The action to be applied for the *AdGroupCriterion*.|[ItemAction](itemaction.md)|
|<a name="adgroupcriterion"></a>AdGroupCriterion|The [BiddableAdGroupCriterion](biddableadgroupcriterion.md) or [NegativeAdGroupCriterion](negativeadgroupcriterion.md), either of which must contain a [ProductPartition](productpartition.md) criterion.<br/><br/>For the Update action, only the *CriterionBid* and *DestinationUrl* elements of the *AdGroupCriterion* are mutable. To update the order or structure of the product group, you cannot use the update action. You must delete ad group criterions and then add new product partitions instead.|[AdGroupCriterion](adgroupcriterion.md)|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[ApplyProductPartitionActions](applyproductpartitionactions.md)  
