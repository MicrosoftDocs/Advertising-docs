---
title: "Customer Accounts"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Manage accounts as a direct advertiser, on behalf of other customers, or build commercial tools.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Customer Accounts
Whether you are managing your own Bing Ads account as a direct advertiser, building commercial tools, or managing campaigns on behalf of other customers, we will introduce opportunities and quickly get you oriented. Manage customer, account, and user entities programmatically with the Customer Management service. For an introduction to the account and campaign hierarchy within a customer, see [Entity Hierarchy and Limits](entity-hierarchy-limits.md).

## <a name="accountmodels"></a>Account Management Models
Search advertising businesses typically align with one or more of the following account management models. 

|Model|Description|
|---------|---------------|
|Direct Advertiser|A direct advertiser builds a Bing Ads application for its own advertising campaigns and is billed directly by Microsoft for valid ad clicks. For relevant best practices, see [Management Model for Direct Advertisers](management-model-direct-advertisers.md).|
|Tool Provider|A tool provider builds a Bing Ads application for other companies to manage their advertising campaigns, and is not billed by Microsoft. The advertiser user owns the accounts, is billed directly by Microsoft for valid ad clicks, and may pay a fee to the tool provider. For relevant best practices, see [Management Model for Tool Providers](management-model-tool-providers.md).|
|Agency|An agency builds a Bing Ads application for their company to manage the campaigns of their advertising clients. The client of the agency owns the accounts, is billed directly by Microsoft for valid ad clicks, and may pay a fee to the agency. For relevant best practices, see [Management Model for Agencies](management-model-agencies.md).|
|Reseller|A reseller builds a Bing Ads application to manage the campaigns of their advertising clients, and is billed directly by Microsoft for valid live clicks. The advertiser does not sign up for Bing Ads credentials, and may pay a fee to the reseller. For relevant best practices, see [Management Model for Resellers](management-model-resellers.md).|

## <a name="accountpermissions"></a>Account Permissions and the Developer Token
The *DeveloperToken* header element must be specified to access Bing Ads services. Obtaining a developer token for API access does not grant permissions to any Bing Ads accounts. A developer token enables programmatic access to the accounts permitted for a user. Each provisioned user is assigned a role, for example Super Admin, and granted permissions to one or more accounts. The same accounts available in the Bing Ads web application are available to the corresponding user programmatically through the API.

There are two types of Bing Ads developer tokens. 

-   Single-user developer token can be used to authenticate solely with one designated user. For example if you are a direct advertiser with one log in email address, then you will only need a single-user token.   

-   Universal developer token (previously known as a multi-user token) can be used to authenticate with any valid user credentials. For example if you are developing an application that will be used by multiple Bing Ads users, then you will likely want to request a universal token instead of getting a single-user token for each user.

Regardless of the developer token type, API access is only enabled for the accounts available to each respective user based on their managed access rights. In other words the developer token does not change read or write access to accounts that the user can manage. The same accounts available in the Bing Ads web application are available to the corresponding user programmatically through the API. 

