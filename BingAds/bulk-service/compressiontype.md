---
title: CompressionType Value Set - Bulk
ms.service: bing-ads-bulk-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible compression types for the file to download.
---
# CompressionType Value Set - Bulk
Defines the possible compression types for the file to download.

## Syntax
```xml
<xs:simpleType name="CompressionType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Zip" />
    <xs:enumeration value="GZip" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="gzip"></a>GZip|The file should be GZIP compressed.|
|<a name="zip"></a>Zip|The file should be ZIP compressed.|

## Requirements
Service: [BulkService.svc v11](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/BulkService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md)  
[DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md)  
