---
title: BidStrategyTypeReportFilter Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible values that you can use to use to filter the report data by bid strategy type.
---
# BidStrategyTypeReportFilter Value Set - Reporting

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Defines the possible values that you can use to use to filter the report data by bid strategy type.

## Syntax
```xml
<xs:simpleType name="BidStrategyTypeReportFilter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="ManualCpc" />
        <xs:enumeration value="EnhancedCpc">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">16</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="enhancedcpc"></a>EnhancedCpc|The report will contain data related to keywords, ad groups, or campaigns that use the enhanced CPC bid strategy.|
|<a name="manualcpc"></a>ManualCpc|The report will contain data related to keywords, ad groups, or campaigns that use the manual CPC bid strategy.|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[DSAAutoTargetPerformanceReportFilter](dsaautotargetperformancereportfilter.md)  
[KeywordPerformanceReportFilter](keywordperformancereportfilter.md)  
[ShareOfVoiceReportFilter](shareofvoicereportfilter.md)  
