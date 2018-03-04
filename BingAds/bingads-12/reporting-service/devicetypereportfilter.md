---
title: DeviceTypeReportFilter Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the device type values that you can use to filter the report data.
---
# DeviceTypeReportFilter Value Set - Reporting
Defines the device type values that you can use to filter the report data. These values are also used as column values in reports that include device type information, such as the ad group performance report.

## Syntax
```xml
<xs:simpleType name="DeviceTypeReportFilter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="Computer" />
        <xs:enumeration value="SmartPhone" />
        <xs:enumeration value="NonSmartPhone" />
        <xs:enumeration value="Tablet" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="computer"></a>Computer|The report will include text ads displayed on computers.|
|<a name="nonsmartphone"></a>NonSmartPhone|The report will include mobile ads displayed on a mobile device.|
|<a name="smartphone"></a>SmartPhone|The report will include text ads displayed on smartphones (any high fidelity device capable of rendering full HTML).|
|<a name="tablet"></a>Tablet|The report will include text ads displayed on a tablet device.|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v11  

## Used By
[AccountPerformanceReportFilter](accountperformancereportfilter.md)  
[AdDynamicTextPerformanceReportFilter](addynamictextperformancereportfilter.md)  
[AdExtensionByAdReportFilter](adextensionbyadreportfilter.md)  
[AdExtensionByKeywordReportFilter](adextensionbykeywordreportfilter.md)  
[AdExtensionDetailReportFilter](adextensiondetailreportfilter.md)  
[AdGroupPerformanceReportFilter](adgroupperformancereportfilter.md)  
[AdPerformanceReportFilter](adperformancereportfilter.md)  
[CampaignPerformanceReportFilter](campaignperformancereportfilter.md)  
[ConversionPerformanceReportFilter](conversionperformancereportfilter.md)  
[DestinationUrlPerformanceReportFilter](destinationurlperformancereportfilter.md)  
[GoalsAndFunnelsReportFilter](goalsandfunnelsreportfilter.md)  
[KeywordPerformanceReportFilter](keywordperformancereportfilter.md)  
[ProductDimensionPerformanceReportFilter](productdimensionperformancereportfilter.md)  
[ProductPartitionPerformanceReportFilter](productpartitionperformancereportfilter.md)  
[ProductPartitionUnitPerformanceReportFilter](productpartitionunitperformancereportfilter.md)  
[ShareOfVoiceReportFilter](shareofvoicereportfilter.md)  
