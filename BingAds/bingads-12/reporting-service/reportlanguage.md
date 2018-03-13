---
title: ReportLanguage Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the language values that you may specify for columns of a downloaded report.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

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
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[ReportRequest](reportrequest.md)  
