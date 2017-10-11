---
title: SortOrder Value Set
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the ascending or descending sort order of results for one of the search operations, for example SearchAccounts, [SearchClientLinks](../customer-management-service/searchclientlinks.md), or [SearchCustomers](../customer-management-service/searchcustomers.md).
---
# SortOrder Value Set
Defines the ascending or descending sort order of results for one of the search operations, for example [SearchAccounts](../customer-management-service/searchaccounts.md), [SearchClientLinks](../customer-management-service/searchclientlinks.md), or [SearchCustomers](../customer-management-service/searchcustomers.md).

## Syntax
```xml
<xs:simpleType name="SortOrder" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Ascending" />
    <xs:enumeration value="Descending" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="ascending"></a>Ascending|The results will be sorted ascending.|
|<a name="descending"></a>Descending|The results will be sorted descending.|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

## Used By
[OrderBy](orderby.md)  
