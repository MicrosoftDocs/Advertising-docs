---
title: SortOrder Value Set - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the ascending or descending sort order of results for one of the search operations, for example SearchAccounts, SearchClientLinks, or SearchCustomers.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# SortOrder Value Set - Customer Management
Defines the ascending or descending sort order of results for one of the search operations, for example [SearchAccounts](searchaccounts.md), [SearchClientLinks](searchclientlinks.md), or [SearchCustomers](searchcustomers.md).

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
Service: [CustomerManagementService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v13  

## Used By
[OrderBy](orderby.md)  
