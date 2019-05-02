---
title: AccountThroughAdGroupReportScope Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the set of accounts, campaigns, and ad groups to include in the report.
---
# AccountThroughAdGroupReportScope Data Object - Reporting
Defines the set of accounts, campaigns, and ad groups to include in the report.

The report scope includes a union of the included [AccountIds](#accountids), [AdGroups](#adgroups), and [Campaigns](#campaigns) elements.

## Syntax
```xml
<xs:complexType name="AccountThroughAdGroupReportScope" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AccountIds" nillable="true" type="q4:ArrayOflong" xmlns:q4="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element minOccurs="0" name="AdGroups" nillable="true" type="tns:ArrayOfAdGroupReportScope" />
    <xs:element minOccurs="0" name="Campaigns" nillable="true" type="tns:ArrayOfCampaignReportScope" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountids"></a>AccountIds|A list of up to 1,000 account identifiers to include in the report.|**long** array|
|<a name="adgroups"></a>AdGroups|A list of up to 300 ad groups to include in the report.|[AdGroupReportScope](adgroupreportscope.md) array|
|<a name="campaigns"></a>Campaigns|A list of up to 300 campaigns to include in the report.|[CampaignReportScope](campaignreportscope.md) array|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v12/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
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
[ConversionPerformanceReportRequest](conversionperformancereportrequest.md)  
[DestinationUrlPerformanceReportRequest](destinationurlperformancereportrequest.md)  
[DSAAutoTargetPerformanceReportRequest](dsaautotargetperformancereportrequest.md)  
[DSACategoryPerformanceReportRequest](dsacategoryperformancereportrequest.md)  
[DSASearchQueryPerformanceReportRequest](dsasearchqueryperformancereportrequest.md)  
[GeographicPerformanceReportRequest](geographicperformancereportrequest.md)  
[GoalsAndFunnelsReportRequest](goalsandfunnelsreportrequest.md)  
[KeywordPerformanceReportRequest](keywordperformancereportrequest.md)  
[NegativeKeywordConflictReportRequest](negativekeywordconflictreportrequest.md)  
[ProductDimensionPerformanceReportRequest](productdimensionperformancereportrequest.md)  
[ProductMatchCountReportRequest](productmatchcountreportrequest.md)  
[ProductPartitionPerformanceReportRequest](productpartitionperformancereportrequest.md)  
[ProductPartitionUnitPerformanceReportRequest](productpartitionunitperformancereportrequest.md)  
[ProductSearchQueryPerformanceReportRequest](productsearchqueryperformancereportrequest.md)  
[ProfessionalDemographicsAudienceReportRequest](professionaldemographicsaudiencereportrequest.md)  
[PublisherUsagePerformanceReportRequest](publisherusageperformancereportrequest.md)  
[SearchCampaignChangeHistoryReportRequest](searchcampaignchangehistoryreportrequest.md)  
[SearchQueryPerformanceReportRequest](searchqueryperformancereportrequest.md)  
[ShareOfVoiceReportRequest](shareofvoicereportrequest.md)  
[UserLocationPerformanceReportRequest](userlocationperformancereportrequest.md)  
