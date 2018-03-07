---
title: CustomerRole Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the role a user has for each customer or list of accounts.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# CustomerRole Data Object - Customer Management
Defines the role a user has for each customer or list of accounts.

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
|<a name="accountids"></a>AccountIds|The list of accounts that the user can access.|**long** array|
|<a name="customerid"></a>CustomerId|The customer that the user can access.|**long**|
|<a name="roleid"></a>RoleId|The role that the user has for each customer or list of accounts.<br /><br />Possible values include the following:<br />16 - The user has the **Advertiser Campaign Manager** role.<br />33 - The user has the **Aggregator** role.<br />41 - The user has the **Super Admin** role.<br />100 - The user has the **ClientViewer** role.<br />203 - The user has the **Standard** role.<br /><br />For more information, see [User Roles and Available Service Operations](../guides/customer-accounts.md#userroles).|**int**|

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12/Entities  

## Used By
[GetUser](getuser.md)  
