---
title: AccountType Value Set - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Defines the possible account types.
---
# AccountType Value Set - Customer Management
Defines the possible account types.

## Syntax
```xml
<xs:simpleType name="AccountType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Advertiser" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="advertiser"></a>Advertiser|An advertiser account.|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

## Used By
[Account](account.md)  
