---
title: InsertionOrderStatus Value Set - Customer Billing
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible status values of an InsertionOrder.
---
# InsertionOrderStatus Value Set - Customer Billing
Defines the possible status values of an [InsertionOrder](insertionorder.md).

## Syntax
```xml
<xs:simpleType name="InsertionOrderStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="PendingSystemReview" />
    <xs:enumeration value="PendingUserReview" />
    <xs:enumeration value="Active" />
    <xs:enumeration value="Declined" />
    <xs:enumeration value="Expired" />
    <xs:enumeration value="Canceled" />
    <xs:enumeration value="Pending" />
    <xs:enumeration value="Exhausted" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="active"></a>Active|You have an approved insertion order, and your ads are eligible to run.|
|<a name="canceled"></a>Canceled|You have canceled an order that you created or that was created by Bing Ads. A canceled order cannot be reactivated. |
|<a name="declined"></a>Declined|You have declined an order created by Bing Ads, or the order you created has been declined. Submit a new order, contact your Bing Ads account manager, or [contact support](http://go.microsoft.com/fwlink?LinkId=398371).|
|<a name="exhausted"></a>Exhausted|Your balance has been depleted and the order is no longer active.<br/><br/> This status is read-only and only the system can set the status to Exhausted.|
|<a name="expired"></a>Expired|Your order has reached its end date and is no longer valid.<br/><br/> This status is read-only and only the system can set the status to Expired.|
|<a name="pending"></a>Pending|You have an approved order that has not reached its start date yet.<br/><br/> This status is read-only and only the system can set the status to Pending.|
|<a name="pendingsystemreview"></a>PendingSystemReview|This value is deprecated.<br/><br/> Previously this read-only status indicated that you created a new order and submitted it for approval. The process used to take up to 48 hours. Beginning in calendar Q2 2017, insertion orders that you create are immediately set to Active, Pending, or Declined.|
|<a name="pendinguserreview"></a>PendingUserReview|You need to approve or decline an order that Bing Ads created for your account.<br/><br/> This status is read-only and only the system can set the status to PendingUserReview.|

## Requirements
Service: [CustomerBillingService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v11/CustomerBillingService.svc)  
Namespace: https\://bingads.microsoft.com/Billing/v11  

## Used By
[InsertionOrder](insertionorder.md)  
