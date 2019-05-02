---
title: Predicate Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a predicate for the list of entities requested using one of the search operations, for example SearchAccounts, SearchClientLinks, SearchCustomers, or SearchUserInvitations.
---
# Predicate Data Object - Customer Management
Defines a predicate for the list of entities requested using one of the search operations, for example [SearchAccounts](searchaccounts.md), [SearchClientLinks](searchclientlinks.md), [SearchCustomers](searchcustomers.md), or [SearchUserInvitations](searchuserinvitations.md).

## Syntax
```xml
<xs:complexType name="Predicate" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Field" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Operator" type="tns:PredicateOperator" />
    <xs:element minOccurs="0" name="Value" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="field"></a>Field|The name of the element for  the object you are searching.<br/><br/>For possible values, see the [Remarks](#remarks) below.|**string**|
|<a name="operator"></a>Operator|Defines the relationship between the field and the value.|[PredicateOperator](predicateoperator.md)|
|<a name="value"></a>Value|The string to search in the specified field.<br/><br/>The length of this string must be four or greater, unless the field is set to MarketCountry or MarketLanguage.|**string**|

## <a name="remarks"></a>Remarks
The supported Field element and Operator elements of a Predicate object for each service operation are provided in detail below. 

### <a name="searchaccounts"></a>SearchAccounts Predicates
For the [SearchAccounts](searchaccounts.md) service operation, the following are supported Field element and Operator elements of a Predicate object.

|Field|Operator|Description|
|---------|------------|---------------|
|AccountId|Equals<br/><br/>In|Use this field to search the Id element of the [AdvertiserAccount](advertiseraccount.md).|
|AccountLifeCycleStatus|Equals|Use this field to search the AccountLifeCycleStatus element of the [AdvertiserAccount](advertiseraccount.md).<br/><br/>Possible values include any string representation of the [AccountLifeCycleStatus](accountlifecyclestatus.md), for example `Value = AccountLifeCycleStatus.Active.ToString()` or `Value="Active"`.|
|AccountName|Contains<br/><br/>Equals|Use this field to search the Name element of the [AdvertiserAccount](advertiseraccount.md).|
|AccountNumber|Contains<br/><br/>Equals<br/><br/>In|Use this field to search the Number element of the [AdvertiserAccount](advertiseraccount.md).|
|CustomerId|Equals|Use this field to search the Id element of the [Customer](customer.md).|
|UserId|Equals|Use this field to search the UserId element of the [User](user.md).|

### <a name="searchclientlinks"></a>SearchClientLinks Predicates
For the [SearchClientLinks](searchclientlinks.md) service operation, the following are supported Field element and Operator elements of a Predicate object.

|Field|Operator|Description|
|---------|------------|---------------|
|ClientAccountId|Equals<br/><br/>In|Search for [ClientLink](clientlink.md) objects by the client account identifier.|
|ManagingCustomerId|Equals|Search for [ClientLink](clientlink.md) objects by the managing customer identifier.|

### <a name="searchcustomers"></a>SearchCustomers Predicates
For the [SearchCustomers](searchcustomers.md) service operation, the following are supported Field element and Operator elements of a Predicate object.

|Field|Operator|Description|
|---------|------------|---------------|
|AccountId|Equals|Use this field to search the Id element of the [AdvertiserAccount](advertiseraccount.md).|
|AccountName|Contains<br/><br/>Equals|Use this field to search the Name element of the [AdvertiserAccount](advertiseraccount.md).|
|AccountNumber|Contains<br/><br/>Equals|Use this field to search the Number element of the [AdvertiserAccount](advertiseraccount.md).|
|ApplicationScope|Equals|For internal use only.|
|CreatedDate|GreaterThanEquals<br/><br/>LessThanEquals|Use this field to search the date when the customer was created or signed up.<br/><br/>The date is stored in Coordinated Universal Time (UTC). Only the month, day, and year of the specified string are used for search. If you specify the hour, minutes, and seconds of a date they will be ignored.<br/><br/>For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|
|CustomerId|Equals<br/><br/>In|Use this field to search the Id element of the [Customer](customer.md).|
|CustomerName|Contains<br/><br/>Equals|Use this field to search the Name element of the [Customer](customer.md).|
|CustomerNumber|Contains<br/><br/>Equals|Use this field to search the Number element of the [Customer](customer.md).|
|MarketCountry|Equals|Use this field to search the MarketCountry element of the [Customer](customer.md).<br/><br/>The MarketCountry and MarketLanguage predicate fields are not required; however, if either is specified then both are required.|
|MarketLanguage|Equals|Use this field to search the MarketLanguage element of the [Customer](customer.md).<br/><br/>The MarketCountry and MarketLanguage predicate fields are not required; however, if either is specified then both are required.|
|UserName|Equals|Use this field to search the UserName element of the [User](user.md).|

### <a name="searchuserinvitations"></a>SearchUserInvitations Predicates
For the [SearchUserInvitations](searchuserinvitations.md) service operation, the following are supported Field element and Operator elements of a Predicate object.

|Field|Operator|Description|
|---------|------------|---------------|
|CustomerId|Equals|Use this field to search the CustomerId element of the [UserInvitation](userinvitation.md).|

## Requirements
Service: [CustomerManagementService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v13/Entities  

## Used By
[SearchAccounts](searchaccounts.md)  
[SearchClientLinks](searchclientlinks.md)  
[SearchCustomers](searchcustomers.md)  
[SearchUserInvitations](searchuserinvitations.md)  
