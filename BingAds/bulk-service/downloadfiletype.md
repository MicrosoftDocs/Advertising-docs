---
title: DownloadFileType Value Set - Bulk
ms.service: bing-ads-bulk-service
ms.topic: "article"
ms.date: 11/1/2017
author: eric-urban
ms.author: eur
description: Defines the file formats for a download request.
---
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
|<a name="csv"></a>Csv|The file format is comma separated values (CSV).|
|<a name="tsv"></a>Tsv|The file format is tab separated values (TSV).|

## Requirements
Service: [BulkService.svc v11](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/BulkService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md)  
[DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md)  
