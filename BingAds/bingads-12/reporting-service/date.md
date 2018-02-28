---
title: Date Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a calendar date by month, day, and year.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# Date Data Object - Reporting
Defines a calendar date by month, day, and year.

## Syntax
```xml
<xs:complexType name="Date" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="Day" type="xs:int" />
    <xs:element name="Month" type="xs:int" />
    <xs:element name="Year" type="xs:int" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="day"></a>Day|Specifies the day of the month.|**int**|
|<a name="month"></a>Month|Specifies the month.|**int**|
|<a name="year"></a>Year|Specifies the year.|**int**|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[BudgetSummaryReportTime](budgetsummaryreporttime.md)  
[ReportTime](reporttime.md)  
