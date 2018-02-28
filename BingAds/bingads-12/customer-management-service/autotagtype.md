---
title: AutoTagType Value Set - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
---
# AutoTagType Value Set - Customer Management

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Reserved.

## Syntax
```xml
<xs:simpleType name="AutoTagType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Inactive" />
    <xs:enumeration value="Preserve" />
    <xs:enumeration value="Replace" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="inactive"></a>Inactive|Reserved.|
|<a name="preserve"></a>Preserve|Reserved.|
|<a name="replace"></a>Replace|Reserved.|

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

## Used By
[AdvertiserAccount](advertiseraccount.md)  
