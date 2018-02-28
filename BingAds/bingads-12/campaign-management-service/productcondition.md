---
title: ProductCondition Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a condition that determines whether a product is selected from a customer's Bing Merchant Center catalog file.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.
# ProductCondition Data Object - Campaign Management
Defines a condition that determines whether a product is selected from a customer's Bing Merchant Center catalog file.

## Syntax
```xml
<xs:complexType name="ProductCondition" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Attribute" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Operand" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="attribute"></a>Attribute|The condition's attribute value.<br /><br />An attribute's value must exactly match the value specified in the customer's Bing Merchant Center catalog file.<br /><br />The available *Attribute* and *Operand* values vary depending on the criterion type.<br /><br />For [ProductScope](../campaign-management-service/productscope.md) and [ProductPartition](../campaign-management-service/productpartition.md) conditions, see [Bing Shopping Product Conditions](../guides/product-ads.md#conditions).<br /><br />**Add or Apply:** Required<br/>**Update:** Optional|**string**|
|<a name="operand"></a>Operand|The condition's operand. The operands implicitly include the equal operator. For example, read Brand as Brand=.<br /><br />**Add or Apply:** Required<br/>**Update:** Optional|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[ProductPartition](productpartition.md)  
[ProductScope](productscope.md)  
