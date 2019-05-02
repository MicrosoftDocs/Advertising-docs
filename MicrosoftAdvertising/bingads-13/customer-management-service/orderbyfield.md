---
title: OrderByField Value Set - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the field order of entities returned using one of the search operations, for example SearchAccounts, SearchClientLinks, or SearchCustomers.
---
# OrderByField Value Set - Customer Management
Defines the field order of entities returned using one of the search operations, for example [SearchAccounts](searchaccounts.md), [SearchClientLinks](searchclientlinks.md), or [SearchCustomers](searchcustomers.md).

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
|<a name="lifecyclestatus"></a>LifeCycleStatus|The order is determined by a predicate life cycle status.|
|<a name="name"></a>Name|The order is determined by a predicate name.|
|<a name="number"></a>Number|The order is determined by a predicate number.|

## Requirements
Service: [CustomerManagementService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v13  

## Used By
[OrderBy](orderby.md)  
