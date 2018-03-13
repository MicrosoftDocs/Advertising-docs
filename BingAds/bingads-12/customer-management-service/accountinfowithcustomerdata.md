---
title: AccountInfoWithCustomerData Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains information that identifies an account and the customer that manages or owns the account.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AccountInfoWithCustomerData Data Object - Customer Management
Defines an object that contains information that identifies an account and the customer that manages or owns the account.

## Syntax
```xml
<xs:complexType name="AccountInfoWithCustomerData" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="CustomerId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="CustomerName" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="AccountId" type="xs:long" />
    <xs:element minOccurs="0" name="AccountName" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="AccountNumber" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="AccountLifeCycleStatus" type="tns:AccountLifeCycleStatus" />
    <xs:element minOccurs="0" name="PauseReason" nillable="true" type="xs:unsignedByte" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The system generated identifier of the account.|**long**|
|<a name="accountlifecyclestatus"></a>AccountLifeCycleStatus|The status of the account.|[AccountLifeCycleStatus](accountlifecyclestatus.md)|
|<a name="accountname"></a>AccountName|The name of the account.|**string**|
|<a name="accountnumber"></a>AccountNumber|The system generated account number that is used to identify the account in the Bing Ads web application. The account number has the form X*nnnnnnn*, where *nnnnnnn* is a series of digits.|**string**|
|<a name="customerid"></a>CustomerId|The system generated identifier of the customer that manages or owns the account.<br /><br />If this account is the result of an account match using the [FindAccountsOrCustomersInfo](findaccountsorcustomersinfo.md), the customer identifier is that of the customer that owns the account. However, if the account is the result of a customer match, the customer identifier is that of the reseller that manages the account, if the account is managed by a reseller; otherwise, the identifier is that of the customer that owns the account.|**long**|
|<a name="customername"></a>CustomerName|The name of the customer that manages or owns the account.|**string**|
|<a name="pausereason"></a>PauseReason|A flag value that indicates who paused the account. The following are the possible values:<br /><br />1 - The user paused the account.<br /><br />2 - The billing service paused the account.<br /><br />4 - The user and billing service paused the account.|**unsignedByte**|

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12/Entities  

## Used By
[FindAccountsOrCustomersInfo](findaccountsorcustomersinfo.md)  
