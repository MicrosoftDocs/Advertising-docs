---
title: ApplicationType Value Set
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible application types.
---
# ApplicationType Value Set
Defines the possible application types.

## Syntax
```xml
<xs:simpleType name="ApplicationType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Advertiser" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="advertiser"></a>Advertiser|An advertiser application.|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

## Used By
[FindAccounts](findaccounts.md)  
[FindAccountsOrCustomersInfo](findaccountsorcustomersinfo.md)  
[GetCustomersInfo](getcustomersinfo.md)  
[SearchCustomers](searchcustomers.md)  
[SignupCustomer](signupcustomer.md)  
[User](user.md)  
