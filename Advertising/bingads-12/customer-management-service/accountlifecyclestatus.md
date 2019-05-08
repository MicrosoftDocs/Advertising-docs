---
title: AccountLifeCycleStatus Value Set - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible status values of an account.
---
# AccountLifeCycleStatus Value Set - Customer Management
Defines the possible status values of an account.

## Syntax
```xml
<xs:simpleType name="AccountLifeCycleStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Draft" />
    <xs:enumeration value="Active" />
    <xs:enumeration value="Inactive" />
    <xs:enumeration value="Pause" />
    <xs:enumeration value="Pending" />
    <xs:enumeration value="Suspended" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="active"></a>Active|The account is active, which means that the account and its campaigns can be managed and its ads served.|
|<a name="draft"></a>Draft|The account is in a draft state. When you add an account, the system sets the status to Draft. After the system validates the payment instrument, the status changes to Active. You cannot add another account while the customer has an account in the Draft state.|
|<a name="inactive"></a>Inactive|The account is inactive, which means that the system deleted the account.|
|<a name="pause"></a>Pause|For internal use only. You may update the account and its campaigns while the account is in the paused state.|
|<a name="pending"></a>Pending|For internal use only. You may update the account and its campaigns while the account is in the pending state.|
|<a name="suspended"></a>Suspended|Your account has been suspended because of suspicious activity, and no ads are eligible for delivery.<br/>Please contact [Microsoft Advertising Support](https://go.microsoft.com/fwlink/?LinkId=269631).|

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

## Used By
[AccountInfo](accountinfo.md)  
[AccountInfoWithCustomerData](accountinfowithcustomerdata.md)  
[AdvertiserAccount](advertiseraccount.md)  
