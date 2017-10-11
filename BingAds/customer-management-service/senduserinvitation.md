---
title: SendUserInvitation Service Operation
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Sends an invitation for  a Microsoft account user to manage one or more Bing Ads customer accounts.
---
# SendUserInvitation Service Operation
Sends an invitation for  a Microsoft account user to manage one or more Bing Ads customer accounts. When the invitation is accepted, the user's Microsoft account is linked to the specified Bing Ads customer accounts.  

It is possible to have multiple pending invitations sent to the same email address, which have not yet expired. It is also possible for those invitations to have specified different user roles, for example if you sent an invitation with an incorrect user role and then sent a second invitation with the correct user role. The recipient can accept any of the invitations. The Bing Ads API does not support any operations to delete pending user invitations. After you invite a user, the only way to cancel the invitation is through the Bing Ads web application. You can find both pending and accepted invitations in the Users section of Accounts & Billing.

Since a recipient can accept the invitation and sign into Bing Ads with a Microsoft account different than the invitation email address, you cannot determine with certainty the mapping from [UserInvitation](../customer-management-service/userinvitation.md) to accepted [User](../customer-management-service/user.md). You can search by the invitation ID (returned by *SendUserInvitations*), only to the extent of finding out whether or not the invitation has been accepted or has expired. The [SearchUserInvitations](../customer-management-service/searchuserinvitations.md) operation returns all pending invitations, whether or not they have expired. Accepted invitations are not included in the [SearchUserInvitations](../customer-management-service/searchuserinvitations.md) response.  

After the invitation has been accepted, you can call [GetUsersInfo](../customer-management-service/getusersinfo.md) and [GetUser](../customer-management-service/getuser.md) to access the Bing Ads user details. Once again though, since a recipient can accept the invitation and sign into Bing Ads with a Microsoft account different than the invitation email address, you cannot determine with certainty the mapping from [UserInvitation](../customer-management-service/userinvitation.md) to accepted [User](../customer-management-service/user.md). With the user ID returned by [GetUsersInfo](../customer-management-service/getusersinfo.md) or [GetUser](../customer-management-service/getuser.md), you can call [DeleteUser](../customer-management-service/deleteuser.md) to remove the user.

For more information about user authentication, see [Authentication with OAuth](~/guides/authentication-oauth.md).

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
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">SendUserInvitation</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SendUserInvitationRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <UserInvitation xmlns:e35="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e35:Id>ValueHere</e35:Id>
        <e35:FirstName i:nil="false">ValueHere</e35:FirstName>
        <e35:LastName i:nil="false">ValueHere</e35:LastName>
        <e35:Email i:nil="false">ValueHere</e35:Email>
        <e35:CustomerId>ValueHere</e35:CustomerId>
        <e35:Role>ValueHere</e35:Role>
        <e35:AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
          <a1:long>ValueHere</a1:long>
        </e35:AccountIds>
        <e35:ExpirationDate>ValueHere</e35:ExpirationDate>
        <e35:Lcid>ValueHere</e35:Lcid>
      </UserInvitation>
    </SendUserInvitationRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <SendUserInvitationResponse xmlns="https://bingads.microsoft.com/Customer/v11">
      <UserInvitationId>ValueHere</UserInvitationId>
    </SendUserInvitationResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
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

	$sendUserInvitationRequest = new SendUserInvitationRequest();

	$request->UserInvitation = $userInvitation;

	return $CustomerManagementProxy->GetService()->SendUserInvitation($request);
}
```
```python
response=customermanagement.SendUserInvitation(
	UserInvitation=UserInvitationHere
)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

