---
title: Paging Data Object - Customer Billing
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a paging object for the list of insertion orders returned using the SearchInsertionOrders operation.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.
# Paging Data Object - Customer Billing
Defines a paging object for the list of insertion orders returned using the [SearchInsertionOrders](../customer-billing-service/searchinsertionorders.md) operation.

## Syntax
```xml
<xs:complexType name="Paging" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Index" type="xs:int" />
    <xs:element minOccurs="0" name="Size" type="xs:int" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="index"></a>Index|The zero-based results page index. For example to request the first page of results, set this value to 0 (zero).|**int**|
|<a name="size"></a>Size|The page size and the number of results to return in the specified page.<br /><br />The maximum size is 1,000.|**int**|

## Requirements
Service: [CustomerBillingService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v12/CustomerBillingService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12/Entities  

## Used By
[SearchInsertionOrders](searchinsertionorders.md)  
