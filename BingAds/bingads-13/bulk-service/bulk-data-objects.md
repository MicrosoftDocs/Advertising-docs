---
title: Bulk Data Objects
ms.service: bing-ads-bulk-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Data objects reference for the Bulk service.
---
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
|[EditorialError](editorialerror.md)|Defines an error object that identifies the entity with the batch of entities that failed editorial review.|
|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md)|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.|
|[OperationError](operationerror.md)|Defines an error object that contains the details that explain why the service operation failed.|
