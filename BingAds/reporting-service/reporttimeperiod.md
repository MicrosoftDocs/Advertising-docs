---
title: ReportTimePeriod Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the predefined time and date range values for a report request.
---
# ReportTimePeriod Value Set - Reporting
Defines the predefined time and date range values for a report request.

## Syntax
```xml
<xs:simpleType name="ReportTimePeriod" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Today" />
    <xs:enumeration value="Yesterday" />
    <xs:enumeration value="LastSevenDays" />
    <xs:enumeration value="ThisWeek" />
    <xs:enumeration value="LastWeek" />
    <xs:enumeration value="LastFourWeeks" />
    <xs:enumeration value="ThisMonth" />
    <xs:enumeration value="LastMonth" />
    <xs:enumeration value="LastThreeMonths" />
    <xs:enumeration value="LastSixMonths" />
    <xs:enumeration value="ThisYear" />
    <xs:enumeration value="LastYear" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="lastfourweeks"></a>LastFourWeeks|A cumulative report for the four calendar weeks prior to today.<br /><br /> A calendar week runs from Sunday to Saturday.|
|<a name="lastmonth"></a>LastMonth|A cumulative report for the previous calendar month.|
|<a name="lastsevendays"></a>LastSevenDays|A report for the previous seven days, one row for each day.|
|<a name="lastsixmonths"></a>LastSixMonths|A cumulative report for the previous six calendar months.|
|<a name="lastthreemonths"></a>LastThreeMonths|A cumulative report for the previous three calendar months.|
|<a name="lastweek"></a>LastWeek|A cumulative report for the previous calendar week.<br /><br /> A calendar week runs from Sunday to Saturday.|
|<a name="lastyear"></a>LastYear|A cumulative report for the previous calendar year.|
|<a name="thismonth"></a>ThisMonth|A cumulative report for the current calendar month.|
|<a name="thisweek"></a>ThisWeek|A cumulative report for the current calendar week.|
|<a name="thisyear"></a>ThisYear|A cumulative report for the current calendar year.|
|<a name="today"></a>Today|A cumulative report for the current day.|
|<a name="yesterday"></a>Yesterday|A cumulative report for the previous day.|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https://bingads.microsoft.com/Reporting/v11  

## Used By
[ReportTime](reporttime.md)  
