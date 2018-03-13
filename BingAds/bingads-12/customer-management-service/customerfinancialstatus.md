---
title: CustomerFinancialStatus Value Set - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible financial status values of a customer.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# CustomerFinancialStatus Value Set - Customer Management
Defines the possible financial status values of a customer.

## Syntax
```xml
<xs:simpleType name="CustomerFinancialStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="ProposalsOnly" />
    <xs:enumeration value="PendingCreditCheck" />
    <xs:enumeration value="ClearFinancialStatus" />
    <xs:enumeration value="SoldToOnly" />
    <xs:enumeration value="CreditHold" />
    <xs:enumeration value="CreditWarning" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="clearfinancialstatus"></a>ClearFinancialStatus|The customer is in good standing.|
|<a name="credithold"></a>CreditHold|One of the customer's accounts is past due.|
|<a name="creditwarning"></a>CreditWarning|Not used.|
|<a name="pendingcreditcheck"></a>PendingCreditCheck|The customer is undergoing a credit check as part of the customer sign-up process. The service will not deliver the customer's ads until the credit check is complete. This status applies only to premium customers.|
|<a name="proposalsonly"></a>ProposalsOnly|Not used.|
|<a name="soldtoonly"></a>SoldToOnly|The customer is considered to be a credit risk. You cannot set the `BillToCustomerId` element of the [AdvertiserAccount](advertiseraccount.md) for a customer that has this status. This status applies only to premium customers.|

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

## Used By
[Customer](customer.md)  
