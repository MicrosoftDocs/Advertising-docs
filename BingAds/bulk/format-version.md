---
title: "Format Version"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
dev_langs:
  - csharp
---
# Format Version
Defines the format version of records in a bulk file.

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For the *Format Version* record, the following attribute fields are available in the [Bulk File Schema](../bulk/bulk-file-schema.md). 

- [Name](#name)

The *Format Version* record is included in the Bulk download file automatically everytime you call the [DownloadCampaignsByAccountIds](../bulk/downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](../bulk/downloadcampaignsbycampaignids.md) service request. 

### <a name="name"></a>Name
This string represents the format version used for bulk download and upload. The format version differs from the Bing Ads API version. Currently for version 11 of the Bing Ads Bulk API, the only supported format version  is *5.0*. For more information, see [Format Versions](../bulk/bulk-file-schema.md#formatversions).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  
