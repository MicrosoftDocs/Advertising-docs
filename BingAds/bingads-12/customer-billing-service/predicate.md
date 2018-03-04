---
title: Predicate Data Object - Customer Billing
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a predicate for the list of insertion orders returned using the SearchInsertionOrders operation.
---
# Predicate Data Object - Customer Billing
Defines a predicate for the list of insertion orders returned using the [SearchInsertionOrders](searchinsertionorders.md) operation.

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
|<a name="field"></a>Field|The name of the element for  the object you are searching.<br /><br />For possible values, see the [SearchInsertionOrders](searchinsertionorders.md) operation.|**string**|
|<a name="operator"></a>Operator|Defines the relationship between the field and the value.|[PredicateOperator](predicateoperator.md)|
|<a name="value"></a>Value|The string to search in the specified field.<br /><br /> The length of this string must be four or greater, unless the field is set to MarketCountry or MarketLanguage.|**string**|

## <a name="remarks"></a>Remarks
The supported Field element and Operator elements of a Predicate object for each service operation are provided in detail below. 

### <a name="searchinsertionorders"></a>SearchInsertionOrders Predicates
For the [SearchInsertionOrders](searchinsertionorders.md) service operation, the following are supported Field element and Operator elements of a Predicate object.

|Field|Operator|Description|
|---------|------------|---------------|
|AccountId|Equals|Use this field to search by the insertion order's account identifier.<br /><br />This predicate field is required.|
|EndDate|GreaterThanEquals<br /><br />LessThanEquals|Use this field to search by insertion order end date. The date is stored in Coordinated Universal Time (UTC). Only the month, day, and year of the specified string are used for search. If you specify the hour, minutes, and seconds of a date they will be ignored.<br /><br />For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|
|InsertionOrderIds|Equals<br /><br />In|Use this field to search the InsertionOrderId element of the [InsertionOrder](insertionorder.md).|
|StartDate|GreaterThanEquals<br /><br />LessThanEquals|Use this field to search by insertion order start date.<br /><br />The date is stored in Coordinated Universal Time (UTC). Only the month, day, and year of the specified string are used for search. If you specify the hour, minutes, and seconds of a date they will be ignored.<br /><br />For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|

## Requirements
Service: [CustomerBillingService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v11/CustomerBillingService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11/Entities  

## Used By
[SearchInsertionOrders](searchinsertionorders.md)  
