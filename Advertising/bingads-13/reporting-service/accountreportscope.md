---
title: AccountReportScope Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the set of accounts to include in the report.
---
# AccountReportScope Data Object - Reporting
Defines the set of accounts to include in the report.

## Syntax
```xml
<xs:complexType name="AccountReportScope" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AccountIds" nillable="true" type="q1:ArrayOflong" xmlns:q1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [AccountReportScope](accountreportscope.md) object has the following elements: [AccountIds](#accountids).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountids"></a>AccountIds|A list of up to 1,000 account identifiers to include in the report.<br/><br/>This element is required.|**long** array|

## Requirements
Service: [ReportingService.svc v13](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v13/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v13  

## Used By
[AccountPerformanceReportRequest](accountperformancereportrequest.md)  
