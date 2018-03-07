---
title: "Bulk Service Reference"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Reference documentation for the Bing Ads Bulk API.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# Bulk Service Reference
The Bulk [service](../guides/web-service-addresses.md) defines an Application Programming Interface (API) that you can use to download and upload campaign entity data in the background.

|Interface|Description|
|---------|---------|
|[Bulk Service Operations](bulk-service-operations.md)|Service operations such as [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) and [GetBulkUploadUrl](getbulkuploadurl.md) can be used to download and upload campaign entity data in the background.|
|[Bulk Data Objects](bulk-data-objects.md)|If want to include performance report data in the Bulk download, you can use the [Date](date.md) and [PerformanceStatsDateRange](performancestatsdaterange.md) objects.|
|[Bulk Value Sets](bulk-value-sets.md)|Choose which data is downloaded with the [DataScope ](datascope.md) and [DownloadEntity](downloadentity.md) value sets.|
|[Bulk File Schema](bulk-file-schema.md)|The bulk schema defines the contents of the file for download or upload with the Bing Ads Bulk service. For both download and upload, the Bulk service supports the file types and corresponding schemas in the [DownloadEntity](downloadentity.md) value set. For more information about using the Bulk service to manage your campaigns, see [Bulk Download and Upload](../guides/bulk-download-upload.md). |

## See Also
[Get Started With the Bing Ads API](../guides/get-started.md)  
[Bing Ads Technical Guides](../guides/technical-guides.md)  
[Bing Ads Web Service Addresses](../guides/web-service-addresses.md)  

