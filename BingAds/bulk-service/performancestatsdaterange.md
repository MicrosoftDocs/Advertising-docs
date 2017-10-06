---
title: PerformanceStatsDateRange Data Object
ms.service: bing-ads-bulk-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the date range values for the requested performance data in a bulk download.
---
# PerformanceStatsDateRange Data Object
Defines the date range values for the requested performance data in a bulk download.

## Syntax
```xml
<xs:complexType name="PerformanceStatsDateRange" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="CustomDateRangeEnd" nillable="true" type="tns:Date" />
    <xs:element minOccurs="0" name="CustomDateRangeStart" nillable="true" type="tns:Date" />
    <xs:element minOccurs="0" name="PredefinedTime" nillable="true" type="tns:ReportTimePeriod" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customdaterangeend"></a>CustomDateRangeEnd|The end date of the custom date range. The end date cannot be later than today?s date.|[Date](date.md)|
|<a name="customdaterangestart"></a>CustomDateRangeStart|The start date of the custom date range. The start date must be earlier than or the same as the end date.|[Date](date.md)|
|<a name="predefinedtime"></a>PredefinedTime|A predefined date range value.|[ReportTimePeriod](reporttimeperiod.md)|

## Requirements
Service: [BulkService.svc v11](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/BulkService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md)  
[DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md)  
