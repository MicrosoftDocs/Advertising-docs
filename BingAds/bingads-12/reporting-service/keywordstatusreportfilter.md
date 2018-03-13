---
title: KeywordStatusReportFilter Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the keyword status values that you can use to filter the report data.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# KeywordStatusReportFilter Value Set - Reporting
Defines the keyword status values that you can use to filter the report data. These values are also used as column values in reports that include keyword status, such as the keyword performance report.

## Syntax
```xml
<xs:simpleType name="KeywordStatusReportFilter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="Active" />
        <xs:enumeration value="Paused" />
        <xs:enumeration value="Deleted" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="active"></a>Active|The report will contain keywords that are active.|
|<a name="deleted"></a>Deleted|The report will contain keywords that have been deleted.|
|<a name="paused"></a>Paused|The report will contain keywords that are paused.|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[AdDynamicTextPerformanceReportFilter](addynamictextperformancereportfilter.md)  
[AdExtensionByKeywordReportFilter](adextensionbykeywordreportfilter.md)  
[ConversionPerformanceReportFilter](conversionperformancereportfilter.md)  
[GoalsAndFunnelsReportFilter](goalsandfunnelsreportfilter.md)  
[KeywordPerformanceReportFilter](keywordperformancereportfilter.md)  
[NegativeKeywordConflictReportFilter](negativekeywordconflictreportfilter.md)  
[SearchQueryPerformanceReportFilter](searchqueryperformancereportfilter.md)  
[ShareOfVoiceReportFilter](shareofvoicereportfilter.md)  
