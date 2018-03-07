---
title: UserInfo Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a user identification object that contains information that identifies a user.
---
# UserInfo Data Object - Customer Management
Defines a user identification object that contains information that identifies a user.

## Syntax
```xml
<xs:complexType name="UserInfo" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Id" type="xs:long" />
    <xs:element minOccurs="0" name="UserName" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="id"></a>Id|The system generated identifier of the user.|**long**|
|<a name="username"></a>UserName|The logon user name of the user.|**string**|

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12/Entities  

## Used By
[GetUsersInfo](getusersinfo.md)  
