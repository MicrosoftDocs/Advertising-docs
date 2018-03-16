---
title: InsertionOrderStatus Value Set - Customer Billing
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible status values of an InsertionOrder.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# InsertionOrderStatus Value Set - Customer Billing
Defines the possible status values of an [InsertionOrder](insertionorder.md).

## Syntax
```xml
<xs:simpleType name="InsertionOrderStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="PendingUserReview">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Active">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Declined">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">3</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Expired">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">4</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Canceled">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">5</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="NotStarted">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">6</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Exhausted">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">7</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="active"></a>Active|You have an approved insertion order, and your ads are eligible to run.<br/><br/>You can also use this value on update to approve an insertion order if its [Status](insertionorder.md#status) is PendingUserReview.<br/><br/>Once approved, the insertion order can only be updated via the [InsertionOrderPendingChanges](insertionorderpendingchanges.md) object.|
|<a name="canceled"></a>Canceled|You have canceled an order that you created or that was created by Bing Ads. A canceled order cannot be reactivated. <br/><br/>You can use this value on update to cancel an insertion order if its [Status](insertionorder.md#status) is Active, Exhausted, or NotStarted. If the insertion order [Status](insertionorder.md#status) is PendingUserReview, then only an internal Bing Ads system admin can use this value on update to cancel an insertion order.|
|<a name="declined"></a>Declined|You have declined an order created by Bing Ads, or the order you created has been declined. Submit a new order, contact your Bing Ads account manager, or [contact support](http://go.microsoft.com/fwlink?LinkId=398371).<br/><br/>You can also use this value on update to decline an insertion order if its [Status](insertionorder.md#status) is PendingUserReview. An internal Bing Ads system admin cannot use this value on update.|
|<a name="exhausted"></a>Exhausted|Your balance has been depleted and the order is no longer active.<br/><br/>This status is read-only and only the system can set the status to Exhausted.|
|<a name="expired"></a>Expired|Your order has reached its end date and is no longer valid.<br/><br/>To reenable an expired insertion order you can extend the end date via the [EndDate](insertionorderpendingchanges.md#enddate) element of the [InsertionOrderPendingChanges](insertionorderpendingchanges.md) object. Note that the [StartDate](insertionorderpendingchanges.md#startdate) of an expired insertion order cannot be updated.<br/><br/>This status is read-only and only the system can set the status to Expired.|
|<a name="notstarted"></a>NotStarted|You have an approved order that has not reached its start date yet.<br/><br/>This status is read-only and only the system can set the status to NotStarted.|
|<a name="pendinguserreview"></a>PendingUserReview|You need to approve or decline an order that Bing Ads created for your account.<br/><br/> This status is read-only and can only be set by Bing Ads.|

## Requirements
Service: [CustomerBillingService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v12/CustomerBillingService.svc)  
Namespace: https\://bingads.microsoft.com/Billing/v12  

## Used By
[InsertionOrder](insertionorder.md)  
