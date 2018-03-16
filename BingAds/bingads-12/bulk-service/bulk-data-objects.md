---
title: Bulk Data Objects
ms.service: bing-ads-bulk-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Data objects reference for the Bulk service.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Bulk Data Objects
The Bulk service defines the following data objects.

|Data Object|Description|
|---|---|
|[AdApiError](adapierror.md)|Defines an error object that contains the details that explain why the service operation failed.|
|[AdApiFaultDetail](adapifaultdetail.md)|Defines a fault object that operations return when generic errors occur, such as an authentication error.|
|[ApiFaultDetail](apifaultdetail.md)|Defines a fault object that operations return when web service-specific errors occur, such as when the request message contains incomplete or invalid data.|
|[ApplicationFault](applicationfault.md)|Defines the base object from which all fault detail objects derive.|
|[BatchError](batcherror.md)|Defines an error object that identifies the item within the batch of items in the request message that caused the operation to fail, and describes the reason for the failure.|
|[CampaignScope](campaignscope.md)|Defines an object that identifies a campaign to download.|
|[Date](date.md)|Defines a calendar date by month, day, and year.|
|[EditorialError](editorialerror.md)|Defines an error object that identifies the entity with the batch of entities that failed editorial review.|
|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md)|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.|
|[OperationError](operationerror.md)|Defines an error object that contains the details that explain why the service operation failed.|
|[PerformanceStatsDateRange](performancestatsdaterange.md)|This data object is not supported in Bing Ads API Version 12, and will be removed in a future version.|
