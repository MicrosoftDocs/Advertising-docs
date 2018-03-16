---
title: UserLocationPerformanceReportFilter Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the criteria to use to filter the user location performance report data.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# UserLocationPerformanceReportFilter Data Object - Reporting
Defines the criteria to use to filter the user location performance report data.

## Syntax
```xml
<xs:complexType name="UserLocationPerformanceReportFilter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AdDistribution" nillable="true" type="tns:AdDistributionReportFilter" />
    <xs:element minOccurs="0" name="CountryCode" nillable="true" type="q15:ArrayOfstring" xmlns:q15="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element minOccurs="0" name="LanguageCode" nillable="true" type="q16:ArrayOfstring" xmlns:q16="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="addistribution"></a>AdDistribution|The report will include data for only the specified distribution medium. For example, you can use the filter to include data for only search ads.<br /><br />You can specify one or more distribution mediums.|[AdDistributionReportFilter](addistributionreportfilter.md)|
|<a name="countrycode"></a>CountryCode|The report will include data for only the specified countries/regions where the user that clicked the ad is located.<br /><br />For a list of possible values, see [Geographical Location Codes](../guides/geographical-location-codes.md).|**string** array|
|<a name="languagecode"></a>LanguageCode|The report will include data for only websites that used the specified languages. For a list of possible values, see [Ad Languages](../guides/ad-languages.md).|**string** array|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v12/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[UserLocationPerformanceReportRequest](userlocationperformancereportrequest.md)  
