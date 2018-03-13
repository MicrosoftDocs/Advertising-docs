---
title: UpdateUser Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Updates the details of the specified user.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# UpdateUser Service Operation - Customer Management
Updates the details of the specified user.

## <a name="request"></a>Request Elements
The *UpdateUserRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="user"></a>User|The user object that contains the updated user information.<br /><br />This operation overwrites the existing user data with the contents of the user object that you pass. This operation performs a full update, not a partial update. The *User* object must contain the time stamp value from the last time that the *User* object was written to. To ensure that the time stamp contains the correct value, call the [GetUser](getuser.md) operation. You can then update the user data as appropriate, and call *UpdateUser*.|[User](user.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateUserResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="lastmodifiedtime"></a>LastModifiedTime|The date and time that the user was last updated. The value is in Coordinated Universal Time (UTC).<br/><br/> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">UpdateUser</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <UpdateUserRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <User xmlns:e365="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e365:ContactInfo i:nil="false">
          <e365:Address i:nil="false">
            <e365:City i:nil="false">ValueHere</e365:City>
            <e365:CountryCode i:nil="false">ValueHere</e365:CountryCode>
            <e365:Id i:nil="false">ValueHere</e365:Id>
            <e365:Line1 i:nil="false">ValueHere</e365:Line1>
            <e365:Line2 i:nil="false">ValueHere</e365:Line2>
            <e365:Line3 i:nil="false">ValueHere</e365:Line3>
            <e365:Line4 i:nil="false">ValueHere</e365:Line4>
            <e365:PostalCode i:nil="false">ValueHere</e365:PostalCode>
            <e365:StateOrProvince i:nil="false">ValueHere</e365:StateOrProvince>
            <e365:TimeStamp i:nil="false">ValueHere</e365:TimeStamp>
            <e365:BusinessName i:nil="false">ValueHere</e365:BusinessName>
          </e365:Address>
          <e365:ContactByPhone i:nil="false">ValueHere</e365:ContactByPhone>
          <e365:ContactByPostalMail i:nil="false">ValueHere</e365:ContactByPostalMail>
          <e365:Email i:nil="false">ValueHere</e365:Email>
          <e365:EmailFormat i:nil="false">ValueHere</e365:EmailFormat>
          <e365:Fax i:nil="false">ValueHere</e365:Fax>
          <e365:HomePhone i:nil="false">ValueHere</e365:HomePhone>
          <e365:Id i:nil="false">ValueHere</e365:Id>
          <e365:Mobile i:nil="false">ValueHere</e365:Mobile>
          <e365:Phone1 i:nil="false">ValueHere</e365:Phone1>
          <e365:Phone2 i:nil="false">ValueHere</e365:Phone2>
        </e365:ContactInfo>
        <e365:CustomerId i:nil="false">ValueHere</e365:CustomerId>
        <e365:Id i:nil="false">ValueHere</e365:Id>
        <e365:JobTitle i:nil="false">ValueHere</e365:JobTitle>
        <e365:LastModifiedByUserId i:nil="false">ValueHere</e365:LastModifiedByUserId>
        <e365:LastModifiedTime i:nil="false">ValueHere</e365:LastModifiedTime>
        <e365:Lcid i:nil="false">ValueHere</e365:Lcid>
        <e365:Name i:nil="false">
          <e365:FirstName i:nil="false">ValueHere</e365:FirstName>
          <e365:LastName i:nil="false">ValueHere</e365:LastName>
          <e365:MiddleInitial i:nil="false">ValueHere</e365:MiddleInitial>
        </e365:Name>
        <e365:Password i:nil="false">ValueHere</e365:Password>
        <e365:SecretAnswer i:nil="false">ValueHere</e365:SecretAnswer>
        <e365:SecretQuestion>ValueHere</e365:SecretQuestion>
        <e365:UserLifeCycleStatus i:nil="false">ValueHere</e365:UserLifeCycleStatus>
        <e365:TimeStamp i:nil="false">ValueHere</e365:TimeStamp>
        <e365:UserName i:nil="false">ValueHere</e365:UserName>
        <e365:IsMigratedToMicrosoftAccount>ValueHere</e365:IsMigratedToMicrosoftAccount>
      </User>
    </UpdateUserRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <UpdateUserResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <LastModifiedTime>ValueHere</LastModifiedTime>
    </UpdateUserResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<UpdateUserResponse> UpdateUserAsync(
	User user)
{
	var request = new UpdateUserRequest
	{
		User = user
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.UpdateUserAsync(r), request));
}
```
```java
static UpdateUserResponse updateUser(
	User user) throws RemoteException, Exception
{
	UpdateUserRequest request = new UpdateUserRequest();

	request.setUser(user);

	return CustomerManagementService.getService().updateUser(request);
}
```
```php
static function UpdateUser(
	$user)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new UpdateUserRequest();

	$request->User = $user;

	return $GLOBALS['CustomerManagementProxy']->GetService()->UpdateUser($request);
}
```
```python
response=customermanagement_service.UpdateUser(
	User=User)
```

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

