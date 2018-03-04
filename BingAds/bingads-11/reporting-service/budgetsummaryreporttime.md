---
title: BudgetSummaryReportTime Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the date range values of a budget summary report request.
---
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
    <xs:element minOccurs="0" name="PredefinedTime" nillable="true" type="tns:BudgetSummaryReportTimePeriod" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customdaterangeend"></a>CustomDateRangeEnd|The end date of a date range.<br/><br/>The end date must be greater than or equal to the start date.<br/><br/>|[Date](date.md)|
|<a name="customdaterangestart"></a>CustomDateRangeStart|The start date of a date range.<br/><br/>|[Date](date.md)|
|<a name="predefinedtime"></a>PredefinedTime|A predefined date range.<br/><br/>The *PredefinedTime* element and the other date elements are mutually exclusive.|[BudgetSummaryReportTimePeriod](budgetsummaryreporttimeperiod.md)|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v11  

## Used By
[BudgetSummaryReportRequest](budgetsummaryreportrequest.md)  
