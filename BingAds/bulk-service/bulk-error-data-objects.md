---
title: "Bulk Error Data Objects"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
---
# Bulk Error Data Objects
Bing Ads bulk service operations may throw fault exceptions that include one or more error objects. The error objects contain the details of why the service operation failed.

## Fault Objects
The following fault objects may be thrown by the bulk service, and should be caught within your application.

|Fault Object|Description|
|----------------|---------------|
|[AdApiFaultDetail](../bulk-service/adapifaultdetail.md)|Defines a fault object that operations return when generic errors occur, such as an authentication error.|
|[ApiFaultDetail](../bulk-service/apifaultdetail.md)|Defines a fault object that operations return when web service-specific errors occur, such as when the request message contains incomplete or invalid data.|
|[ApplicationFault](../bulk-service/applicationfault.md)|Defines the base object from which all fault detail objects derive.<br /><br />**Note:** Do not catch [ApplicationFault](../bulk-service/applicationfault.md), and instead catch one or more of the derived faults such as [AdApiFaultDetail](../bulk-service/adapifaultdetail.md).|

## Error Objects
The following error objects may be returned within bulk fault objects, and contain the details of why the service operation failed.

|Error Object|Description|
|----------------|---------------|
|[AdApiError](../bulk-service/adapierror.md)|Defines an error object that contains the details of why the service operation failed.|
|[BatchError](../bulk-service/batcherror.md)|Defines an error object that identifies the item within the batch of items in the request message that caused the operation to fail, and the reason for the failure.|
|[EditorialError](../bulk-service/editorialerror.md)|Defines an error object that identifies the entity with the batch of entities that failed editorial review.|
|[OperationError](../bulk-service/operationerror.md)|Defines an error object that contains the details of why the service operation failed.|
