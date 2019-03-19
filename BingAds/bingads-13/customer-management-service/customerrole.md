---
title: CustomerRole Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the role a user has for one customer or list of accounts within a customer.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# CustomerRole Data Object - Customer Management
Defines the role a user has for one customer or list of accounts within a customer.

If a user has access to multiple customers, then multiple [CustomerRole](customerrole.md) objects are returned via the [GetUser](getuser.md) operation.

## Syntax
```xml
<xs:complexType name="CustomerRole" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="RoleId" type="xs:int" />
    <xs:element minOccurs="0" name="CustomerId" type="xs:long" />
    <xs:element minOccurs="0" name="AccountIds" nillable="true" type="q5:ArrayOflong" xmlns:q5="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element minOccurs="0" name="LinkedAccountIds" nillable="true" type="q6:ArrayOflong" xmlns:q6="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
      <xs:annotation>
        <xs:appinfo>
          <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
        </xs:appinfo>
      </xs:annotation>
    </xs:element>
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountids"></a>AccountIds|The list of accounts that the user can access in the customer.<br/><br/>If this element is nil, the user has access to all of the accounts (current and future) in the customer.|**long** array|
|<a name="customerid"></a>CustomerId|The identifier of the [Customer](customer.md) that the user can access.|**long**|
|<a name="linkedaccountids"></a>LinkedAccountIds|The list of linked accounts that the user can access as an agency on behalf of another customer.|**long** array|
|<a name="roleid"></a>RoleId|The role that the user has for each customer or list of accounts.<br/><br/>Possible values include the following:<br/>16 - The user has the **Advertiser Campaign Manager** role.<br/>33 - The user has the **Aggregator** role.<br/>41 - The user has the **Super Admin** role.<br/>100 - The user has the **ClientViewer** role.<br/>203 - The user has the **Standard** role.<br/><br/>For more information, see [User Roles and Available Service Operations](../guides/customer-accounts.md#userroles).|**int**|

## Requirements
Service: [CustomerManagementService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v13/Entities  

## Used By
[GetUser](getuser.md)  