You can request the token type when requesting API access, or upgrade at a later date through the [Bing Ads Developer Portal](https://developers.bingads.microsoft.com/Account). For information on requesting a developer token, see [Get Started With the Bing Ads API](get-started.md).

## <a name="managingcustomers"></a>Managing Customers
Your application must support one or more customers. 

### <a name="createcustomer"></a>Adding Customers
Only a reseller's aggregator user can sign up customers. For more information on the reseller entity model, see [Management Model for Resellers](management-model-resellers.md).

To sign up a customer, you call the [SignupCustomer](../customer-management-service/signupcustomer.md) operation and pass both [Customer](../customer-management-service/customer.md) and [AdvertiserAccount](../customer-management-service/advertiseraccount.md) objects. The customer object includes the customer's name, the address where the customer is located, the market in which the customer operates, and the industry in which the customer participates. Although it is possible to add multiple customers with the same details, you should use unique customer names so that users can easily distinguish between customers in a user interface.

The account object must specify the name of the account; the type of currency to use to settle the account; and the payment method identifier, which must be set to null. The operation generates an invoice account and sets the payment method identifier to the identifier associated with the reseller's invoice. You are invoiced for all charges incurred by the customers that you manage.

### Getting Customers
To get a list of the customers to which the specified user can access, call the [GetCustomersInfo](../customer-management-service/getcustomersinfo.md) operation. The operation returns an array of objects that contain the name and identifier of each customer that matches the filter criteria that you specified, if any. To get the details of each customer in the list, such as the address or financial status, pass the customer identifier to the [GetCustomer](../customer-management-service/getcustomer.md) operation. You can also search for customers that match a specified filter criteria using the [SearchCustomers](../customer-management-service/searchcustomers.md) operation.

### Updating Customers
Only a super admin or aggregator user can update customers. Because the update operation requires the time stamp of the previous write operation that was performed against the customer, you must first call the [GetCustomer](../customer-management-service/getcustomersinfo.md) operation. The [GetCustomer](../customer-management-service/getcustomersinfo.md) operation returns the customer's data, which includes the time stamp.

After you get the customer object, update the data as appropriate. Because the update operation completely overwrites the existing customer data, the customer data must contain all required data; otherwise, the operation will fail.

To update a customer, call the [UpdateCustomer](../customer-management-service/updatecustomer.md) operation. The call will fail if another user updates the customer data between the time you called the [GetCustomer](../customer-management-service/getcustomersinfo.md) and [UpdateCustomer](../customer-management-service/updatecustomer.md) operations.

You cannot update a customer that has been deleted. Before trying to update the customer, you should check the status of the customer to ensure that it is not inactive.

### Deleting Customers
Only internal account managers can delete customers. If you want to delete a customer that you manage, contact your account manager.

## <a name="managingaccounts"></a>Managing Accounts
Your application must support one or more accounts.

### Adding Accounts
Only internal account managers can add accounts to an existing customer. If you want to add an account to a customer that you manage, contact your account manager.

Resellers can create an account for a managed customer by calling the [SignupCustomer](../customer-management-service/signupcustomer.md) operation. For more information, see [Adding Customers](#createcustomer).

### Getting Accounts
To get a list of the accounts that you own or manage, call the [GetAccountsInfo](../customer-management-service/getaccountsinfo.md) operation. The operation returns an array of objects that contain the name, identifier, and status of each account. To get the details of each account in the list, such as the account's financial status, pass the account identifier to the [GetAccount](../customer-management-service/getaccount.md) operation. You can also search for accounts that match a specified filter criteria using the [SearchAccounts](../customer-management-service/searchaccounts.md) operation.

For code examples that show how to search for accounts that can be managed by the current authenticated user, see [Search Accounts by User Code Example](code-example-search-user-accounts.md).
### Updating Accounts
Only a super admin or aggregator user can update accounts. Because the update operation requires the time stamp of the previous write operation that was performed against the account, you must first call the [GetAccount](../customer-management-service/getaccount.md) operation. The [GetAccount](../customer-management-service/getaccount.md) operation returns the account's data, which includes the time stamp.

After you get the account object, update the data as appropriate. Because the update operation completely overwrites the existing account data, the account data must contain all required data; otherwise, the operation will fail.

To update an account, call the [UpdateAccount](../customer-management-service/updateaccount.md) operation. The call will fail if another user updates the account data between the time you called the *GetAccount* and [UpdateAccount](../customer-management-service/updateaccount.md) operations.

You cannot update an account that has been deleted. Before trying to update the account, you should check the status of the account to ensure that it is not inactive.

### Deleting Accounts
Only a super admin or aggregator user can delete accounts. To delete an account, call the [DeleteAccount](../customer-management-service/deleteaccount.md) operation. Because the delete operation requires the time stamp of the previous write operation that was performed against the account, you must first call the [GetAccount](../customer-management-service/getaccount.md) operation. The [GetAccount](../customer-management-service/getaccount.md) operation returns the account's data, which includes the time stamp.

You cannot delete an account that has already been deleted. You should check the status of the account to ensure that it is not inactive before trying to delete the account.

After deleting the account it will be searchable and show as inactive in the Bing Ads web application. You may or may not choose to surface inactive accounts in your application.

## <a name="managingusers"></a>Managing Users
Your application must support one or more users per customer. For information on using a Microsoft Account to authenticate with Bing Ads services, see [MAuthentication with OAuth](authentication-oauth.md).


### <a name="userroles"></a>User Roles and Available Service Operations
The user role granted by a customer's super admin or the Bing Ads system administrator determines service availability. For example a user with the advertiser campaign manager role may add and update campaigns, but may not create or update users. Unless otherwise noted in the reference content per service operation, the following table describes the service restrictions per user role.

|User Role|Available Services|Provisioning|
|-------------|----------------------|----------------|
|Advertiser Campaign Manager|This role has permissions to view selected accounts and add, edit, or delete campaigns within the selected accounts. The Advertiser Campaign Manager can view payment methods, but cannot manage any billing and payment tasks.<br /><br />Read operations for all services are available.<br /><br />With the [Customer Management service](../customer-management-service/customer-management-service-operations.md), write operations are not available. The only exception is that the Advertiser Campaign Manager can update the *TrackingUrlTemplate* and *AutoTag* values in the *ForwardCompatibilityMap* element of an [AdvertiserAccount](../customer-management-service/advertiseraccount.md) using the [UpdateAccount](../customer-management-service/updateaccount.md) operation. The *Id*, *Name* and *TimeStamp* properties are read-only and required for the update; however, all other properties of the Account object are read-only and will be ignored.|A user with the advertiser campaign manager role can be created by a customer's super admin or aggregator in the Bing Ads web application. For more information on getting and updating users, see [Managing Users](#managingusers).|
|Aggregator|Read and write operations for all services are available, except *DeleteCustomer* and [AddAccount](../customer-management-service/addaccount.md) with the [Customer Management service](../customer-management-service/customer-management-service-operations.md).|The aggregator role is provisioned for resellers by special request through the System Administrator. For more information, see [Management Model for Resellers](management-model-resellers.md) and contact your account manager.|
|Client Viewer|This role has read-only permissions.<br /><br />Read operations for all services are available.|A user with the viewer role can be created by a customer's super admin or aggregator in the Bing Ads web application. For more information on getting and updating users, see [Managing Users](#managingusers).|
|Standard User|This role has permissions to manage campaigns and perform some billing activities on selected accounts. This role cannot add, edit, or delete payment methods; create or delete accounts; or link to or unlink from clients. Standard Users can also be set as the Primary Contact to an account.<br/><br/>Standard Users can manage some users in the accounts they have access to. A Standard User can add or remove other Standard Users, Advertiser Campaign Managers, and Viewers, and view information about all users in the context of the current customer. However, Standard Users cannot add or delete a Super Admin, nor can they edit a Super Admin's role.<br /><br />Read operations for all services are available.<br /><br />With the Customer Billing and Customer Management services, with the exception of [AddInsertionOrder](../customer-billing-service/addinsertionorder.md), [UpdateInsertionOrder](../customer-billing-service/updateinsertionorder.md), and [UpdateAccount](../customer-management-service/updateaccount.md), write operations are not available.|A user with the standard user role can be created by a customer's super admin or aggregator in the Bing Ads web application.|
|Super Admin|This role has full permissions for all accounts. A Super Admin can manage everything related to billing and payments, account details, and other users (including other Super Admins). The Super Admin can specify which accounts other users have access to. When signing up as a new customer, the first user is the Super Admin.<br/><br/>Read operations for all services are available.<br /><br />With the [Customer Management service](../customer-management-service/customer-management-service-operations.md), all operations are available except *AddAccount*, *DeleteCustomer*, *SignupCustomer*, and *UpdateUserRoles*. Write operations for all other services are available.|When signing up as a new Bing Ads customer in the Bing Ads web application, the first user provisioned has the super admin role. Thereafter the super admin may create new users with customer relevant roles. For more information on getting and updating users, see [Managing Users](#managingusers).|

### <a name="multi-user"></a>Multi-User Credentials
Previously one Bing Ads user could only access accounts within a single customer. You could manage accounts across multiple customers as an agency, however, you would have had to create a distinct user per customer. One notable exception is the aggregator user role that can access all of the [reseller's](management-model-resellers.md) child customers.

Now with multi-user credentials it is possible via the Bing Ads web application and Bing Ads Editor to sign in with one email address and manage accounts across different customers. You are also assigned a different user role (Super Admin, Standard User, Advertiser Campaign Manager, or Viewer) per customer that you can access. For example, your multi-user credentials grants you access to Customer A and Customer B. However, your Viewer user role for Customer A limits you from making any changes on the accounts that Belong to Customer A. But as a Super Admin for Customer B, you have full control over that customer's accounts.

Multi-user credentials can be provisioned manually i.e., contact support or your account manager to merge existing user names into a single user name. It is also possible to self-serve via user invitation whether via the Bing Ads web application or [SendUserInvitation](../customer-management-service/senduserinvitation.md) service operation. Previously if you tried to accept an invitation to manage a new customer with existing Bing Ads credentials, you had to choose a new user name. Now you are enabled to accept the invitation with a new or existing user name. If you accept the invitation with existing Bing Ads credentials, you will have multi-user credentials. 

> [!IMPORTANT]
> Bing Ads API Version 11 does not support multi-user credentials across multiple customers. If you authenticate with multi-user credentials, then you will only have the permissions originally granted to that user. If there was never a previous user name i.e., you accepted an invitation to manage another customer's accounts with credentials that you already use in Bing Ads, then you will only be able to use Bing Ads API version 11 to manage the original customer assigned to your user name. Starting with Bing Ads API Version 12 the multi-user credentials can access accounts across multiple customers.  

You might prefer to think of "multi-user" credentials to mean "multiple user roles", since from one perspective you only login with one user name to access multipe customers with varying permissions. By design though, the intention is to reflect that one person's credentials can act as multiple distinct users. In fact one person with multi-user credentials has multiple [User](../customer-management-service/user.md) objects assigned i.e., one [User](../customer-management-service/user.md) object per customer that they can access. 

Let's consider the following user roles and permissions before multi-user consolidation. Each user must log in separately and has different permissions during each logged in session. Likewise via the API each user's access token (see [Authentication with OAuth](authentication-oauth.md)) represents permissions limited to the corresponding user and role. 

|User|Role|Permissions|
|-------------|----------------------|----------------|
|one@contoso.com|Viewer|Customer A - All Accounts|
|two@contoso.com|Super Admin|Customer B - All Accounts|
|three@contoso.com|Viewer|Customer C - Account A|
|four@contoso.com|Standard User|Customer B - All Accounts|

First please note that only one email address per customer can be consolidated, so in this example two@contoso.com and four@contoso.com cannot be consolidated together. Now let's see what happens after the top three users are consolidated under one@contoso.com. 
  * No changes for user four@contoso.com whether via the Bing Ads web application, Bing Ads Editor, or API. 
  * The user one@contoso.com can log in via the Bing Ads web application and Bing Ads Editor. The consolidated users i.e., two@contoso.com and three@contoso.com no longer have permissions to sign in via the Bing Ads web application or Bing Ads Editor. While signed in as one@contoso.com, you can switch context to the customer accounts with corresponding user roles that had previously been assigned to two@contoso.com and three@contoso.com. Although you can access multiple customers signed in with one user's credentials (one@contoso.com), you will need to switch from customer to customer to manage the accounts that are linked with unique user roles. Customers and their related accounts remain distinct. For more details see the Bing Ads help topic [Managing your user name to access multiple accounts](https://help.bingads.microsoft.com/#apex/3/en/app54567/1/en-US/#ext:Customers_Management).
  * With Bing Ads API version 11 there is no change to access before versus after multi-user consolidation. Each of the user's access token (see [Authentication with OAuth](authentication-oauth.md)) represents permissions limited to the corresponding user and role. 
  * Starting with Bing Ads API version 12, the access token for user one@contoso.com will represent permissions to the consolidated list (superset) of accounts. The user role in effect will depend on the customer and account identifiers specified in the service request. Access tokens for two@contoso.com and three@contoso.com will no longer be accepted. 
  * The *UserName* returned via [GetUser](../customer-management-service/getuser.md) and [GetUsersInfo](../customer-management-service/getusersinfo.md) will differ between version 11 and 12 for two@contoso.com and three@contoso.com. In version 11 the *UserName* will be two@contoso.com and three@contoso.com, whereas in version 12 the *UserName* for each of the corresponding user identifiers will be one@contoso.com. In other words the operations will always return whatever user name can authenticate using the respective API version. 

    > [!NOTE]
    > If the multi-user credentials were provisioned through the user invitation work flow i.e., there was never an "old user name" for access to a customer, a system generated GUID will be returned in the *UserName* element in version 11. In version 12 the multi-user email address will be returned. 
  
Also of note is that the Name, Lcid, JobTitle, and ContactInfo user settings for the same person will be automatically synchronized with any updates that occur after user consolidation. The LastModifiedByUserId and LastModifiedTime are also in sync across each returned [User](../customer-management-service/user.md) object, unless you had an old username merged and have not updated any user settings since the consolidation. 
> [!NOTE]
> The TimeStamp differs from the LastModifiedTime. All TimeStamp values are unique per User and when you call [UpdateUser](../customer-management-service/updateuser.md) you must include the corresponding user's timestamps (including the address timestamp).

For example let's say you haven't updated user information for one@contoso.com since prior to consolidation with two@contoso.com and three@contoso.com. After consolidation and until the user settings are updated post-consolidation, you will continue to observe a distinct LastModifiedByUserId and LastModifiedTime within each returned [User](../customer-management-service/user.md) object.

|User Id|Contact Info Id|Permissions|LastModifiedByUserId|
|-------------|----------------------|----------------|----------------|
|123|234|Customer A - All Accounts|123|
|456|567|Customer B - All Accounts|456|
|789|890|Customer C - Account A|789|

Now let's say that one@contoso.com is acting in the context of Customer B and updates their contact information. The updated contact information as well as the same LastModifiedByUserId and LastModifiedTime are now syncrhonized across all returned [User](../customer-management-service/user.md) objects.

|User Id|Contact Info Id|Permissions|LastModifiedByUserId|
|-------------|----------------------|----------------|----------------|
|123|234|Customer A - All Accounts|456|
|456|567|Customer B - All Accounts|456|
|789|890|Customer C - Account A|456|

### Adding Users
Users cannot be created programmatically. With the [SendUserInvitation](../customer-management-service/senduserinvitation.md) service operation, you can send an invitation for someone to manage one or more Bing Ads customer accounts. When you invite a new user, you can specify the role of the user. The role determines the actions that the user can perform in Bing Ads. For more information, see [User Roles and Available Service Operations](#userroles). Once the invitation is accepted, the user's Microsoft account can manage the Bing Ads customer accounts with the user role that you provisioned. 

It is possible to have multiple pending invitations sent to the same email address, which have not yet expired. It is also possible for those invitations to have specified different user roles, for example if you sent an invitation with an incorrect user role and then sent a second invitation with the correct user role. The recipient can accept any of the invitations. The Bing Ads API does not support any operations to delete pending user invitations. After you invite a user, the only way to cancel the invitation is through the Bing Ads web application. You can find both pending and accepted invitations in the Users section of Accounts & Billing.

Since a recipient can accept the invitation and sign into Bing Ads with a Microsoft account different than the invitation email address, you cannot determine with certainty the mapping from [UserInvitation](../customer-management-service/userinvitation.md) to accepted [User](../customer-management-service/user.md). You can search by the invitation ID (returned by [SendUserInvitation](../customer-management-service/senduserinvitation.md)), only to the extent of finding out whether or not the invitation has been accepted or has expired. The [SearchUserInvitations](../customer-management-service/searchuserinvitations.md) operation returns all pending invitations, whether or not they have expired. Accepted invitations are not included in the [SearchUserInvitations](../customer-management-service/searchuserinvitations.md) response.  

### Getting Users
To get a list of the users who can access one or more accounts of a customer, call the [GetUsersInfo](../customer-management-service/getusersinfo.md) operation. The operation returns an array of objects that contains the log in email address and identifier of each user. To get the details of each user in the list, such as their role and account permissions in Bing Ads, call the [GetUser](../customer-management-service/getuser.md) operation. When calling [GetUser](../customer-management-service/getuser.md) if you leave the *UserId* element nil, the response will include details for the current authenticated user as specified by the request header credentials. 

The [GetUser](../customer-management-service/getuser.md) response includes a list of [CustomerRole](../customer-management-service/customerrole.md) objects named *CustomerRoles*. Each returned role is mapped to a specific customer (and specific accounts if applicable).  

```xml
<CustomerRoles xmlns:e328="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
  <e328:CustomerRole>
    <e328:RoleId>ValueHere</e328:RoleId>
    <e328:CustomerId>ValueHere</e328:CustomerId>
    <e328:AccountIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
    <a1:long>ValueHere</a1:long>
    </e328:AccountIds>
  </e328:CustomerRole>
</CustomerRoles>
```

### Updating Users
Only a super admin or aggregator user can update users. Because the update operation requires the time stamp of the previous write operation that was performed against the user, you must first call the [GetUser](../customer-management-service/getuser.md) operation. The [GetUser](../customer-management-service/getuser.md) operation returns the user's data, which includes the time stamp.

After you get the user object, update the data as appropriate. Because the update operation overwrites the existing user data, the user data must contain all required data; otherwise, the operation will fail.

To update a user's information, call the [UpdateUser](../customer-management-service/updateuser.md) operation. The call will fail if another user updates the user data between the time you called the [GetUser](../customer-management-service/getuser.md) and [UpdateUser](../customer-management-service/updateuser.md) operations.

You cannot update a user that has been deleted. Before trying to update the user, you should check the status of the user to ensure that they have not been inactivated or deleted.

Only resellers can update user roles. To update a user's role, call the [UpdateUserRoles](../customer-management-service/updateuserroles.md) operation. For users with an account role, you can add and delete the accounts that the user has access to. For users with a customer role, you can add and delete the customers that the user has access to. You can also change a user from having an account role to having a customer role or vice-versa.

### Deleting Users
Only a super admin or aggregator user can delete users. To delete a user, call the [DeleteUser](../customer-management-service/deleteuser.md) operation. Because the delete operation requires the time stamp of the previous write operation that was performed against the user, you must first call the [GetUser](../customer-management-service/getuser.md) operation. The [GetUser](../customer-management-service/getuser.md) operation returns the user's data, which includes the time stamp.

You cannot delete a user who has already been deleted. You should check the status of the user to ensure that it is not inactive or deleted before trying to delete the user.

You cannot delete a user who is specified as the primary user of one or more accounts. Before you can delete a user who is specified as the primary user of one or more accounts, set the *PrimaryUserId* element of each account to a different user. For more information on updating accounts, see [Managing Accounts](#managingaccounts).

## See Also
[Customer Management service Reference](../customer-management-service/customer-management-service-reference.md)
[Bing Ads Web Service Addresses](web-service-addresses.md)

