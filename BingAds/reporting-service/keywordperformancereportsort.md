---
title: KeywordPerformanceReportSort Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a keyword performance report column and corresponding sort order.
---
# KeywordPerformanceReportSort Data Object - Reporting
Defines a keyword performance report column and corresponding sort order.

## Syntax
```xml
<xs:complexType name="KeywordPerformanceReportSort" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="SortColumn" type="tns:KeywordPerformanceReportColumn" />
    <xs:element name="SortOrder" type="tns:SortOrder" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="sortcolumn"></a>SortColumn|The keyword performance report column by which to sort.|[KeywordPerformanceReportColumn](keywordperformancereportcolumn.md)|
|<a name="sortorder"></a>SortOrder|Defines the ascending or descending sort order of values within the specified report column.|[SortOrder](sortorder.md)|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: ```https://bingads.microsoft.com/Reporting/v11```  

## Used By
[KeywordPerformanceReportRequest](keywordperformancereportrequest.md)  
