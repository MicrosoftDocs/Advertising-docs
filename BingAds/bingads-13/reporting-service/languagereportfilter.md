---
title: LanguageReportFilter Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the language values that you can use to filter the report data.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# LanguageReportFilter Value Set - Reporting
Defines the language values that you can use to filter the report data. These values are also used as column values in reports that include language, such as the keyword performance report.

## Syntax
```xml
<xs:simpleType name="LanguageReportFilter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="Danish" />
        <xs:enumeration value="Dutch" />
        <xs:enumeration value="English" />
        <xs:enumeration value="Finnish" />
        <xs:enumeration value="French" />
        <xs:enumeration value="German" />
        <xs:enumeration value="Italian" />
        <xs:enumeration value="Japanese" />
        <xs:enumeration value="Norwegian" />
        <xs:enumeration value="Portuguese" />
        <xs:enumeration value="Swedish" />
        <xs:enumeration value="Spanish" />
        <xs:enumeration value="Arabic" />
        <xs:enumeration value="Hebrew" />
        <xs:enumeration value="Korean" />
        <xs:enumeration value="Russian" />
        <xs:enumeration value="TraditionalChinese" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="arabic"></a>Arabic|The report will contain data for ads that were viewed in Arabic.|
|<a name="danish"></a>Danish|The report will contain data for ads that were viewed in Danish.|
|<a name="dutch"></a>Dutch|The report will contain data for ads that were viewed in Dutch.|
|<a name="english"></a>English|The report will contain data for ads that were viewed in English.|
|<a name="finnish"></a>Finnish|The report will contain data for ads that were viewed in Finnish.|
|<a name="french"></a>French|The report will contain data for ads that were viewed in French.|
|<a name="german"></a>German|The report will contain data for ads that were viewed in German.|
|<a name="hebrew"></a>Hebrew|The report will contain data for ads that were viewed in Hebrew.|
|<a name="italian"></a>Italian|The report will contain data for ads that were viewed in Italian.|
|<a name="japanese"></a>Japanese|The report will contain data for ads that were viewed in Japanese.|
|<a name="korean"></a>Korean|The report will contain data for ads that were viewed in Korean.|
|<a name="norwegian"></a>Norwegian|The report will contain data for ads that were viewed in Norwegian.|
|<a name="portuguese"></a>Portuguese|The report will contain data for ads that were viewed in Portuguese.|
|<a name="russian"></a>Russian|The report will contain data for ads that were viewed in Russian.|
|<a name="spanish"></a>Spanish|The report will contain data for ads that were viewed in Spanish.|
|<a name="swedish"></a>Swedish|The report will contain data for ads that were viewed in Swedish.|
|<a name="traditionalchinese"></a>TraditionalChinese|The report will contain data for ads that were viewed in Traditional Chinese.|

## Requirements
Service: [ReportingService.svc v13](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v13/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v13  

## Used By
[AdDynamicTextPerformanceReportFilter](addynamictextperformancereportfilter.md)  
[AdGroupPerformanceReportFilter](adgroupperformancereportfilter.md)  
[AdPerformanceReportFilter](adperformancereportfilter.md)  
[AgeGenderAudienceReportFilter](agegenderaudiencereportfilter.md)  
[DestinationUrlPerformanceReportFilter](destinationurlperformancereportfilter.md)  
[DSAAutoTargetPerformanceReportFilter](dsaautotargetperformancereportfilter.md)  
[DSACategoryPerformanceReportFilter](dsacategoryperformancereportfilter.md)  
[DSASearchQueryPerformanceReportFilter](dsasearchqueryperformancereportfilter.md)  
[GeographicPerformanceReportFilter](geographicperformancereportfilter.md)  
[KeywordPerformanceReportFilter](keywordperformancereportfilter.md)  
[ProductDimensionPerformanceReportFilter](productdimensionperformancereportfilter.md)  
[ProductPartitionPerformanceReportFilter](productpartitionperformancereportfilter.md)  
[ProductPartitionUnitPerformanceReportFilter](productpartitionunitperformancereportfilter.md)  
[ProductSearchQueryPerformanceReportFilter](productsearchqueryperformancereportfilter.md)  
[ProfessionalDemographicsAudienceReportFilter](professionaldemographicsaudiencereportfilter.md)  
[PublisherUsagePerformanceReportFilter](publisherusageperformancereportfilter.md)  
[SearchQueryPerformanceReportFilter](searchqueryperformancereportfilter.md)  
[ShareOfVoiceReportFilter](shareofvoicereportfilter.md)  
[UserLocationPerformanceReportFilter](userlocationperformancereportfilter.md)  
