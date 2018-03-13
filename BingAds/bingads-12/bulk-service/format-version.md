---
title: "Format Version Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Format Version fields in a Bulk file.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Format Version Record - Bulk
Defines the format version of records in a bulk file.

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For the *Format Version* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Name](#name)

The *Format Version* record is included in the Bulk download file automatically everytime you call the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. 

### <a name="name"></a>Name
This string represents the format version used for bulk download and upload. The format version differs from the Bing Ads API version. Currently for version 12 of the Bing Ads Bulk API, the only supported format version  is *6.0*. For more information, see [Format Versions](bulk-file-schema.md#formatversions).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  
