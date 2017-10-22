---
title: UserLifeCycleStatus Value Set - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: "article"
ms.date: 11/1/2017
author: eric-urban
ms.author: eur
description: Defines the possible status values of a user.
---
# UserLifeCycleStatus Value Set - Customer Management
Defines the possible status values of a user.

## Syntax
```xml
<xs:simpleType name="UserLifeCycleStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Pending" />
    <xs:enumeration value="Active" />
    <xs:enumeration value="Inactive" />
    <xs:enumeration value="Deleted" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="active"></a>Active|The user is active.|
|<a name="deleted"></a>Deleted|Reserved for internal use. The user was deleted.|
|<a name="inactive"></a>Inactive|Reserved for internal use. The user was disabled by the system.|
|<a name="pending"></a>Pending|The user is a new user who has not been activated. The user is sent notification about how to activate the account. After the user activates the account, the status changes to Active.<br/><br/> This status is deprecated and is only applicable for managed user credentials, and not for Microsoft account (MSA) users. |

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

## Used By
[GetUsersInfo](getusersinfo.md)  
[User](user.md)  
