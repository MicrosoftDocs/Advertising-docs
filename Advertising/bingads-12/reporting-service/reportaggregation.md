---
title: ReportAggregation Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the aggregation values that you can use for a report.
---
# ReportAggregation Value Set - Reporting
Defines the aggregation values that you can use for a report.

## Syntax
```xml
<xs:simpleType name="ReportAggregation" xmlns:xs="http://www.w3.org/2001/XMLSchema">
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
|<a name="daily"></a>Daily|Each row of the report identifies the month, day, and year when the transaction occurred. The report data will be aggregated by each day. The time period will be formatted as *yyyy-mm-dd*.|
|<a name="dayofweek"></a>DayOfWeek|Each row of the report identifies the day of the week when the transaction occurred. The report data will be aggregated by each of the seven days in a week. The possible data values are *1* - *7* where *1* represents Sunday and *7* represents Saturday. If the report time spans multiple weeks, then the performance data across all weeks for a given day of the week will be aggregated in one row. For example if *Campaign A* has 5 impressions every Monday (day 2) throughout each of the 3 weeks included in the report time range, then the report will include one row with a *2* in the TimePeriod column and the impressions in that row totaling 15.|
|<a name="hourly"></a>Hourly|Each row of the report identifies the hour when the transaction occurred. The report data will be aggregated by each hour of the day.<br/><br/>The time period will be formatted with the date and hour (int value) delimited by a single pipe i.e., "mm/dd/yyyy 12:00:00 AM&#124;hour" where 12:00:00 AM can be ignored. For example, if the click occurred March 15, 2018 between 07:00 and 08:00, then the field in the downloaded report would be "3/15/2018 12:00:00 AM&#124;7". The possible values for the hour component are *0* - *23*. If the report time spans multiple days, then the performance data for a given hour will be provided separately across multiple rows i.e. the report will include one row for each unique day and hour. For example if *Campaign A* has 5 impressions during *Hour* 7 on each of the 3 days included in the report time range, then the report will include three rows each with 5 impressions for *Hour* 7.|
|<a name="hourofday"></a>HourOfDay|Each row of the report identifies the hour of the day when the transaction occurred. The report data will be aggregated by each of the 24 hours across all days. The possible values are *0* - *23*. If the report time spans multiple days, then the performance data across all days for a given hour will be aggregated in one row. For example if *Campaign A* has 5 impressions during hour *7* on each of the 3 days included in the report time range, then the report will include one row with impressions for *HourOfDay* totaling 15.|
|<a name="monthly"></a>Monthly|Each row of the report identifies the month when the transaction occurred. The report data will be aggregated by each month. The time period that contains the first day of the month will be formatted as *yyyy-mm-dd*.|
|<a name="summary"></a>Summary|The report data will be aggregated by the entire specified report time. The report will not include a time period column.|
|<a name="weekly"></a>Weekly|Each row of the report identifies the week when the transaction occurred. The report data will be aggregated by each week. The time period that contains the date of the Sunday for each week will be formatted as *yyyy-mm-dd*.|
|<a name="yearly"></a>Yearly|Each row of the report identifies the year when the transaction occurred. The report data will be aggregated by each year. The time period that contains the year will be formatted as *yyyy*.|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v12/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[AccountPerformanceReportRequest](accountperformancereportrequest.md)  
[AdDynamicTextPerformanceReportRequest](addynamictextperformancereportrequest.md)  
[AdExtensionByAdReportRequest](adextensionbyadreportrequest.md)  
[AdExtensionByKeywordReportRequest](adextensionbykeywordreportrequest.md)  
[AdExtensionDetailReportRequest](adextensiondetailreportrequest.md)  
[AdGroupPerformanceReportRequest](adgroupperformancereportrequest.md)  
[AdPerformanceReportRequest](adperformancereportrequest.md)  
[AgeGenderAudienceReportRequest](agegenderaudiencereportrequest.md)  
[AgeGenderDemographicReportRequest](agegenderdemographicreportrequest.md)  
[AudiencePerformanceReportRequest](audienceperformancereportrequest.md)  
[CallDetailReportRequest](calldetailreportrequest.md)  
[CampaignPerformanceReportRequest](campaignperformancereportrequest.md)  
[ConversionPerformanceReportRequest](conversionperformancereportrequest.md)  
[DestinationUrlPerformanceReportRequest](destinationurlperformancereportrequest.md)  
[DSAAutoTargetPerformanceReportRequest](dsaautotargetperformancereportrequest.md)  
[DSACategoryPerformanceReportRequest](dsacategoryperformancereportrequest.md)  
[DSASearchQueryPerformanceReportRequest](dsasearchqueryperformancereportrequest.md)  
[GeographicPerformanceReportRequest](geographicperformancereportrequest.md)  
[GoalsAndFunnelsReportRequest](goalsandfunnelsreportrequest.md)  
[KeywordPerformanceReportRequest](keywordperformancereportrequest.md)  
[ProductDimensionPerformanceReportRequest](productdimensionperformancereportrequest.md)  
[ProductMatchCountReportRequest](productmatchcountreportrequest.md)  
[ProductPartitionPerformanceReportRequest](productpartitionperformancereportrequest.md)  
[ProductPartitionUnitPerformanceReportRequest](productpartitionunitperformancereportrequest.md)  
[ProductSearchQueryPerformanceReportRequest](productsearchqueryperformancereportrequest.md)  
[ProfessionalDemographicsAudienceReportRequest](professionaldemographicsaudiencereportrequest.md)  
[PublisherUsagePerformanceReportRequest](publisherusageperformancereportrequest.md)  
[SearchQueryPerformanceReportRequest](searchqueryperformancereportrequest.md)  
[ShareOfVoiceReportRequest](shareofvoicereportrequest.md)  
[UserLocationPerformanceReportRequest](userlocationperformancereportrequest.md)  
