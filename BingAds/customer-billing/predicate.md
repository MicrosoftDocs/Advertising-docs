---
title: Predicate Data Object
ms.service: bing-ads-customer-billing
ms.topic: article
author: eric-urban
ms.author: eur
---
# Predicate Data Object
Defines a predicate for the list of insertion orders returned using the [SearchInsertionOrders](../customer-billing/searchinsertionorders.md) operation.

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
|<a name="field"></a>Field|The name of the element for  the object you are searching.<br /><br />For possible values, see the [SearchInsertionOrders](../customer-billing/searchinsertionorders.md) operation.|**string**|
|<a name="operator"></a>Operator|Defines the relationship between the field and the value.|[PredicateOperator](predicateoperator.md)|
|<a name="value"></a>Value|The string to search in the specified field.<br /><br />**Note**: The length of this string must be four or greater, unless the field is set to MarketCountry or MarketLanguage.|**string**|

## Requirements
Service: [CustomerBillingService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v11/CustomerBillingService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11/Entities  

## Used By
[SearchInsertionOrders](searchinsertionorders.md)  
