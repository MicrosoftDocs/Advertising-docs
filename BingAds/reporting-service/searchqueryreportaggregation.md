---
title: SearchQueryReportAggregation Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the aggregation values that you can use in a search query performance report.
---
# SearchQueryReportAggregation Value Set - Reporting
Defines the aggregation values that you can use in a search query performance report.

## Syntax
```xml
<xs:simpleType name="SearchQueryReportAggregation" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Summary" />
    <xs:enumeration value="Hourly" />
    <xs:enumeration value="Daily" />
    <xs:enumeration value="Weekly" />
    <xs:enumeration value="Monthly" />
    <xs:enumeration value="Yearly" />
    <xs:enumeration value="HourOfDay" />
    <xs:enumeration value="DayOfWeek" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="daily"></a>Daily|The report data will be aggregated for each day.|
|<a name="dayofweek"></a>DayOfWeek|The report data will be aggregated by each of the seven days in a week.|
|<a name="hourly"></a>Hourly|The report data will be aggregated for each hour.|
|<a name="hourofday"></a>HourOfDay|The report data will be aggregated by each of the 24 hours in a day.|
|<a name="monthly"></a>Monthly|The report data will be aggregated for each month.|
|<a name="summary"></a>Summary|The report data will be aggregated for the entire specified report time.|
|<a name="weekly"></a>Weekly|The report data will be aggregated for each week.|
|<a name="yearly"></a>Yearly|The report data will be aggregated for each year.|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https://bingads.microsoft.com/Reporting/v11  

## Used By
[DSASearchQueryPerformanceReportRequest](dsasearchqueryperformancereportrequest.md)  
[SearchQueryPerformanceReportRequest](searchqueryperformancereportrequest.md)  
