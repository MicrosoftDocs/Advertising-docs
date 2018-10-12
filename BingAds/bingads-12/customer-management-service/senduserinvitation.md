---
title: SendUserInvitation Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Sends an invitation for  a Microsoft account user to manage one or more Bing Ads customer accounts.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# SendUserInvitation Service Operation - Customer Management
Sends an invitation for  a Microsoft account user to manage one or more Bing Ads customer accounts. When the invitation is accepted, the user's Microsoft account is linked to the specified Bing Ads customer accounts.  

It is possible to have multiple pending invitations sent to the same email address, which have not yet expired. It is also possible for those invitations to have specified different user roles, for example if you sent an invitation with an incorrect user role and then sent a second invitation with the correct user role. The recipient can accept any of the invitations. The Bing Ads API does not support any operations to delete pending user invitations. After you invite a user, the only way to cancel the invitation is through the Bing Ads web application. You can find both pending and accepted invitations in the Users section of Accounts & Billing.

Since a recipient can accept the invitation and sign into Bing Ads with a Microsoft account different than the invitation email address, you cannot determine with certainty the mapping from [UserInvitation](userinvitation.md) to accepted [User](user.md). You can search by the invitation ID (returned by *SendUserInvitations*), only to the extent of finding out whether or not the invitation has been accepted or has expired. The [SearchUserInvitations](searchuserinvitations.md) operation returns all pending invitations, whether or not they have expired. Accepted invitations are not included in the [SearchUserInvitations](searchuserinvitations.md) response.  

After the invitation has been accepted, you can call [GetUsersInfo](getusersinfo.md) and [GetUser](getuser.md) to access the Bing Ads user details. Once again though, since a recipient can accept the invitation and sign into Bing Ads with a Microsoft account different than the invitation email address, you cannot determine with certainty the mapping from [UserInvitation](userinvitation.md) to accepted [User](user.md). With the user ID returned by [GetUsersInfo](getusersinfo.md) or [GetUser](getuser.md), you can call [DeleteUser](deleteuser.md) to remove the user.

> [!IMPORTANT]
> Bing Ads multi-user credentials is now available. Previously if you tried to accept an invitation to manage a new customer with existing Bing Ads credentials, you had to choose a new user name. Now you are enabled to accept the invitation with a new or existing user name. If you accept the invitation with existing Bing Ads credentials, you will have multi-user credentials. It is also possible to contact support directly and have multiple user names consolidated to a single user name i.e., one login will have multi-user permissions. Bing Ads API Version 11 does not support multi-user credentials across multiple customers. If you authenticate with multi-user credentials, then you will only have the permissions originally granted to that user. If there was never a previous user name i.e., you accepted an invitation to manage another customer's accounts with credentials that you already use in Bing Ads, then you will only be able to use Bing Ads API version 11 to manage the original customer assigned to your user name. Starting with Bing Ads API Version 12 the multi-user credentials can access accounts across multiple customers. For more details, see [Multi-User Credentials](../guides/customer-accounts.md#multi-user). 

For more information about user authentication, see [Authentication with OAuth](../guides/authentication-oauth.md).

## <a name="request"></a>Request Elements
The *SendUserInvitationRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="userinvitation"></a>UserInvitation|The user invitation to send.|[UserInvitation](userinvitation.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SendUserInvitationResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="userinvitationid"></a>UserInvitationId|A system-generated identifier for the user invitation that was sent.|**long**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-header) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">SendUserInvitation</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <SendUserInvitationRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <UserInvitation xmlns:e40="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e40:Id>ValueHere</e40:Id>
        <e40:FirstName i:nil="false">ValueHere</e40:FirstName>
        <e40:LastName i:nil="false">ValueHere</e40:LastName>
        <e40:Email i:nil="false">ValueHere</e40:Email>
        <e40:CustomerId>ValueHere</e40:CustomerId>
        <e40:RoleId>ValueHere</e40:RoleId>
        <e40:AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
          <a1:long>ValueHere</a1:long>
        </e40:AccountIds>
        <e40:ExpirationDate>ValueHere</e40:ExpirationDate>
        <e40:Lcid>ValueHere</e40:Lcid>
      </UserInvitation>
    </SendUserInvitationRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
This template was generated by a tool to show the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <SendUserInvitationResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <UserInvitationId>ValueHere</UserInvitationId>
    </SendUserInvitationResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<SendUserInvitationResponse> SendUserInvitationAsync(
	UserInvitation userInvitation)
{
	var request = new SendUserInvitationRequest
	{
		UserInvitation = userInvitation
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.SendUserInvitationAsync(r), request));
}
```
```java
static SendUserInvitationResponse sendUserInvitation(
	UserInvitation userInvitation) throws RemoteException, Exception
{
	SendUserInvitationRequest request = new SendUserInvitationRequest();

	request.setUserInvitation(userInvitation);

	return CustomerManagementService.getService().sendUserInvitation(request);
}
```
```php
static function SendUserInvitation(
	$userInvitation)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new SendUserInvitationRequest();

	$request->UserInvitation = $userInvitation;

	return $GLOBALS['CustomerManagementProxy']->GetService()->SendUserInvitation($request);
}
```
```python
response=customermanagement_service.SendUserInvitation(
	UserInvitation=UserInvitation)
```

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

