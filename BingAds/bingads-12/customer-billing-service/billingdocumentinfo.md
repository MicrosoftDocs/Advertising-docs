---
title: BillingDocumentInfo Data Object - Customer Billing
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a billing document identification object that contains information about a billing document, such as the billing document identifier, billing document amount, and account identifier.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# BillingDocumentInfo Data Object - Customer Billing
Defines a billing document identification object that contains information about a billing document, such as the billing document identifier, billing document amount, and account identifier.

## Syntax
```xml
<xs:complexType name="BillingDocumentInfo" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AccountId" type="xs:long" />
    <xs:element minOccurs="0" name="AccountName" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="AccountNumber" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Amount" type="xs:double" />
    <xs:element minOccurs="0" name="CurrencyCode" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="DocumentDate" nillable="true" type="xs:dateTime" />
    <xs:element minOccurs="0" name="DocumentId" nillable="true" type="xs:long" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account for which the billing document was generated.|**long**|
|<a name="accountname"></a>AccountName|The account name.|**string**|
|<a name="accountnumber"></a>AccountNumber|The account number.|**string**|
|<a name="amount"></a>Amount|The amount of the billing document.|**double**|
|<a name="currencycode"></a>CurrencyCode|The currency of the billing document. For possible values, see [Currencies](../guides/currencies.md).|**string**|
|<a name="documentdate"></a>DocumentDate|The date of the billing document.|**dateTime**|
|<a name="documentid"></a>DocumentId|An identifier of the billing document.|**long**|

## Requirements
Service: [CustomerBillingService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v11/CustomerBillingService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11/Entities  

## Used By
[GetBillingDocumentsInfo](getbillingdocumentsinfo.md)  
