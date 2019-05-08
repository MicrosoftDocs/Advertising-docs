---
title: ReportTimePeriod Value Set - Bulk
ms.service: bing-ads-bulk-service
ms.topic: article
author: eric-urban
ms.author: eur
description: This value set is not supported in Bing Ads API Version 12, and will be removed in a future version.
---
# ReportTimePeriod Value Set - Bulk
This value set is not supported in Bing Ads API Version 12, and will be removed in a future version. If you want data aggregated by day, week, or month, you can use the Reporting API. For more details see [Reports](../guides/reports.md).

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
|<a name="lastfourweeks"></a>LastFourWeeks|Performance data for the four calendar weeks prior to today.<br/><br/>A calendar week runs from Sunday to Saturday.|
|<a name="lastmonth"></a>LastMonth|Performance data for the previous calendar month.|
|<a name="lastsevendays"></a>LastSevenDays|Performance data for the previous seven days, one row for each day.|
|<a name="lastsixmonths"></a>LastSixMonths|Performance data for the previous six calendar months.|
|<a name="lastthreemonths"></a>LastThreeMonths|Performance data for the previous three calendar months.|
|<a name="lastweek"></a>LastWeek|Performance data for the previous calendar week.<br/><br/>A calendar week runs from Sunday to Saturday.|
|<a name="lastyear"></a>LastYear|Performance data for the previous calendar year.|
|<a name="thismonth"></a>ThisMonth|Performance data for the current calendar month.|
|<a name="thisweek"></a>ThisWeek|Performance data for the current calendar week.|
|<a name="thisyear"></a>ThisYear|Performance data for the current calendar year.|
|<a name="today"></a>Today|Performance data for the current day.|
|<a name="yesterday"></a>Yesterday|Performance data for the previous day.|

## Requirements
Service: [BulkService.svc v12](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/BulkService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[PerformanceStatsDateRange](performancestatsdaterange.md)  
