---
title: NonHourlyReportAggregation Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the aggregation values for reports that cannot specify hourly aggregation.
---
# NonHourlyReportAggregation Value Set - Reporting
Defines the aggregation values for reports that cannot specify hourly aggregation.

## Syntax
```xml
<xs:simpleType name="NonHourlyReportAggregation" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Summary" />
    <xs:enumeration value="Daily" />
    <xs:enumeration value="Weekly" />
    <xs:enumeration value="Monthly" />
    <xs:enumeration value="Yearly" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="daily"></a>Daily|Each row of the report identifies the month, day, and year when the transaction occurred. The report data will be aggregated by each day. Each row of the report identifies the month, day, and year when the transaction occurred. The report will include a column named *GregorianDate* that contains the day formatted as *mm/dd/yyyy*.|
|<a name="monthly"></a>Monthly|Each row of the report identifies the month when the transaction occurred. The report data will be aggregated by each month. The report will include a column named *MonthStartDate* that contains the first day of the month formatted as *mm/dd/yyyy*.|
|<a name="summary"></a>Summary|The report data will be aggregated by the entire specified report time. The report will not include a time period column.|
|<a name="weekly"></a>Weekly|Each row of the report identifies the week when the transaction occurred. The report data will be aggregated by each week. The report will include a column named *WeekStartDate* that contains the date of the Sunday for each week formatted as *mm/dd/yyyy*.|
|<a name="yearly"></a>Yearly|Each row of the report identifies the year when the transaction occurred. The report data will be aggregated by each year. The report will include a column named *Year* that contains the year formatted as *yyyy*.|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https://bingads.microsoft.com/Reporting/v11  

## Used By
[AdDynamicTextPerformanceReportRequest](addynamictextperformancereportrequest.md)  
[AdPerformanceReportRequest](adperformancereportrequest.md)  
[AgeGenderDemographicReportRequest](agegenderdemographicreportrequest.md)  
[ConversionPerformanceReportRequest](conversionperformancereportrequest.md)  
[DestinationUrlPerformanceReportRequest](destinationurlperformancereportrequest.md)  
[DSAAutoTargetPerformanceReportRequest](dsaautotargetperformancereportrequest.md)  
[DSACategoryPerformanceReportRequest](dsacategoryperformancereportrequest.md)  
[GeographicPerformanceReportRequest](geographicperformancereportrequest.md)  
[GoalsAndFunnelsReportRequest](goalsandfunnelsreportrequest.md)  
[PublisherUsagePerformanceReportRequest](publisherusageperformancereportrequest.md)  
[ShareOfVoiceReportRequest](shareofvoicereportrequest.md)  
[UserLocationPerformanceReportRequest](userlocationperformancereportrequest.md)  
