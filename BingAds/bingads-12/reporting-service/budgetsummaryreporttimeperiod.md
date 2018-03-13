---
title: BudgetSummaryReportTimePeriod Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the predefined time and date range values for a budget summary report request.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# BudgetSummaryReportTimePeriod Value Set - Reporting
Defines the predefined time and date range values for a budget summary report request.

## Syntax
```xml
<xs:simpleType name="BudgetSummaryReportTimePeriod" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Today" />
    <xs:enumeration value="Yesterday" />
    <xs:enumeration value="LastSevenDays" />
    <xs:enumeration value="ThisMonth" />
    <xs:enumeration value="LastMonth" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="lastmonth"></a>LastMonth|A cumulative report for the previous calendar month.|
|<a name="lastsevendays"></a>LastSevenDays|A cumulative report for the previous seven days, having one row for each day.|
|<a name="thismonth"></a>ThisMonth|A cumulative report for the current calendar month.|
|<a name="today"></a>Today|A cumulative report for the current day.|
|<a name="yesterday"></a>Yesterday|A cumulative report for the previous day.|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[BudgetSummaryReportTime](budgetsummaryreporttime.md)  
