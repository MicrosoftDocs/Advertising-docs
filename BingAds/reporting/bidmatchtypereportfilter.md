---
title: BidMatchTypeReportFilter Value Set
ms.service: bing-ads-reporting
ms.topic: article
author: eric-urban
ms.author: eur
---
# BidMatchTypeReportFilter Value Set
Defines the bid match type values that you can use to filter the report data. These values are also used as column values in reports that include bid match type, such as the keyword performance report.

## Syntax
```xml
<xs:simpleType name="BidMatchTypeReportFilter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="Exact" />
        <xs:enumeration value="Phrase" />
        <xs:enumeration value="Broad" />
        <xs:enumeration value="Content" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="broad"></a>Broad|The report will contain keywords that set a bid value for the broad match type.|
|<a name="content"></a>Content|The report will contain keywords that set a bid value for the content match type.|
|<a name="exact"></a>Exact|The report will contain keywords that set a bid value for the exact match type.|
|<a name="phrase"></a>Phrase|The report will contain keywords that set a bid value for the phrase match type.|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https://bingads.microsoft.com/Reporting/v11  

## Used By
[KeywordPerformanceReportFilter](keywordperformancereportfilter.md)  
[ShareOfVoiceReportFilter](shareofvoicereportfilter.md)  
