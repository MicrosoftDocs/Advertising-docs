---
title: CustomerInfo Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a customer identification object that contains information that identifies a customer.
---
# CustomerInfo Data Object - Customer Management
Defines a customer identification object that contains information that identifies a customer.

## Syntax
```xml
<xs:complexType name="CustomerInfo" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Name" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="id"></a>Id|The system generated identifier of the customer.|**long**|
|<a name="name"></a>Name|The name of the customer.|**string**|

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12/Entities  

## Used By
[AdvertiserAccount](advertiseraccount.md)  
[GetCustomersInfo](getcustomersinfo.md)  
