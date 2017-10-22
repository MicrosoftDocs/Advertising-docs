---
title: Account Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: "article"
ms.date: 11/1/2017
author: eric-urban
ms.author: eur
description: Defines an account.
---
# Account Data Object - Customer Management
Defines an account. This is the base object from which the advertising accounts derive.

Do not try to instantiate an *Account*. You can create the [AdvertiserAccount](../customer-management-service/advertiseraccount.md) object that derives from it. 

## Syntax
```xml
<xs:complexType name="Account" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AccountType" type="tns:AccountType" />
    <xs:element minOccurs="0" name="BillToCustomerId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="CountryCode" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="CurrencyType" nillable="true" type="tns:CurrencyType" />
    <xs:element minOccurs="0" name="AccountFinancialStatus" nillable="true" type="tns:AccountFinancialStatus" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Language" nillable="true" type="tns:LanguageType" />
    <xs:element minOccurs="0" name="ForwardCompatibilityMap" nillable="true" type="q1:ArrayOfKeyValuePairOfstringstring" xmlns:q1="http://schemas.datacontract.org/2004/07/System.Collections.Generic" />
    <xs:element minOccurs="0" name="LastModifiedByUserId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="LastModifiedTime" nillable="true" type="xs:dateTime" />
    <xs:element minOccurs="0" name="Name" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Number" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ParentCustomerId" type="xs:long" />
    <xs:element minOccurs="0" name="PaymentMethodId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="PaymentMethodType" nillable="true" type="tns:PaymentMethodType" />
    <xs:element minOccurs="0" name="PrimaryUserId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="AccountLifeCycleStatus" nillable="true" type="tns:AccountLifeCycleStatus" />
    <xs:element minOccurs="0" name="TimeStamp" nillable="true" type="xs:base64Binary" />
    <xs:element minOccurs="0" name="TimeZone" nillable="true" type="tns:TimeZoneType" />
    <xs:element minOccurs="0" name="PauseReason" nillable="true" type="xs:unsignedByte" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountfinancialstatus"></a>AccountFinancialStatus|The financial status of the account. For example, the status can indicate whether the account is in good standing or is past due.|[AccountFinancialStatus](accountfinancialstatus.md)|
|<a name="accountlifecyclestatus"></a>AccountLifeCycleStatus|The status of the account. You cannot set the status of the account.|[AccountLifeCycleStatus](accountlifecyclestatus.md)|
|<a name="accounttype"></a>AccountType|The type of the account. For example, whether the account is an advertiser account.|[AccountType](accounttype.md)|
|<a name="billtocustomerid"></a>BillToCustomerId|The identifier of the customer that is billed for the charges that the account generates. This is either the reseller that manages this account on behalf of the owner or the identifier of the customer that owns the account.<br/><br/>The service sets the identifier based on the owner of the payment instrument identified in the *PaymentMethodId* element.|**long**|
|<a name="countrycode"></a>CountryCode|The code that identifies the country/region in which the account operates. The service uses the country/region information for billing purposes.<br/><br/>For a list of country code values, see [Ad Languages](~/guides/ad-languages.md).<br/><br/> If you specify a country code value when signing up a customer, the value is ignored. The signup process instead gets the country code value from the *CountryCode* element of the customer's address. For more information, see the *CustomerAddress* element of the [Customer](../customer-management-service/customer.md).|**string**|
|<a name="currencytype"></a>CurrencyType|The type of currency that is used to settle the account. The service uses the currency information for billing purposes.|[CurrencyType](currencytype.md)|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The system generated identifier of the account.<br/><br/>This is the identifier that you set the *AccountId* element and *CustomerAccountId* SOAP header to in many of the campaign requests.|**long**|
|<a name="language"></a>Language|The language used to render the invoice (if you use an invoice as your payment method).<br/><br/>If you specify a language value when signing up a customer, the value is ignored. The signup process instead gets the language value from the *Lcid* element of the [User](../customer-management-service/user.md). If the *Lcid* element is set to a value such as *FrenchCanada*, the *Language* element is set to *French*.|[LanguageType](languagetype.md)|
|<a name="lastmodifiedbyuserid"></a>LastModifiedByUserId|The identifier of the last user to update the account's information.|**long**|
|<a name="lastmodifiedtime"></a>LastModifiedTime|The date and time that the account was last updated. The value is in Coordinated Universal Time (UTC).<br/><br/> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|
|<a name="name"></a>Name|The name of the account. The name can contain a maximum of 100 characters and must be unique within the customer.|**string**|
|<a name="number"></a>Number|The system generated account number that is used to identify the account in the Bing Ads web application. The account number has the form *xxxxxxxx*, where *xxxxxxxx* is a series of any eight alphanumeric characters.|**string**|
|<a name="parentcustomerid"></a>ParentCustomerId|The identifier of the customer that owns the account.<br/><br/>In the campaign requests that require a customer identifier, this is the identifier that you set the *CustomerId* SOAP header to.|**long**|
|<a name="pausereason"></a>PauseReason|A flag value that indicates who paused the account. The following are the possible values:<br/><br/>1 - The user paused the account.<br/><br/>2 - The billing service paused the account.<br/><br/>4 - The user and billing service paused the account.|**unsignedByte**|
|<a name="paymentmethodid"></a>PaymentMethodId|The identifier of the payment instrument to use to settle the account.<br/><br/>When signing up a customer, set this element to NULL. The service picks up the payment method identifier associated with the reseller's invoice automatically.|**long**|
|<a name="paymentmethodtype"></a>PaymentMethodType|The type of payment instrument to use to settle the account. You do not have to set this value because the type is determined by the payment instrument corresponding to the *PaymentMethodId* element.<br/><br/>When you call the [GetAccount](../customer-management-service/getaccount.md) and [SearchAccounts](../customer-management-service/searchaccounts.md) to get the account data, *PaymentMethodType* is set to NULL, and you cannot determine the payment method that the account uses.<br/><br/> Reserved for internal use.|[PaymentMethodType](paymentmethodtype.md)|
|<a name="primaryuserid"></a>PrimaryUserId|The identifier of the account manager who is primarily responsible for managing this account.<br/><br/>By default, the value is set to the reseller's user identifier.|**long**|
|<a name="timestamp"></a>TimeStamp|The time-stamp value that the system uses internally to reconcile updates when you call the [UpdateAccount](../customer-management-service/updateaccount.md) and [DeleteAccount](../customer-management-service/deleteaccount.md) operations.|**base64Binary**|
|<a name="timezone"></a>TimeZone|The default time-zone value to use for campaigns in this account.<br/><br/>If you do not specify a value when the account is added, the time zone will be set to *PacificTimeUSCanadaTijuana* by default.<br/><br/> This time-zone value is used by the Bing Ads web application to display the account time zone preference, and does not provide a default time-zone value for campaigns that are created by using the Campaign Management API.|[TimeZoneType](timezonetype.md)|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11/Entities  

## Used By
[GetAccount](getaccount.md)  
[SearchAccounts](searchaccounts.md)  
[SignupCustomer](signupcustomer.md)  
[UpdateAccount](updateaccount.md)  
