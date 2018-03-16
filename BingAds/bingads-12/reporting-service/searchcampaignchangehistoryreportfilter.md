---
title: SearchCampaignChangeHistoryReportFilter Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the criteria to use to filter the campaign change history report data.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# SearchCampaignChangeHistoryReportFilter Data Object - Reporting
Defines the criteria to use to filter the campaign change history report data.

## Syntax
```xml
<xs:complexType name="SearchCampaignChangeHistoryReportFilter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AdDistribution" nillable="true" type="tns:AdDistributionReportFilter" />
    <xs:element minOccurs="0" name="HowChanged" nillable="true" type="tns:ChangeTypeReportFilter" />
    <xs:element minOccurs="0" name="ItemChanged" nillable="true" type="tns:ChangeEntityReportFilter" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="addistribution"></a>AdDistribution|The report will include data for only the specified distribution medium. For example, you can use the filter to include data for only search ads.<br /><br />You can specify one or more distribution mediums.|[AdDistributionReportFilter](addistributionreportfilter.md)|
|<a name="howchanged"></a>HowChanged|The report will include data for only the specified type of change. For example, you can use the filter to include data only for updates or deletions.<br /><br />You may specify only one type of change.|[ChangeTypeReportFilter](changetypereportfilter.md)|
|<a name="itemchanged"></a>ItemChanged|The report will include data for only the specified type of entity. For example, you can use the filter to include data only for changes to ad groups or campaigns.<br /><br />You may specify only one type of entity.|[ChangeEntityReportFilter](changeentityreportfilter.md)|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v12/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[SearchCampaignChangeHistoryReportRequest](searchcampaignchangehistoryreportrequest.md)  
