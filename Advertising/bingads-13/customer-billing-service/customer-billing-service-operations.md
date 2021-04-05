---
title: Customer Billing Service Operations
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Service operations reference for the CustomerBilling service.
---
# Customer Billing Service Operations
The Customer Billing service defines the following service operations.

|Service Operation|Description|Request Limits|
|---|---|---|
|[AddInsertionOrder](addinsertionorder.md)|Adds an insertion order to the specified account.|N/A.|
|[DispatchCoupons](dispatchcoupons.md)|Defines the DispatchCoupons Service Operation.|1 *CouponClassName*|
|[GetAccountMonthlySpend](getaccountmonthlyspend.md)|Gets the amount spent by the account in the specified month.|1 *AccountId*|
|[GetBillingDocuments](getbillingdocuments.md)|Gets the specified billing documents.|25 *BillingDocumentInfo*|
|[GetBillingDocumentsInfo](getbillingdocumentsinfo.md)|Gets a list of objects that contains billing document identification information, for example the billing document identifier, amount, and account identifier.|Not applicable.|
|[RedeemCoupon](redeemcoupon.md)|Defines the RedeemCoupon Service Operation.|1 *CouponCode*|
|[SearchCoupons](searchcoupons.md)|Defines the SearchCoupons Service Operation.|1 *Predicates*|
|[SearchInsertionOrders](searchinsertionorders.md)|Searches for insertion orders that match a specified criteria.|6 *Predicates*|
|[UpdateInsertionOrder](updateinsertionorder.md)|Updates an insertion order within the specified account.|1 *AccountId*<br/>1 *InsertionOrder*|
