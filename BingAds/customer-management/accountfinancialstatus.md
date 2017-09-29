---
title: AccountFinancialStatus Value Set
ms.service: bing-ads-customer-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# AccountFinancialStatus Value Set
Defines the possible financial status values of an account.

## Syntax
```xml
<xs:simpleType name="AccountFinancialStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Proposed" />
    <xs:enumeration value="PendingCreditCheck" />
    <xs:enumeration value="ClearFinancialStatus" />
    <xs:enumeration value="SoldToOnly" />
    <xs:enumeration value="CreditWarning" />
    <xs:enumeration value="Hold" />
    <xs:enumeration value="WriteOff" />
    <xs:enumeration value="TaxOnHold" />
    <xs:enumeration value="UserHold" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="clearfinancialstatus"></a>ClearFinancialStatus|The account is in good standing.|
|<a name="creditwarning"></a>CreditWarning|Not used.|
|<a name="hold"></a>Hold|For an advertiser account, this status indicates that the account is past due. The service will not deliver the account?s ads until the account is settled. For a credit card account, this status indicates that the card has been declined three times.<br /><br />For a publisher account, this status indicates that the payout to the publisher is placed on hold by the customer service organization. The service continues to deliver the account?s ads.|
|<a name="pendingcreditcheck"></a>PendingCreditCheck|Not used.|
|<a name="proposed"></a>Proposed|For an advertiser account, this status indicates that the customer can add campaigns to the account; however, the service will not deliver the account?s ads.|
|<a name="soldtoonly"></a>SoldToOnly|Not used.|
|<a name="taxonhold"></a>TaxOnHold|For a publisher account, this status indicates that the publisher has yet to provide a valid tax instrument. The service continues to deliver the account?s ads.|
|<a name="userhold"></a>UserHold|For a publisher account, this status indicates that the payout to the publisher was placed on hold by publisher. The service continues to deliver the account?s ads.|
|<a name="writeoff"></a>WriteOff|The account is past due; however, collection is no longer being pursued. When this status is set, the `Status` element of the [Account](../customer-management/account.md) will be set to *Inactive*.|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

## Used By
[Account](account.md)  
