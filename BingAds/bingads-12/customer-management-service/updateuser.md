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
      <User xmlns:e1270="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e1270:ContactInfo i:nil="false">
          <e1270:Address i:nil="false">
            <e1270:City i:nil="false">ValueHere</e1270:City>
            <e1270:CountryCode i:nil="false">ValueHere</e1270:CountryCode>
            <e1270:Id i:nil="false">ValueHere</e1270:Id>
            <e1270:Line1 i:nil="false">ValueHere</e1270:Line1>
            <e1270:Line2 i:nil="false">ValueHere</e1270:Line2>
            <e1270:Line3 i:nil="false">ValueHere</e1270:Line3>
            <e1270:Line4 i:nil="false">ValueHere</e1270:Line4>
            <e1270:PostalCode i:nil="false">ValueHere</e1270:PostalCode>
            <e1270:StateOrProvince i:nil="false">ValueHere</e1270:StateOrProvince>
            <e1270:TimeStamp i:nil="false">ValueHere</e1270:TimeStamp>
          </e1270:Address>
          <e1270:ContactByPhone i:nil="false">ValueHere</e1270:ContactByPhone>
          <e1270:ContactByPostalMail i:nil="false">ValueHere</e1270:ContactByPostalMail>
          <e1270:Email i:nil="false">ValueHere</e1270:Email>
          <e1270:EmailFormat i:nil="false">ValueHere</e1270:EmailFormat>
          <e1270:Fax i:nil="false">ValueHere</e1270:Fax>
          <e1270:HomePhone i:nil="false">ValueHere</e1270:HomePhone>
          <e1270:Id i:nil="false">ValueHere</e1270:Id>
          <e1270:Mobile i:nil="false">ValueHere</e1270:Mobile>
          <e1270:Phone1 i:nil="false">ValueHere</e1270:Phone1>
          <e1270:Phone2 i:nil="false">ValueHere</e1270:Phone2>
        </e1270:ContactInfo>
        <e1270:CustomerId i:nil="false">ValueHere</e1270:CustomerId>
        <e1270:Id i:nil="false">ValueHere</e1270:Id>
        <e1270:JobTitle i:nil="false">ValueHere</e1270:JobTitle>
        <e1270:LastModifiedByUserId i:nil="false">ValueHere</e1270:LastModifiedByUserId>
        <e1270:LastModifiedTime i:nil="false">ValueHere</e1270:LastModifiedTime>
        <e1270:Lcid i:nil="false">ValueHere</e1270:Lcid>
        <e1270:Name i:nil="false">
          <e1270:FirstName i:nil="false">ValueHere</e1270:FirstName>
          <e1270:LastName i:nil="false">ValueHere</e1270:LastName>
          <e1270:MiddleInitial i:nil="false">ValueHere</e1270:MiddleInitial>
        </e1270:Name>
        <e1270:Password i:nil="false">ValueHere</e1270:Password>
        <e1270:SecretAnswer i:nil="false">ValueHere</e1270:SecretAnswer>
        <e1270:SecretQuestion>ValueHere</e1270:SecretQuestion>
        <e1270:UserLifeCycleStatus i:nil="false">ValueHere</e1270:UserLifeCycleStatus>
        <e1270:TimeStamp i:nil="false">ValueHere</e1270:TimeStamp>
        <e1270:UserName i:nil="false">ValueHere</e1270:UserName>
        <e1270:IsMigratedToMicrosoftAccount>ValueHere</e1270:IsMigratedToMicrosoftAccount>
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

