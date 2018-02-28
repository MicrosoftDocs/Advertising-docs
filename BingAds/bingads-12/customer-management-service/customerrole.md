---
title: CustomerRole Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.
# CustomerRole Data Object - Customer Management
Reserved.

## Syntax
```xml
<xs:complexType name="CustomerRole" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="RoleId" type="xs:int" />
    <xs:element minOccurs="0" name="CustomerId" type="xs:long" />
    <xs:element minOccurs="0" name="AccountIds" nillable="true" type="q4:ArrayOflong" xmlns:q4="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountids"></a>AccountIds|Reserved.|**long** array|
|<a name="customerid"></a>CustomerId|Reserved.|**long**|
|<a name="roleid"></a>RoleId|Reserved.|**int**|

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12/Entities  

## Used By
[GetUser](getuser.md)  
