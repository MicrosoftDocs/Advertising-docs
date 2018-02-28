---
title: OperationError Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an error object that contains the details that explain why the service operation failed.
---
# OperationError Data Object - Reporting

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Defines an error object that contains the details that explain why the service operation failed.

## Syntax
```xml
<xs:complexType name="OperationError" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Code" type="xs:int" />
    <xs:element minOccurs="0" name="Details" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ErrorCode" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Message" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="code"></a>Code|A numeric error code that identifies the error|**int**|
|<a name="details"></a>Details|A message that provides additional details about the error. This string can be empty.|**string**|
|<a name="errorcode"></a>ErrorCode|A symbolic string constant that identifies the error. For example, *UserIsNotAuthorized*.|**string**|
|<a name="message"></a>Message|A message that describes the error.|**string**|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[ApiFaultDetail](apifaultdetail.md)  
