---
title: DSACategoryPerformanceReportFilter Data Object
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the criteria to use to filter the DSA category performance report data.
---
# DSACategoryPerformanceReportFilter Data Object
Defines the criteria to use to filter the DSA category performance report data.

## Syntax
```xml
<xs:complexType name="DSACategoryPerformanceReportFilter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AccountStatus" nillable="true" type="tns:AccountStatusReportFilter" />
    <xs:element minOccurs="0" name="AdGroupStatus" nillable="true" type="tns:AdGroupStatusReportFilter" />
    <xs:element minOccurs="0" name="AdStatus" nillable="true" type="tns:AdStatusReportFilter" />
    <xs:element minOccurs="0" name="CampaignStatus" nillable="true" type="tns:CampaignStatusReportFilter" />
    <xs:element minOccurs="0" name="LanguageCode" nillable="true" type="q34:ArrayOfstring" xmlns:q34="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountstatus"></a>AccountStatus|The report will include data for only the account status. For example, you can use the filter to include data for only active accounts.<br /><br />You can specify one or more account statuses.|[AccountStatusReportFilter](accountstatusreportfilter.md)|
|<a name="adgroupstatus"></a>AdGroupStatus|The report will include data for only the ad group status. For example, you can use the filter to include data for only active ad groups.<br /><br />You can specify one or more ad group statuses.|[AdGroupStatusReportFilter](adgroupstatusreportfilter.md)|
|<a name="adstatus"></a>AdStatus|The report will include data for ads that have the specified status value. You can specify one or more status values.|[AdStatusReportFilter](adstatusreportfilter.md)|
|<a name="campaignstatus"></a>CampaignStatus|The report will include data for campaigns that have the specified status value. You can specify one or more status values.|[CampaignStatusReportFilter](campaignstatusreportfilter.md)|
|<a name="languagecode"></a>LanguageCode|The report will include data for only websites that used the specified languages. For a list of possible values, see [Ad Languages](~/guides/ad-languages.md).|**string**|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https://bingads.microsoft.com/Reporting/v11  

## Used By
[DSACategoryPerformanceReportRequest](dsacategoryperformancereportrequest.md)  
