---
title: DataScope Value Set - Bulk
ms.service: bing-ads-bulk-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the scope or types of data to download.
---
# DataScope Value Set - Bulk
Defines the scope or types of data to download.

## Syntax
```xml
<xs:simpleType name="DataScope" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="EntityData" />
        <xs:enumeration value="EntityPerformanceData" />
        <xs:enumeration value="QualityScoreData" />
        <xs:enumeration value="BidSuggestionsData" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="bidsuggestionsdata"></a>BidSuggestionsData|Download the keyword bid suggestion records.|
|<a name="entitydata"></a>EntityData|Download entity records e.g., campaigns and ad groups.|
|<a name="entityperformancedata"></a>EntityPerformanceData|This value is not supported in Bing Ads API Version 12, and will be removed in a future version. If you want data aggregated by day, week, or month, you can use the Bing Ads Reporting API. For more details see [Reports](../guides/reports.md).|
|<a name="qualityscoredata"></a>QualityScoreData|Download the quality score fields i.e., Quality Score, Keyword Relevance, Landing Page Relevance, and Landing Page User Experience in the [Ad Group](#ad-group.md), [Campaign](#campaign.md), and [Keyword](#keyword.md) records.|

## Requirements
Service: [BulkService.svc v12](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/BulkService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md)  
[DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md)  
