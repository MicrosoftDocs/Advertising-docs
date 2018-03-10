---
title: ProductScope Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a campaign level product scope with list of conditions that help determine whether a product from the Bing Merchant Center store gets served as a product ad.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# ProductScope Data Object - Campaign Management
Defines a campaign level product scope with list of conditions that help determine whether a product from the Bing Merchant Center store gets served as a product ad.

The *ProductScope* criterion can only be included within [BiddableCampaignCriterion](biddablecampaigncriterion.md). Also note that ad group level [ProductPartition](productpartition.md) can be added to [BiddableAdGroupCriterion](biddableadgroupcriterion.md) and [NegativeAdGroupCriterion](negativeadgroupcriterion.md). Duplicate or conflicting product conditions attempted within an ad group's [ProductPartition](productpartition.md) group will be rejected by the [ApplyProductPartitionActions](applyproductpartitionactions.md) operation; however, the operation will not validate whether duplicate or conflicting conditions already exist within the campaign level product scope.

> [!TIP]
> For an implementation overview, see the [Bing Shopping Campaigns](../guides/product-ads.md) technical guide.

## Syntax
```xml
<xs:complexType name="ProductScope" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Criterion">
      <xs:sequence>
        <xs:element minOccurs="0" name="Conditions" nillable="true" type="tns:ArrayOfProductCondition" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="conditions"></a>Conditions|A list of up to 7 product conditions that helps determine whether a product from the Bing Merchant Center store gets served as an ad.<br /><br /> Conditions may be returned by Bing Ads services in a different order from the order that you submitted.<br /><br />**Add:** Required<br/>**Update:** Required|[ProductCondition](productcondition.md) array|

The [ProductScope](productscope.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementscriterion"></a>Inherited Elements from Criterion
The [ProductScope](productscope.md) object derives from the [Criterion](criterion.md) object, and inherits the following elements. The descriptions below are specific to [ProductScope](productscope.md), and might not apply to other objects that inherit the same elements from the [Criterion](criterion.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the criterion. This value is *ProductScope* when you retrieve a product scope criterion. For more information about criterion types, see the [Criterion Data Object Remarks](criterion.md#remarks).<br /><br />**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

