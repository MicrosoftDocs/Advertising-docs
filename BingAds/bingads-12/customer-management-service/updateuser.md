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
      <User xmlns:e914="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e914:ContactInfo i:nil="false">
          <e914:Address i:nil="false">
            <e914:City i:nil="false">ValueHere</e914:City>
            <e914:CountryCode i:nil="false">ValueHere</e914:CountryCode>
            <e914:Id i:nil="false">ValueHere</e914:Id>
            <e914:Line1 i:nil="false">ValueHere</e914:Line1>
            <e914:Line2 i:nil="false">ValueHere</e914:Line2>
            <e914:Line3 i:nil="false">ValueHere</e914:Line3>
            <e914:Line4 i:nil="false">ValueHere</e914:Line4>
            <e914:PostalCode i:nil="false">ValueHere</e914:PostalCode>
            <e914:StateOrProvince i:nil="false">ValueHere</e914:StateOrProvince>
            <e914:TimeStamp i:nil="false">ValueHere</e914:TimeStamp>
            <e914:BusinessName i:nil="false">ValueHere</e914:BusinessName>
          </e914:Address>
          <e914:ContactByPhone i:nil="false">ValueHere</e914:ContactByPhone>
          <e914:ContactByPostalMail i:nil="false">ValueHere</e914:ContactByPostalMail>
          <e914:Email i:nil="false">ValueHere</e914:Email>
          <e914:EmailFormat i:nil="false">ValueHere</e914:EmailFormat>
          <e914:Fax i:nil="false">ValueHere</e914:Fax>
          <e914:HomePhone i:nil="false">ValueHere</e914:HomePhone>
          <e914:Id i:nil="false">ValueHere</e914:Id>
          <e914:Mobile i:nil="false">ValueHere</e914:Mobile>
          <e914:Phone1 i:nil="false">ValueHere</e914:Phone1>
          <e914:Phone2 i:nil="false">ValueHere</e914:Phone2>
        </e914:ContactInfo>
        <e914:CustomerId i:nil="false">ValueHere</e914:CustomerId>
        <e914:Id i:nil="false">ValueHere</e914:Id>
        <e914:JobTitle i:nil="false">ValueHere</e914:JobTitle>
        <e914:LastModifiedByUserId i:nil="false">ValueHere</e914:LastModifiedByUserId>
        <e914:LastModifiedTime i:nil="false">ValueHere</e914:LastModifiedTime>
        <e914:Lcid i:nil="false">ValueHere</e914:Lcid>
        <e914:Name i:nil="false">
          <e914:FirstName i:nil="false">ValueHere</e914:FirstName>
          <e914:LastName i:nil="false">ValueHere</e914:LastName>
          <e914:MiddleInitial i:nil="false">ValueHere</e914:MiddleInitial>
        </e914:Name>
        <e914:Password i:nil="false">ValueHere</e914:Password>
        <e914:SecretAnswer i:nil="false">ValueHere</e914:SecretAnswer>
        <e914:SecretQuestion>ValueHere</e914:SecretQuestion>
        <e914:UserLifeCycleStatus i:nil="false">ValueHere</e914:UserLifeCycleStatus>
        <e914:TimeStamp i:nil="false">ValueHere</e914:TimeStamp>
        <e914:UserName i:nil="false">ValueHere</e914:UserName>
        <ForwardCompatibilityMap xmlns:e915="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e915:KeyValuePairOfstringstring>
            <e915:key i:nil="false">ValueHere</e915:key>
            <e915:value i:nil="false">ValueHere</e915:value>
          </e915:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
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

