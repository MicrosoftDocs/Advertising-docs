---
title: OrderByField Value Set - Customer Billing
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the field order of insertion orders returned using SearchInsertionOrders.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# OrderByField Value Set - Customer Billing
Defines the field order of insertion orders returned using [SearchInsertionOrders](searchinsertionorders.md).

## Syntax
```xml
<xs:simpleType name="OrderByField" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Id" />
    <xs:enumeration value="Name" />
    <xs:enumeration value="Number" />
    <xs:enumeration value="LifeCycleStatus" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="id"></a>Id|The order is determined by a predicate identifier.|
|<a name="lifecyclestatus"></a>LifeCycleStatus|The order is determined by a predicate life cycle status.<br /><br /> This value is reserved for future use.|
|<a name="name"></a>Name|The order is determined by a predicate name.|
|<a name="number"></a>Number|The order is determined by a predicate number.<br /><br /> This value is reserved for future use.|

## Requirements
Service: [CustomerBillingService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v12/CustomerBillingService.svc)  
Namespace: https\://bingads.microsoft.com/Billing/v12  

## Used By
[OrderBy](orderby.md)  
