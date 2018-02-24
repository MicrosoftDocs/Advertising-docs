---
title: Customer Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a customer.
---
# Customer Data Object - Customer Management
Defines a customer.

## Syntax
```xml
<xs:complexType name="Customer" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="CustomerAddress" nillable="true" type="tns:Address" />
    <xs:element minOccurs="0" name="CustomerFinancialStatus" nillable="true" type="tns:CustomerFinancialStatus" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Industry" nillable="true" type="tns:Industry" />
    <xs:element minOccurs="0" name="LastModifiedByUserId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="LastModifiedTime" nillable="true" type="xs:dateTime" />
    <xs:element minOccurs="0" name="MarketCountry" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ForwardCompatibilityMap" nillable="true" type="q3:ArrayOfKeyValuePairOfstringstring" xmlns:q3="http://schemas.datacontract.org/2004/07/System.Collections.Generic" />
    <xs:element minOccurs="0" name="MarketLanguage" nillable="true" type="tns:LanguageType" />
    <xs:element minOccurs="0" name="Name" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ServiceLevel" nillable="true" type="tns:ServiceLevel" />
    <xs:element minOccurs="0" name="CustomerLifeCycleStatus" nillable="true" type="tns:CustomerLifeCycleStatus" />
    <xs:element minOccurs="0" name="TimeStamp" nillable="true" type="xs:base64Binary" />
    <xs:element minOccurs="0" name="Number" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customeraddress"></a>CustomerAddress|The customer's business address.<br/><br/>**Add:** Required<br/>**Update:** Required|[Address](address.md)|
|<a name="customerfinancialstatus"></a>CustomerFinancialStatus|The financial status of the customer. For example, the status indicates whether the customer is in good standing or one or more of the accounts are past due.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[CustomerFinancialStatus](customerfinancialstatus.md)|
|<a name="customerlifecyclestatus"></a>CustomerLifeCycleStatus|The status of the customer. When you create the customer, the status is set to *Active*. You cannot change the status.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[CustomerLifeCycleStatus](customerlifecyclestatus.md)|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br /> Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for the *Customer* object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The system generated customer identifier.<br /><br />Use this identifier with operation requests that require a *CustomerId* SOAP header element.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**long**|
|<a name="industry"></a>Industry|The primary business segment of the customer, for example, automotive, food, or entertainment.<br/><br/>**Add:** Required<br/>**Update:** Required|[Industry](industry.md)|
|<a name="lastmodifiedbyuserid"></a>LastModifiedByUserId|The identifier of the last user to update the customer's information.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="lastmodifiedtime"></a>LastModifiedTime|The date and time that the customer information was last updated. The value is in Coordinated Universal Time (UTC).<br /><br />The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the **dateTime** entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**dateTime**|
|<a name="marketcountry"></a>MarketCountry|The primary country where the customer operates. For a list of customer market country code values, see [Product Language](~/guides/ad-languages.md#productlanguage).<br/><br/>**Add:** Required<br/>**Update:** Read-only|**string**|
|<a name="marketlanguage"></a>MarketLanguage|The primary language that the customer uses. Your customer market language determines the language of the Bing Ads interface. For a list of customer market language code values, see [Product Language](~/guides/ad-languages.md#productlanguage).<br/><br/>**Add:** Required<br/>**Update:** Read-only|[LanguageType](languagetype.md)|
|<a name="name"></a>Name|The name of the customer. The name can contain a maximum of 90 characters.<br/><br/>**Add:** Required<br/>**Update:** Required|**string**|
|<a name="number"></a>Number|A system-generated customer number that is used in the Bing Ads web application. The customer number is of the form, C*nnnnnnn*, where *nnnnnnn* is a series of digits.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|
|<a name="servicelevel"></a>ServiceLevel|For internal use only. If this element is set when calling [SignupCustomer](../customer-management-service/signupcustomer.md) an error will be returned. If this element is set when calling [UpdateCustomer](../customer-management-service/updatecustomer.md) the element will be ignored.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[ServiceLevel](servicelevel.md)|
|<a name="timestamp"></a>TimeStamp|A time-stamp value that the system uses internally to reconcile updates when you call the [UpdateCustomer](../customer-management-service/updatecustomer.md) and [DeleteCustomer](../customer-management-service/deletecustomer.md) operations.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**base64Binary**|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11/Entities  

## Used By
[GetCustomer](getcustomer.md)  
[SearchCustomers](searchcustomers.md)  
[SignupCustomer](signupcustomer.md)  
[UpdateCustomer](updatecustomer.md)  
