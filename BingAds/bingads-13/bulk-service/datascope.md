---
title: DataScope Value Set - Bulk
ms.service: bing-ads-bulk-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the scope or types of data to download.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# DataScope Value Set - Bulk
Defines the scope or types of data to download.

## Syntax
```xml
<xs:simpleType name="DataScope" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="EntityData" />
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
|<a name="qualityscoredata"></a>QualityScoreData|Download the quality score fields i.e., Quality Score, Keyword Relevance, Landing Page Relevance, and Landing Page User Experience in the [Ad Group](#ad-group.md), [Campaign](#campaign.md), and [Keyword](#keyword.md) records.|

## Requirements
Service: [BulkService.svc v13](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/BulkService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md)  
[DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md)  
