---
title: UserRole Value Set
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible roles of a user.
---
# UserRole Value Set
Defines the possible roles of a user.

## Syntax
```xml
<xs:simpleType name="UserRole" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="AdvertiserCampaignManager" />
    <xs:enumeration value="SuperAdmin" />
    <xs:enumeration value="ClientViewer" />
    <xs:enumeration value="ClientManager" />
    <xs:enumeration value="PublisherAdmin" />
    <xs:enumeration value="PublisherAccountManager" />
    <xs:enumeration value="PublisherReportUser" />
    <xs:enumeration value="PublisherListManager" />
    <xs:enumeration value="PublisherAdViewer" />
    <xs:enumeration value="ClientAdmin" />
    <xs:enumeration value="StandardUser" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="advertisercampaignmanager"></a>AdvertiserCampaignManager|This role has permissions to view selected accounts and add, edit, or delete campaigns within the selected accounts. The Advertiser Campaign Manager can view payment methods, but cannot manage any billing and payment tasks.|
|<a name="clientadmin"></a>ClientAdmin|Reserved for internal use.|
|<a name="clientmanager"></a>ClientManager|Reserved for internal use.|
|<a name="clientviewer"></a>ClientViewer|Reserved for internal use.|
|<a name="publisheraccountmanager"></a>PublisherAccountManager|Reserved for internal use.|
|<a name="publisheradmin"></a>PublisherAdmin|Reserved for internal use.|
|<a name="publisheradviewer"></a>PublisherAdViewer|Reserved for internal use.|
|<a name="publisherlistmanager"></a>PublisherListManager|Reserved for internal use.|
|<a name="publisherreportuser"></a>PublisherReportUser|Reserved for internal use.|
|<a name="standarduser"></a>StandardUser|This role has permissions to manage campaigns and perform some billing activities on specific accounts. This role cannot add, edit, or delete payment methods or other users; create or delete accounts; or link to or unlink from clients.|
|<a name="superadmin"></a>SuperAdmin|This role has full permissions for all accounts. A Super Admin can manage everything related to billing and payments, account details, and other users (including other Super Admins). The Super Admin can specify which accounts other users have access to. When signing up as a new customer, the first user is the Super Admin.|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

## Used By
[UserInvitation](userinvitation.md)  
