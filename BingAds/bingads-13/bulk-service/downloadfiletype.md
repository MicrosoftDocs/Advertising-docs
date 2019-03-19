---
title: DownloadFileType Value Set - Bulk
ms.service: bing-ads-bulk-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the file formats for a download request.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# DownloadFileType Value Set - Bulk
Defines the file formats for a download request.

> [!NOTE]
> The downloaded **Csv** or **Tsv** file will be ZIP compressed.

## Syntax
```xml
<xs:simpleType name="DownloadFileType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Csv" />
    <xs:enumeration value="Tsv" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="csv"></a>Csv|The file format is comma separated values (CSV).<br/><br/>The downloaded file will be ZIP compressed.|
|<a name="tsv"></a>Tsv|The file format is tab separated values (TSV).<br/><br/>The downloaded file will be ZIP compressed.|

## Requirements
Service: [BulkService.svc v13](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/BulkService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md)  
[DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md)  
