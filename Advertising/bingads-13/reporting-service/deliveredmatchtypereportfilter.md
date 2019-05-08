---
title: DeliveredMatchTypeReportFilter Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the delivered match type values that you can use to filter the report data.
---
# DeliveredMatchTypeReportFilter Value Set - Reporting
Defines the delivered match type values that you can use to filter the report data. These values are also used as column values in reports that include match type, such as the keyword performance report.

## Syntax
```xml
<xs:simpleType name="DeliveredMatchTypeReportFilter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="Exact" />
        <xs:enumeration value="Phrase" />
        <xs:enumeration value="Broad" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="broad"></a>Broad|The report will contain ads that were delivered using a broad match comparison.|
|<a name="exact"></a>Exact|The report will contain ads that were delivered by using an exact match comparison.|
|<a name="phrase"></a>Phrase|The report will contain ads that were delivered by using a phrase match comparison.|

## Requirements
Service: [ReportingService.svc v13](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v13/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v13  

## Used By
[KeywordPerformanceReportFilter](keywordperformancereportfilter.md)  
[SearchQueryPerformanceReportFilter](searchqueryperformancereportfilter.md)  
[ShareOfVoiceReportFilter](shareofvoicereportfilter.md)  
