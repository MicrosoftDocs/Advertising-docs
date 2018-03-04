---
title: Paging Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a paging object for the list of entities returned using one of the search operations, for example SearchAccounts, SearchClientLinks, or SearchCustomers.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# Paging Data Object - Customer Management
Defines a paging object for the list of entities returned using one of the search operations, for example [SearchAccounts](searchaccounts.md), [SearchClientLinks](searchclientlinks.md), or [SearchCustomers](searchcustomers.md).

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
|<a name="size"></a>Size|The page size and the number of results to return in the specified page. The maximum size is 1,000.|**int**|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11/Entities  

## Used By
[SearchAccounts](searchaccounts.md)  
[SearchClientLinks](searchclientlinks.md)  
[SearchCustomers](searchcustomers.md)  
