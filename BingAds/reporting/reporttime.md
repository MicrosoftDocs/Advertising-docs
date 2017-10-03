---
title: ReportTime Data Object
ms.service: bing-ads-reporting
ms.topic: article
author: eric-urban
ms.author: eur
---
# ReportTime Data Object
Defines the date range values of a report request.

## Syntax
```xml
<xs:complexType name="ReportTime" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="CustomDateRangeEnd" nillable="true" type="tns:Date" />
    <xs:element minOccurs="0" name="CustomDateRangeStart" nillable="true" type="tns:Date" />
    <xs:element minOccurs="0" name="PredefinedTime" nillable="true" type="tns:ReportTimePeriod" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customdaterangeend"></a>CustomDateRangeEnd|The end date of the custom date range. The end date cannot be later than today?s date.|[Date](date.md)|
|<a name="customdaterangestart"></a>CustomDateRangeStart|The start date of the custom date range. The start date must be earlier than or the same as the end date.|[Date](date.md)|
|<a name="predefinedtime"></a>PredefinedTime|A predefined date range value. Each report request type specifies the predefined time periods that you can specify for each aggregation type.|[ReportTimePeriod](reporttimeperiod.md)|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https://bingads.microsoft.com/Reporting/v11  

## Used By
[AccountPerformanceReportRequest](accountperformancereportrequest.md)  
[AdDynamicTextPerformanceReportRequest](addynamictextperformancereportrequest.md)  
[AdExtensionByAdReportRequest](adextensionbyadreportrequest.md)  
[AdExtensionByKeywordReportRequest](adextensionbykeywordreportrequest.md)  
[AdExtensionDetailReportRequest](adextensiondetailreportrequest.md)  
[AdGroupPerformanceReportRequest](adgroupperformancereportrequest.md)  
[AdPerformanceReportRequest](adperformancereportrequest.md)  
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
[ProductPartitionPerformanceReportRequest](productpartitionperformancereportrequest.md)  
[ProductPartitionUnitPerformanceReportRequest](productpartitionunitperformancereportrequest.md)  
[ProductSearchQueryPerformanceReportRequest](productsearchqueryperformancereportrequest.md)  
[PublisherUsagePerformanceReportRequest](publisherusageperformancereportrequest.md)  
[SearchCampaignChangeHistoryReportRequest](searchcampaignchangehistoryreportrequest.md)  
[SearchQueryPerformanceReportRequest](searchqueryperformancereportrequest.md)  
[ShareOfVoiceReportRequest](shareofvoicereportrequest.md)  
[UserLocationPerformanceReportRequest](userlocationperformancereportrequest.md)  
