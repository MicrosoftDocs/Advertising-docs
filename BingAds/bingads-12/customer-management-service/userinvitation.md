---
title: UserInvitation Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a user invitation.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# UserInvitation Data Object - Customer Management
Defines a user invitation. When the invitation is accepted, the user's Microsoft account is linked to the specified Bing Ads customer accounts.

It is possible to have multiple pending invitations sent to the same email address, which have not yet expired. It is also possible for those invitations to have specified different user roles, for example if you sent an invitation with an incorrect user role and then sent a second invitation with the correct user role. The recipient can accept any of the invitations. The Bing Ads API does not support any operations to delete pending user invitations. After you invite a user, the only way to cancel the invitation is through the Bing Ads web application. You can find both pending and accepted invitations in the Users section of Accounts & Billing.

Since a recipient can accept the invitation and sign into Bing Ads with a Microsoft account different than the invitation email address, you cannot determine with certainty the mapping from *UserInvitation* to accepted [User](user.md). You can search by the invitation ID (returned by [SendUserInvitation](senduserinvitation.md)), only to the extent of finding out whether or not the invitation has been accepted or has expired. The [SearchUserInvitations](searchuserinvitations.md) operation returns all pending invitations, whether or not they have expired. Accepted invitations are not included in the [SearchUserInvitations](searchuserinvitations.md) response.  

After the invitation has been accepted, you can call [GetUsersInfo](getusersinfo.md) and [GetUser](getuser.md) to access the Bing Ads user details. Once again though, since a recipient can accept the invitation and sign into Bing Ads with a Microsoft account different than the invitation email address, you cannot determine with certainty the mapping from *UserInvitation* to accepted [User](user.md). With the user ID returned by [GetUsersInfo](getusersinfo.md) or [GetUser](getuser.md), you can call [DeleteUser](deleteuser.md) to remove the user.

For more information about user authentication, see [Authentication with OAuth](../guides/authentication-oauth.md).

## Syntax
```xml
<xs:complexType name="UserInvitation" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Id" type="xs:long" />
    <xs:element minOccurs="0" name="FirstName" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="LastName" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Email" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="CustomerId" type="xs:long" />
    <xs:element minOccurs="0" name="RoleId" type="xs:int" />
    <xs:element minOccurs="0" name="AccountIds" nillable="true" type="q8:ArrayOflong" xmlns:q8="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element minOccurs="0" name="ExpirationDate" type="xs:dateTime" />
    <xs:element minOccurs="0" name="Lcid" type="tns:LCID" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountids"></a>AccountIds|An array of identifiers of the accounts that the user can manage. To specify that the user can manage all current and future accounts of the customer to which the user belongs, set to NULL.<br /><br />Users with account level roles such as Advertiser Campaign Manager can be restricted to specific accounts. Users with customer level roles such as Super Admin can access all accounts within the user's customer, and their access cannot be restricted to specific accounts.<br /><br /> When attempting to restrict customer level user roles, for example attempting to restrict a Super Admin to specific accounts, the operation will not fail and the user will be granted access for all accounts within the specified customer.<br/><br/>**Send:** Optional|**long** array|
|<a name="customerid"></a>CustomerId|The identifier of the customer this user is invited to manage. The *AccountIds* element determines which customer accounts the user can manage.<br/><br/>**Send:** Required|**long**|
|<a name="email"></a>Email|The email address corresponding to the user's Microsoft account. The address can contain a maximum of 100 characters.<br/><br/>**Send:** Required|**string**|
|<a name="expirationdate"></a>ExpirationDate|The date and time that the user invitation will expire. The value is in Coordinated Universal Time (UTC).<br /><br /> The duration of a user invitation is subject to change, and currently set at 30 days. You cannot set or update this value.<br/><br/>**Send:** Read-only|**dateTime**|
|<a name="firstname"></a>FirstName|The first name of the user. The first name is limited to 40 characters.<br/><br/>**Send:** Required|**string**|
|<a name="id"></a>Id|A system generated unique identifier for the user invitation.<br/><br/>**Send:** Read-only|**long**|
|<a name="lastname"></a>LastName|The last name of the user. The last name is limited to 40 characters.<br/><br/>**Send:** Required|**string**|
|<a name="lcid"></a>Lcid|The locale to use when sending correspondence to the user by email or postal mail. The default is EnglishUS.<br/><br/>**Send:** Required|[LCID](lcid.md)|
|<a name="roleid"></a>RoleId|The role that the user has for each customer or list of accounts.<br /><br />Possible values include the following:<br />16 - The user has the **Advertiser Campaign Manager** role.<br />33 - The user has the **Aggregator** role.<br />41 - The user has the **Super Admin** role.<br />100 - The user has the **ClientViewer** role.<br />203 - The user has the **Standard** role.<br /><br />For more information, see [User Roles and Available Service Operations](../guides/customer-accounts.md#userroles).|**int**|

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12/Entities  

## Used By
[SearchUserInvitations](searchuserinvitations.md)  
[SendUserInvitation](senduserinvitation.md)  
