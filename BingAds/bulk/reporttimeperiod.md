---
title: ReportTimePeriod Value Set
ms.service: bing-ads-bulk
ms.topic: article
author: eric-urban
ms.author: eur
---
# ReportTimePeriod Value Set
Defines the date range values for the requested performance data in a bulk download.

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
|<a name="lastfourweeks"></a>LastFourWeeks|Performance data for the four calendar weeks prior to today.<br /><br />**Note:** A calendar week runs from Sunday to Saturday.|
|<a name="lastmonth"></a>LastMonth|Performance data for the previous calendar month.|
|<a name="lastsevendays"></a>LastSevenDays|Performance data for the previous seven days, one row for each day.|
|<a name="lastsixmonths"></a>LastSixMonths|Performance data for the previous six calendar months.|
|<a name="lastthreemonths"></a>LastThreeMonths|Performance data for the previous three calendar months.|
|<a name="lastweek"></a>LastWeek|Performance data for the previous calendar week.<br /><br />**Note:** A calendar week runs from Sunday to Saturday.|
|<a name="lastyear"></a>LastYear|Performance data for the previous calendar year.|
|<a name="thismonth"></a>ThisMonth|Performance data for the current calendar month.|
|<a name="thisweek"></a>ThisWeek|Performance data for the current calendar week.|
|<a name="thisyear"></a>ThisYear|Performance data for the current calendar year.|
|<a name="today"></a>Today|Performance data for the current day.|
|<a name="yesterday"></a>Yesterday|Performance data for the previous day.|

## Requirements
Service: [BulkService.svc v11](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/BulkService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[PerformanceStatsDateRange](performancestatsdaterange.md)  
