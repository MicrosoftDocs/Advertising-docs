---
title: BudgetSummaryReportTime Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the date range values of a budget summary report request.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# BudgetSummaryReportTime Data Object - Reporting
Defines the date range values of a budget summary report request.

> [!NOTE]
> The *CustomDateRangeStart* and *CustomDateRangeEnd* elements versus the *PredefinedTime* element are mutually exclusive. For information about how the time zone of the campaign affects the date range that you specify, see [Time Zones in Reporting](../guides/reports.md#reptimezones).

## Syntax
```xml
<xs:complexType name="BudgetSummaryReportTime" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="CustomDateRangeEnd" nillable="true" type="tns:Date" />
    <xs:element minOccurs="0" name="CustomDateRangeStart" nillable="true" type="tns:Date" />
    <xs:element minOccurs="0" name="PredefinedTime" nillable="true" type="tns:ReportTimePeriod" />
    <xs:element minOccurs="0" name="ReportTimeZone" nillable="true" type="tns:ReportTimeZone" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customdaterangeend"></a>CustomDateRangeEnd|The end date of a date range.<br/><br/>The end date must be greater than or equal to the start date.<br/><br/>|[Date](date.md)|
|<a name="customdaterangestart"></a>CustomDateRangeStart|The start date of a date range.<br/><br/>|[Date](date.md)|
|<a name="predefinedtime"></a>PredefinedTime|A predefined date range.<br/><br/>The *PredefinedTime* element and the other date elements are mutually exclusive.|[ReportTimePeriod](reporttimeperiod.md)|
|<a name="reporttimezone"></a>ReportTimeZone|Determines the time zone that you want the Reporting service to use for the requested time period.<br/><br/>The time zone helps you accurately scope data for the requested time period.<br/><br/>If you do not choose a time zone, the Reporting service uses PacificTimeUSCanadaTijuana by default.|[ReportTimeZone](reporttimezone.md)|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v12/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[BudgetSummaryReportRequest](budgetsummaryreportrequest.md)  
