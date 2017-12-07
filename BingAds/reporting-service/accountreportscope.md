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

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountids"></a>AccountIds|An array of a maximum of 1,000 account identifiers that identifies the account data to include in the report.<br /><br />To include every account to which the user has access, including accounts that the user manages, set this element to NULL.|**long** array|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: ```https://bingads.microsoft.com/Reporting/v11```  

## Used By
[AccountPerformanceReportRequest](accountperformancereportrequest.md)  
