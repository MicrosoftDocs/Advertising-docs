---
title: OperationError Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an error object that contains the details that explain why the service operation failed.
---
# OperationError Data Object - Customer Management
Defines an error object that contains the details that explain why the service operation failed.

## Syntax
```xml
<xs:complexType name="OperationError" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Code" type="xs:int" />
    <xs:element minOccurs="0" name="Details" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Message" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="code"></a>Code|A numeric error code that identifies the error|**int**|
|<a name="details"></a>Details|A message that provides additional details about the error. This string can be empty.|**string**|
|<a name="message"></a>Message|A message that describes the error.|**string**|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11/Exception  

## Used By
[AddClientLinks](addclientlinks.md)  
[ApiFault](apifault.md)  
[UpdateClientLinks](updateclientlinks.md)  
