---
title: AdGroupCriterionAction Data Object
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# AdGroupCriterionAction Data Object
Defines the action to apply to a [BiddableAdGroupCriterion](../campaign-management/biddableadgroupcriterion.md) or [NegativeAdGroupCriterion](../campaign-management/negativeadgroupcriterion.md), specifically one that contains a [ProductPartition](../campaign-management/productpartition.md). You can send a group of [AdGroupCriterionAction](../campaign-management/adgroupcriterionaction.md) objects, also known as a product group, to the [ApplyProductPartitionActions](../campaign-management/applyproductpartitionactions.md) service operation.

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
|<a name="adgroupcriterion"></a>AdGroupCriterion|The [BiddableAdGroupCriterion](../campaign-management/biddableadgroupcriterion.md) or [NegativeAdGroupCriterion](../campaign-management/negativeadgroupcriterion.md), either of which must contain a [ProductPartition](../campaign-management/productpartition.md) criterion.<br/><br/>For the Update action, only the *CriterionBid* and *DestinationUrl* elements of the *AdGroupCriterion* are mutable. To update the order or structure of the product group, you cannot use the update action. You must delete ad group criterions and then add new product partitions instead.|[AdGroupCriterion](adgroupcriterion.md)|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[ApplyProductPartitionActions](applyproductpartitionactions.md)  
