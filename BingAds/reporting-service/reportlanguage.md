---
title: ReportLanguage Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the language values that you may specify for columns of a downloaded report.
---
# ReportLanguage Value Set - Reporting
Defines the language values that you may specify for columns of a downloaded report.

## Syntax
```xml
<xs:simpleType name="ReportLanguage" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="English" />
    <xs:enumeration value="French" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="english"></a>English|The report columns will be in English.|
|<a name="french"></a>French|The report columns will be in French.|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https://bingads.microsoft.com/Reporting/v11  

## Used By
[ReportRequest](reportrequest.md)  
