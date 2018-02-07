---
title: Customer Billing Service Operations
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Service operations reference for the CustomerBilling service.
---
# Customer Billing Service Operations

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

The Customer Billing service defines the following service operations.

|Service Operation|Description|Request Limits|
|---|---|---|
|[AddInsertionOrder](addinsertionorder.md)|Adds an insertion order to the specified account.|N/A.|
|[GetAccountMonthlySpend](getaccountmonthlyspend.md)|Gets the amount spent by the account in the specified month.|1 *AccountId*|
|[GetBillingDocuments](getbillingdocuments.md)|Gets the specified billing documents.|Not applicable.|
|[GetBillingDocumentsInfo](getbillingdocumentsinfo.md)|Gets a list of objects that contains billing document identification information, for example the billing document identifier, amount, and account identifier.|Not applicable.|
|[GetInsertionOrdersByAccount](getinsertionordersbyaccount.md)|Gets a list of insertion orders for the specified account.|1 *AccountId*|
|[SearchInsertionOrders](searchinsertionorders.md)|Searches for insertion orders that match a specified criteria.|6 *Predicates*|
|[UpdateInsertionOrder](updateinsertionorder.md)|Updates an insertion order within the specified account.|1 *AccountId*<br/>1 *InsertionOrder*|
