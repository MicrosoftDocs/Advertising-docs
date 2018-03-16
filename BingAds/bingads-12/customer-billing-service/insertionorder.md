---
title: InsertionOrder Data Object - Customer Billing
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an insertion order.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# InsertionOrder Data Object - Customer Billing
Defines an insertion order.

An insertion order is a contract in which you agree to spend up to a certain amount (not exceeding your credit line) over a time period. Advertisers use insertion orders to manage spend and budgets within their monthly invoice accounts. An account can have multiple active insertion orders, and only one insertion order is spending at a time. The spending insertion order is the one with the earliest end date.

Most elements of this object can only be set before the insertion order becomes approved i.e., if the [Status](#status) is set to PendingUserReview. In that case you can either make new changes or approve, decline, or cancel the insertion order via elements of this object. Once the insertion order [Status](#status) is Active, Exhausted, Expired, or NotStarted, then you can either make new changes or approve or decline the current pending changes via the [PendingChanges](#pendingchanges) element. If the insertion order [Status](#status) is Canceled or Declined then you cannot update the insertion order. 

## Syntax
```xml
<xs:complexType name="InsertionOrder" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AccountId" type="xs:long" />
    <xs:element minOccurs="0" name="BalanceAmount" nillable="true" type="xs:double" />
    <xs:element minOccurs="0" name="BookingCountryCode" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Comment" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="EndDate" nillable="true" type="xs:dateTime" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="LastModifiedByUserId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="LastModifiedTime" nillable="true" type="xs:dateTime" />
    <xs:element minOccurs="0" name="NotificationThreshold" nillable="true" type="xs:double" />
    <xs:element minOccurs="0" name="ReferenceId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="SpendCapAmount" type="xs:double" />
    <xs:element minOccurs="0" name="StartDate" nillable="true" type="xs:dateTime" />
    <xs:element minOccurs="0" name="Name" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Status" nillable="true" type="tns:InsertionOrderStatus" />
    <xs:element minOccurs="0" name="PurchaseOrder" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ChangePendingReview" nillable="true" type="xs:boolean" />
    <xs:element minOccurs="0" name="PendingChanges" nillable="true" type="tns:InsertionOrderPendingChanges" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account to which the insertion order applies.<br /><br />You cannot update the account identifier after you create the insertion order.<br/><br/>**Add:** Required<br/>**Update:** Read-only|**long**|
|<a name="balanceamount"></a>BalanceAmount|The running balance of the insertion order. The running balance value is initially the same as the spending limit, and then decreases each time an ad in the account is served.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**double**|
|<a name="bookingcountrycode"></a>BookingCountryCode|A code that identifies the country/region in which the account operates. For a list of country code values, see [Geographical Location Codes](../guides/geographical-location-codes.md).<br /><br />You cannot update the country code after the insertion order becomes active.<br/><br/>**Add:** Required<br/>**Update:** Read-only|**string**|
|<a name="changependingreview"></a>ChangePendingReview|Determines whether or not you need to approve or decline a change made to an existing order by Bing Ads.<br/><br/>The default value (nil) is false. If this element is true then you need to approve or decline a change made to an existing order by Bing Ads.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**boolean**|
|<a name="comment"></a>Comment|A description of the insertion order. The description is limited to 100 characters.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string**|
|<a name="enddate"></a>EndDate|The date that the insertion order expires. The end date must be later than the start date.<br /><br /> The date is stored in Coordinated Universal Time (UTC). Only the month, day, and year of the specified string are used. If you specify the hour, minutes, and seconds of a date they will be ignored.<br /><br />For information about the format of the date and time, see the **dateTime** entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).<br/><br/>**Add:** Required<br/>**Update:** Optional|**dateTime**|
|<a name="id"></a>Id|A system generated identifier that identifies the insertion order.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="lastmodifiedbyuserid"></a>LastModifiedByUserId|An identifier of the last user to update the insertion order.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="lastmodifiedtime"></a>LastModifiedTime|The date and time that the insertion order was last updated.<br /><br /> The date is stored in Coordinated Universal Time (UTC).<br /><br />For information about the format of the date and time, see the **dateTime** entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**dateTime**|
|<a name="name"></a>Name|The friendly name that can be used to reference this insertion order.<br /><br />The name can contain a maximum of 100 characters.<br /><br />The name does not need to be unique compared to other insertion orders for the customer.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string**|
|<a name="notificationthreshold"></a>NotificationThreshold|A percentage of the budget that has been spent. Specify the percentage as a value from 0 to 100. Notification is sent when the threshold is reached. For example, if you set the threshold to 70, the Billing service sends notification when you have spent 70 percent of the budget.<br /><br />If you do not want to receive notification, set to NULL.<br /><br /> Reserved for internal use.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**double**|
|<a name="pendingchanges"></a>PendingChanges|Can be used to manage changes for an approved insertion order with status set to either Active, Exhausted, Expired, or NotStarted.<br/><br/>**Add:** Read-only<br/>**Update:** Optional|[InsertionOrderPendingChanges](insertionorderpendingchanges.md)|
|<a name="purchaseorder"></a>PurchaseOrder|A purchase order value that can be used to reference this insertion order in monthly invoices. This value will be printed as the purchase order in the monthly invoices.<br /><br />The purchase order can contain a maximum of 50 characters.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string**|
|<a name="referenceid"></a>ReferenceId|Internal use only.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**long**|
|<a name="spendcapamount"></a>SpendCapAmount|The budget for this insertion order. The budget is a hard limit. When the account reaches this limit and there is not another insertion order available, the account's lifecycle status value is set to Pause.<br/><br/>**Add:** Required<br/>**Update:** Optional|**double**|
|<a name="startdate"></a>StartDate|The date that the insertion order can begin accruing charges. The start date must be later than the current date.<br /><br /> The date is stored in Coordinated Universal Time (UTC). Only the month, day, and year of the specified string are used. If you specify the hour, minutes, and seconds of a date they will be ignored.<br /><br />For information about the format of the date and time, see the **dateTime** entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).<br/><br/>**Add:** Required<br/>**Update:** Optional|**dateTime**|
|<a name="status"></a>Status|The status of the insertion order.<br/><br/>**Add:** Read-only. Insertion orders that you create are immediately set to Active, NotStarted, or Declined.<br/>**Update:** Required to approve or decline an insertion order that is not yet approved, or cancel an insertion order that has already be approved. You can only approve or decline via this element if the current status is set to PendingUserReview. You can only cancel via this element if the current status is set to Active, Exhausted, or NotStarted. Once the insertion order status is Active, Exhausted, Expired, or NotStarted, then you can either make new changes or approve or decline the current pending changes via the [PendingChanges](#pendingchanges) element.<br/><br/>When you call [UpdateInsertionOrder](updateinsertionorder.md) you can either set this Status element or modify other elements of this object, but you cannot change the status in parallel with other property updates.|[InsertionOrderStatus](insertionorderstatus.md)|

## Requirements
Service: [CustomerBillingService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v12/CustomerBillingService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12/Entities  

## Used By
[AddInsertionOrder](addinsertionorder.md)  
[GetInsertionOrdersByAccount](getinsertionordersbyaccount.md)  
[SearchInsertionOrders](searchinsertionorders.md)  
[UpdateInsertionOrder](updateinsertionorder.md)  
