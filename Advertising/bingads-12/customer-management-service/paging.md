---
title: Paging Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a paging object that you can use to request objects in batches.
---
# Paging Data Object - Customer Management
Defines a paging object that you can use to request objects in batches.

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
|<a name="index"></a>Index|The zero-based results page index.<br/><br/>For example to request the first page of results, set this value to 0 (zero).|**int**|
|<a name="size"></a>Size|The page size and the number of results to return in the specified page.<br/><br/>The maximum size is 1,000. If you do not set this element the default size is 0 (zero).|**int**|

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12/Entities  

## Used By
[SearchAccounts](searchaccounts.md)  
[SearchClientLinks](searchclientlinks.md)  
[SearchCustomers](searchcustomers.md)  
