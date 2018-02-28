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
# GetUser Service Operation - Customer Management

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

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
      <User xmlns:e17="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e17:ContactInfo d4p1:nil="false">
          <e17:Address d4p1:nil="false">
            <e17:City d4p1:nil="false">ValueHere</e17:City>
            <e17:CountryCode d4p1:nil="false">ValueHere</e17:CountryCode>
            <e17:Id d4p1:nil="false">ValueHere</e17:Id>
            <e17:Line1 d4p1:nil="false">ValueHere</e17:Line1>
            <e17:Line2 d4p1:nil="false">ValueHere</e17:Line2>
            <e17:Line3 d4p1:nil="false">ValueHere</e17:Line3>
            <e17:Line4 d4p1:nil="false">ValueHere</e17:Line4>
            <e17:PostalCode d4p1:nil="false">ValueHere</e17:PostalCode>
            <e17:StateOrProvince d4p1:nil="false">ValueHere</e17:StateOrProvince>
            <e17:TimeStamp d4p1:nil="false">ValueHere</e17:TimeStamp>
          </e17:Address>
          <e17:ContactByPhone d4p1:nil="false">ValueHere</e17:ContactByPhone>
          <e17:ContactByPostalMail d4p1:nil="false">ValueHere</e17:ContactByPostalMail>
          <e17:Email d4p1:nil="false">ValueHere</e17:Email>
          <e17:EmailFormat d4p1:nil="false">ValueHere</e17:EmailFormat>
          <e17:Fax d4p1:nil="false">ValueHere</e17:Fax>
          <e17:HomePhone d4p1:nil="false">ValueHere</e17:HomePhone>
          <e17:Id d4p1:nil="false">ValueHere</e17:Id>
          <e17:Mobile d4p1:nil="false">ValueHere</e17:Mobile>
          <e17:Phone1 d4p1:nil="false">ValueHere</e17:Phone1>
          <e17:Phone2 d4p1:nil="false">ValueHere</e17:Phone2>
        </e17:ContactInfo>
        <e17:CustomerId d4p1:nil="false">ValueHere</e17:CustomerId>
        <e17:Id d4p1:nil="false">ValueHere</e17:Id>
        <e17:JobTitle d4p1:nil="false">ValueHere</e17:JobTitle>
        <e17:LastModifiedByUserId d4p1:nil="false">ValueHere</e17:LastModifiedByUserId>
        <e17:LastModifiedTime d4p1:nil="false">ValueHere</e17:LastModifiedTime>
        <e17:Lcid d4p1:nil="false">ValueHere</e17:Lcid>
        <e17:Name d4p1:nil="false">
          <e17:FirstName d4p1:nil="false">ValueHere</e17:FirstName>
          <e17:LastName d4p1:nil="false">ValueHere</e17:LastName>
          <e17:MiddleInitial d4p1:nil="false">ValueHere</e17:MiddleInitial>
        </e17:Name>
        <e17:Password d4p1:nil="false">ValueHere</e17:Password>
        <e17:SecretAnswer d4p1:nil="false">ValueHere</e17:SecretAnswer>
        <e17:SecretQuestion>ValueHere</e17:SecretQuestion>
        <e17:UserLifeCycleStatus d4p1:nil="false">ValueHere</e17:UserLifeCycleStatus>
        <e17:TimeStamp d4p1:nil="false">ValueHere</e17:TimeStamp>
        <e17:UserName d4p1:nil="false">ValueHere</e17:UserName>
        <e17:IsMigratedToMicrosoftAccount>ValueHere</e17:IsMigratedToMicrosoftAccount>
      </User>
      <CustomerRoles xmlns:e18="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e18:CustomerRole>
          <e18:RoleId>ValueHere</e18:RoleId>
          <e18:CustomerId>ValueHere</e18:CustomerId>
          <e18:AccountIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </e18:AccountIds>
        </e18:CustomerRole>
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

