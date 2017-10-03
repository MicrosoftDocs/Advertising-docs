---
title: OrderBy Data Object
ms.service: bing-ads-customer-billing
ms.topic: article
author: eric-urban
ms.author: eur
---
# OrderBy Data Object
Defines an order for the list of insertion orders returned using the [SearchInsertionOrders](../customer-billing/searchinsertionorders.md) operation.

## Syntax
```xml
<xs:complexType name="OrderBy" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Field" type="tns:OrderByField" />
    <xs:element minOccurs="0" name="Order" type="tns:SortOrder" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="field"></a>Field|Determines the field to order the results. For example order the results by *Id*.|[OrderByField](orderbyfield.md)|
|<a name="order"></a>Order|Determines whether the results are ascending or descending.|[SortOrder](sortorder.md)|

## Requirements
Service: [CustomerBillingService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v11/CustomerBillingService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11/Entities  

## Used By
[SearchInsertionOrders](searchinsertionorders.md)  
