---
title: UpdateUser Service Operation
ms.service: bing-ads-customer-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# UpdateUser Service Operation
Updates the details of the specified user.

## <a name="request"></a>Request Elements
The *UpdateUserRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="user"></a>User|The user object that contains the updated user information.<br /><br />This operation overwrites the existing user data with the contents of the user object that you pass. This operation performs a full update, not a partial update. The *User* object must contain the time stamp value from the last time that the *User* object was written to. To ensure that the time stamp contains the correct value, call the [GetUser](../customer-management/getuser.md) operation. You can then update the user data as appropriate, and call *UpdateUser*.|[User](user.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateUserResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="lastmodifiedtime"></a>LastModifiedTime|The date and time that the user was last updated. The value is in Coordinated Universal Time (UTC).<br/><br/>**Note:** The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">UpdateUser</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <UpdateUserRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <User xmlns:e50="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e50:ContactInfo i:nil="false">
          <e50:Address i:nil="false">
            <e50:City i:nil="false">ValueHere</e50:City>
            <e50:CountryCode i:nil="false">ValueHere</e50:CountryCode>
            <e50:Id i:nil="false">ValueHere</e50:Id>
            <e50:Line1 i:nil="false">ValueHere</e50:Line1>
            <e50:Line2 i:nil="false">ValueHere</e50:Line2>
            <e50:Line3 i:nil="false">ValueHere</e50:Line3>
            <e50:Line4 i:nil="false">ValueHere</e50:Line4>
            <e50:PostalCode i:nil="false">ValueHere</e50:PostalCode>
            <e50:StateOrProvince i:nil="false">ValueHere</e50:StateOrProvince>
            <e50:TimeStamp i:nil="false">ValueHere</e50:TimeStamp>
          </e50:Address>
          <e50:ContactByPhone i:nil="false">ValueHere</e50:ContactByPhone>
          <e50:ContactByPostalMail i:nil="false">ValueHere</e50:ContactByPostalMail>
          <e50:Email i:nil="false">ValueHere</e50:Email>
          <e50:EmailFormat i:nil="false">ValueHere</e50:EmailFormat>
          <e50:Fax i:nil="false">ValueHere</e50:Fax>
          <e50:HomePhone i:nil="false">ValueHere</e50:HomePhone>
          <e50:Id i:nil="false">ValueHere</e50:Id>
          <e50:Mobile i:nil="false">ValueHere</e50:Mobile>
          <e50:Phone1 i:nil="false">ValueHere</e50:Phone1>
          <e50:Phone2 i:nil="false">ValueHere</e50:Phone2>
        </e50:ContactInfo>
        <e50:CustomerAppScope i:nil="false">ValueHere</e50:CustomerAppScope>
        <e50:CustomerId i:nil="false">ValueHere</e50:CustomerId>
        <e50:Id i:nil="false">ValueHere</e50:Id>
        <e50:JobTitle i:nil="false">ValueHere</e50:JobTitle>
        <e50:LastModifiedByUserId i:nil="false">ValueHere</e50:LastModifiedByUserId>
        <e50:LastModifiedTime i:nil="false">ValueHere</e50:LastModifiedTime>
        <e50:Lcid i:nil="false">ValueHere</e50:Lcid>
        <e50:Name i:nil="false">
          <e50:FirstName i:nil="false">ValueHere</e50:FirstName>
          <e50:LastName i:nil="false">ValueHere</e50:LastName>
          <e50:MiddleInitial i:nil="false">ValueHere</e50:MiddleInitial>
        </e50:Name>
        <e50:Password i:nil="false">ValueHere</e50:Password>
        <e50:SecretAnswer i:nil="false">ValueHere</e50:SecretAnswer>
        <e50:SecretQuestion>ValueHere</e50:SecretQuestion>
        <e50:UserLifeCycleStatus i:nil="false">ValueHere</e50:UserLifeCycleStatus>
        <e50:TimeStamp i:nil="false">ValueHere</e50:TimeStamp>
        <e50:UserName i:nil="false">ValueHere</e50:UserName>
        <e50:IsMigratedToMicrosoftAccount>ValueHere</e50:IsMigratedToMicrosoftAccount>
      </User>
    </UpdateUserRequest>
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
    <UpdateUserResponse xmlns="https://bingads.microsoft.com/Customer/v11">
      <LastModifiedTime>ValueHere</LastModifiedTime>
    </UpdateUserResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
protected async Task<UpdateUserResponse> UpdateUserAsync(
	User user)
{
	var request = new UpdateUserRequest
	{
		User = user
	};

	return (await CustomerManagement.CallAsync((s, r) => s.UpdateUserAsync(r), request));
}
```
```java
static UpdateUserResponse updateUser(
	User user)
{
	UpdateUserRequest request = new UpdateUserRequest();

	request.setUser(user);

	return CustomerManagement.getService().updateUser(request);
}
```
```php
static function UpdateUser(
	$user)

	$updateUserRequest = new UpdateUserRequest();

	$request->User = $user;

	return $CustomerManagementProxy->GetService()->UpdateUser($request);
}
```
```python
response=customermanagement.UpdateUser(
	User=UserHere
)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

