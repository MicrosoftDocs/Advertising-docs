---
title: DateRange Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a date range object.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# DateRange Data Object - Customer Management
Defines a date range object.

## Syntax
```xml
<xs:complexType name="DateRange" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="MinDate" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="MaxDate" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="maxdate"></a>MaxDate|The maximum date.<br /><br /> The date format should be specified as *"yyyyMMdd"*. For example December 31, 2050 should be specified as *"20501231"*.|**string**|
|<a name="mindate"></a>MinDate|The minimum date.<br /><br /> The date format should be specified as *"yyyyMMdd"*. For example April 3, 2017 should be specified as *"20170403"*.|**string**|

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12/Entities  

## Used By
[SearchCustomers](searchcustomers.md)  
