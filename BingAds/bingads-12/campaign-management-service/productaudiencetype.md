---
title: ProductAudienceType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
---
# ProductAudienceType Value Set - Campaign Management
Reserved.

## Syntax
```xml
<xs:simpleType name="ProductAudienceType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="GeneralVisitors" />
        <xs:enumeration value="ProductSearchers" />
        <xs:enumeration value="ProductViewers" />
        <xs:enumeration value="ShoppingCartAbandoners" />
        <xs:enumeration value="PastBuyers" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="generalvisitors"></a>GeneralVisitors|Reserved.|
|<a name="pastbuyers"></a>PastBuyers|Reserved.|
|<a name="productsearchers"></a>ProductSearchers|Reserved.|
|<a name="productviewers"></a>ProductViewers|Reserved.|
|<a name="shoppingcartabandoners"></a>ShoppingCartAbandoners|Reserved.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[ProductAudience](productaudience.md)  
