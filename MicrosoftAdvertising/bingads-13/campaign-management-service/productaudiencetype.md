---
title: ProductAudienceType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible types of product audiences.
---
# ProductAudienceType Value Set - Campaign Management
Defines the possible types of product audiences.

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
|<a name="generalvisitors"></a>GeneralVisitors|The audience includes general visitors.|
|<a name="pastbuyers"></a>PastBuyers|The audience includes past buyers.|
|<a name="productsearchers"></a>ProductSearchers|The audience includes product searchers.|
|<a name="productviewers"></a>ProductViewers|The audience includes product viewers.|
|<a name="shoppingcartabandoners"></a>ShoppingCartAbandoners|The audience includes shopping cart abandoners.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[ProductAudience](productaudience.md)  
