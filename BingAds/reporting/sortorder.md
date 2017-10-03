---
title: SortOrder Value Set
ms.service: bing-ads-reporting
ms.topic: article
author: eric-urban
ms.author: eur
---
# SortOrder Value Set
Defines the ascending or descending sort order of values within the specified report column.

## Syntax
```xml
<xs:simpleType name="SortOrder" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Ascending" />
    <xs:enumeration value="Descending" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="ascending"></a>Ascending|The results will be sorted ascending.|
|<a name="descending"></a>Descending|The results will be sorted descending.|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https://bingads.microsoft.com/Reporting/v11  

## Used By
[KeywordPerformanceReportSort](keywordperformancereportsort.md)  
