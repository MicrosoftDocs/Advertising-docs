---
title: AccountInfo Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an account identification object that contains information that identifies an account.
---
# AccountInfo Data Object - Customer Management
Defines an account identification object that contains information that identifies an account.

## Syntax
```xml
<xs:complexType name="AccountInfo" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Id" type="xs:long" />
    <xs:element minOccurs="0" name="Name" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Number" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="AccountLifeCycleStatus" type="tns:AccountLifeCycleStatus" />
    <xs:element minOccurs="0" name="PauseReason" nillable="true" type="xs:unsignedByte" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountlifecyclestatus"></a>AccountLifeCycleStatus|The status of the account.|[AccountLifeCycleStatus](accountlifecyclestatus.md)|
|<a name="id"></a>Id|The system generated identifier of the account.|**long**|
|<a name="name"></a>Name|The name of the account.|**string**|
|<a name="number"></a>Number|The account number.|**string**|
|<a name="pausereason"></a>PauseReason|A flag value that indicates who paused the account. The following are the possible values:<br /><br />1 - The user paused the account.<br /><br />2 - The billing service paused the account.<br /><br />4 - The user and billing service paused the account.|**unsignedByte**|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11/Entities  

## Used By
[FindAccounts](findaccounts.md)  
[GetAccountsInfo](getaccountsinfo.md)  
