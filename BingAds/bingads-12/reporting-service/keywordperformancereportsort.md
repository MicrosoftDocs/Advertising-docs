---
title: KeywordPerformanceReportSort Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a keyword performance report column and corresponding sort order.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

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
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v12/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[KeywordPerformanceReportRequest](keywordperformancereportrequest.md)  
