---
title: CustomerLifeCycleStatus Value Set
ms.service: bing-ads-customer-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# CustomerLifeCycleStatus Value Set
Defines the possible status values of a customer.

## Syntax
```xml
<xs:simpleType name="CustomerLifeCycleStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Active" />
    <xs:enumeration value="Inactive" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="active"></a>Active|The customer is active.|
|<a name="inactive"></a>Inactive|The customer is inactive, which means that the customer was deleted.|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

## Used By
[Customer](customer.md)  
