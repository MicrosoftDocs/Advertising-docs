---
title: ProductPartition Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an ad group level product partition with one condition that helps determine whether a product from the Bing Merchant Center store gets served as a product ad.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# ProductPartition Data Object - Campaign Management
Defines an ad group level product partition with one condition that helps determine whether a product from the Bing Merchant Center store gets served as a product ad.

The *ProductPartition* criterion can be included within [BiddableAdGroupCriterion](../campaign-management-service/biddableadgroupcriterion.md) and [NegativeAdGroupCriterion](../campaign-management-service/negativeadgroupcriterion.md). Also note that campaign level [ProductScope](../campaign-management-service/productscope.md) can be added to [BiddableCampaignCriterion](../campaign-management-service/biddablecampaigncriterion.md). Duplicate or conflicting product conditions attempted within an ad group's product partition group will be rejected by the [ApplyProductPartitionActions](../campaign-management-service/applyproductpartitionactions.md) operation; however, the operation will not validate whether duplicate or conflicting conditions already exist within the campaign level [ProductScope](../campaign-management-service/productscope.md).

> [!TIP]
> For an implementation overview, see the [Bing Shopping Campaigns](../guides/product-ads.md) technical guide.

## Syntax
```xml
<xs:complexType name="ProductPartition" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Criterion">
      <xs:sequence>
        <xs:element name="Condition" nillable="true" type="tns:ProductCondition" />
        <xs:element name="ParentCriterionId" nillable="true" type="xs:long" />
        <xs:element name="PartitionType" type="tns:ProductPartitionType" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="condition"></a>Condition|A condition that helps determine whether a product from the Bing Merchant Center store gets served as an ad.<br /><br />Multiple product conditions can be specified by creating a tree of *ProductPartition* objects using [ApplyProductPartitionActions](../campaign-management-service/applyproductpartitionactions.md). For a catalog item to be served as an ad, it must meet all conditions. To get a list of all conditions for an ad group, call [GetAdGroupCriterionsByIds](../campaign-management-service/getadgroupcriterionsbyids.md) with the *AdGroupCriterionIds* element set to null and the *CriterionType* element set to ProductPartition.<br/><br/>**Add:** Required<br/>**Update:** Update is not supported for this object|[ProductCondition](productcondition.md)|
|<a name="parentcriterionid"></a>ParentCriterionId|The identifier of the parent [BiddableAdGroupCriterion](../campaign-management-service/biddableadgroupcriterion.md) or [NegativeAdGroupCriterion](../campaign-management-service/negativeadgroupcriterion.md).<br /><br /> This element must be set to null if the product partition represents the root node of a product partition tree.<br/><br/>**Add:** Required<br/>**Update:** Update is not supported for this object<br/>**Delete:** Required|**long**|
|<a name="partitiontype"></a>PartitionType|The type of product partition, for example *Subdivision* or *Unit*.<br/><br/>**Add:** Required<br/>**Update:** Update is not supported for this object|[ProductPartitionType](productpartitiontype.md)|

The [ProductPartition](productpartition.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementscriterion"></a>Inherited Elements from Criterion
The [ProductPartition](productpartition.md) object derives from the [Criterion](criterion.md) object, and inherits the following elements. The descriptions below are specific to [ProductPartition](productpartition.md), and might not apply to other objects that inherit the same elements from the [Criterion](criterion.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the criterion. This value is *ProductPartition* when you retrieve a product partition criterion. For more information about criterion types, see the [Criterion Data Object Remarks](../campaign-management-service/criterion.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

