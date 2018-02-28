---
title: GetUser Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the details of a user.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# GetUser Service Operation - Customer Management
Gets the details of a user.

## <a name="request"></a>Request Elements
The *GetUserRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="userid"></a>UserId|The identifier of the user to get.<br /><br /> If this element is null or not provided, the response will include details for the authenticated user specified in the request header.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetUserResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customerroles"></a>CustomerRoles|Reserved.|[CustomerRole](customerrole.md) array|
|<a name="user"></a>User|A user object that contains information about the user.|[User](user.md)|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">GetUser</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetUserRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <UserId i:nil="false">ValueHere</UserId>
    </GetUserRequest>
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
    <GetUserResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <User xmlns:e327="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e327:ContactInfo d4p1:nil="false">
          <e327:Address d4p1:nil="false">
            <e327:City d4p1:nil="false">ValueHere</e327:City>
            <e327:CountryCode d4p1:nil="false">ValueHere</e327:CountryCode>
            <e327:Id d4p1:nil="false">ValueHere</e327:Id>
            <e327:Line1 d4p1:nil="false">ValueHere</e327:Line1>
            <e327:Line2 d4p1:nil="false">ValueHere</e327:Line2>
            <e327:Line3 d4p1:nil="false">ValueHere</e327:Line3>
            <e327:Line4 d4p1:nil="false">ValueHere</e327:Line4>
            <e327:PostalCode d4p1:nil="false">ValueHere</e327:PostalCode>
            <e327:StateOrProvince d4p1:nil="false">ValueHere</e327:StateOrProvince>
            <e327:TimeStamp d4p1:nil="false">ValueHere</e327:TimeStamp>
          </e327:Address>
          <e327:ContactByPhone d4p1:nil="false">ValueHere</e327:ContactByPhone>
          <e327:ContactByPostalMail d4p1:nil="false">ValueHere</e327:ContactByPostalMail>
          <e327:Email d4p1:nil="false">ValueHere</e327:Email>
          <e327:EmailFormat d4p1:nil="false">ValueHere</e327:EmailFormat>
          <e327:Fax d4p1:nil="false">ValueHere</e327:Fax>
          <e327:HomePhone d4p1:nil="false">ValueHere</e327:HomePhone>
          <e327:Id d4p1:nil="false">ValueHere</e327:Id>
          <e327:Mobile d4p1:nil="false">ValueHere</e327:Mobile>
          <e327:Phone1 d4p1:nil="false">ValueHere</e327:Phone1>
          <e327:Phone2 d4p1:nil="false">ValueHere</e327:Phone2>
        </e327:ContactInfo>
        <e327:CustomerId d4p1:nil="false">ValueHere</e327:CustomerId>
        <e327:Id d4p1:nil="false">ValueHere</e327:Id>
        <e327:JobTitle d4p1:nil="false">ValueHere</e327:JobTitle>
        <e327:LastModifiedByUserId d4p1:nil="false">ValueHere</e327:LastModifiedByUserId>
        <e327:LastModifiedTime d4p1:nil="false">ValueHere</e327:LastModifiedTime>
        <e327:Lcid d4p1:nil="false">ValueHere</e327:Lcid>
        <e327:Name d4p1:nil="false">
          <e327:FirstName d4p1:nil="false">ValueHere</e327:FirstName>
          <e327:LastName d4p1:nil="false">ValueHere</e327:LastName>
          <e327:MiddleInitial d4p1:nil="false">ValueHere</e327:MiddleInitial>
        </e327:Name>
        <e327:Password d4p1:nil="false">ValueHere</e327:Password>
        <e327:SecretAnswer d4p1:nil="false">ValueHere</e327:SecretAnswer>
        <e327:SecretQuestion>ValueHere</e327:SecretQuestion>
        <e327:UserLifeCycleStatus d4p1:nil="false">ValueHere</e327:UserLifeCycleStatus>
        <e327:TimeStamp d4p1:nil="false">ValueHere</e327:TimeStamp>
        <e327:UserName d4p1:nil="false">ValueHere</e327:UserName>
        <e327:IsMigratedToMicrosoftAccount>ValueHere</e327:IsMigratedToMicrosoftAccount>
      </User>
      <CustomerRoles xmlns:e328="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e328:CustomerRole>
          <e328:RoleId>ValueHere</e328:RoleId>
          <e328:CustomerId>ValueHere</e328:CustomerId>
          <e328:AccountIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </e328:AccountIds>
        </e328:CustomerRole>
      </CustomerRoles>
    </GetUserResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetUserResponse> GetUserAsync(
	long? userId)
{
	var request = new GetUserRequest
	{
		UserId = userId
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.GetUserAsync(r), request));
}
```
```java
static GetUserResponse getUser(
	java.lang.Long userId) throws RemoteException, Exception
{
	GetUserRequest request = new GetUserRequest();

	request.setUserId(userId);

	return CustomerManagementService.getService().getUser(request);
}
```
```php
static function GetUser(
	$userId)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new GetUserRequest();

	$request->UserId = $userId;

	return $GLOBALS['CustomerManagementProxy']->GetService()->GetUser($request);
}
```
```python
response=customermanagement_service.GetUser(
	UserId=UserId)
```

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

