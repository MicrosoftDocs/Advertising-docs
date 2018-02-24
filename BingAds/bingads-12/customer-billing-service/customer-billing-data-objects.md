---
title: Customer Billing Data Objects
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Data objects reference for the CustomerBilling service.
---
# Customer Billing Data Objects

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

The Customer Billing service defines the following data objects.

|Data Object|Description|
|---|---|
|[AdApiError](adapierror.md)|Defines an error object that contains the details that explain why the service operation failed.|
|[AdApiFaultDetail](adapifaultdetail.md)|Defines a fault object that operations return when generic errors occur, such as an authentication error.|
|[ApiBatchFault](apibatchfault.md)|Defines a fault object that operations return when web service-specific errors occur, such as when the request message contains incomplete or invalid data.|
|[ApiFault](apifault.md)|Defines a fault object that operations return when web service-specific errors occur, such as when the request message contains incomplete or invalid data.|
|[ApplicationFault](applicationfault.md)|Defines the base object from which all fault detail objects derive.|
|[BatchError](batcherror.md)|Defines an error object that identifies the item within the batch of items in the request message that caused the operation to fail, and describes the reason for the failure.|
|[BillingDocument](billingdocument.md)|Defines a billing document.|
|[BillingDocumentInfo](billingdocumentinfo.md)|Defines a billing document identification object that contains information about a billing document, such as the billing document identifier, billing document amount, and account identifier.|
|[InsertionOrder](insertionorder.md)|Defines an insertion order.|
|[OperationError](operationerror.md)|Defines an error object that contains the details that explain why the service operation failed.|
|[OrderBy](orderby.md)|Defines an order for the list of insertion orders returned using the [SearchInsertionOrders](/bingads/customer-billing-service/searchinsertionorders.md) operation.|
|[Paging](paging.md)|Defines a paging object for the list of insertion orders returned using the [SearchInsertionOrders](/bingads/customer-billing-service/searchinsertionorders.md) operation.|
|[Predicate](predicate.md)|Defines a predicate for the list of insertion orders returned using the [SearchInsertionOrders](/bingads/customer-billing-service/searchinsertionorders.md) operation.|
