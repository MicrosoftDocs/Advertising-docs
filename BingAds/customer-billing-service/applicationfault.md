---
title: ApplicationFault Data Object - Customer Billing
ms.service: bing-ads-customer-billing-service
ms.topic: "article"
ms.date: 11/1/2017
author: eric-urban
ms.author: eur
description: Defines the base object from which all fault detail objects derive.
---
# ApplicationFault Data Object - Customer Billing
Defines the base object from which all fault detail objects derive.

## Syntax
```xml
<xs:complexType name="ApplicationFault" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="TrackingId" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="trackingid"></a>TrackingId|The identifier of the log entry that contains the details of the API call.|**string**|

## Requirements
Service: [CustomerBillingService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v11/CustomerBillingService.svc)  
Namespace: https://adapi.microsoft.com  

