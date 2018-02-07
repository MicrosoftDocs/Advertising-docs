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
|<a name="accounts"></a>Accounts|An array of identifiers of the accounts to which the user has access permissions. If the *Roles* element contains an account role and the *Accounts* element contains a 0 (zero)-length array, it indicates that the user has access permissions to all of the customer's accounts.|**long** array|
|<a name="customers"></a>Customers|An array of identifiers of the customers to which the user has access permissions. If the *Roles* element contains a customer role and the *Customers* element contains a 0 (zero)-length array, it indicates that the user has access permissions to all customers.|**long** array|
|<a name="roles"></a>Roles|An array of roles that determines the permissions that the user has to manage the customer or account data.<br /><br />Possible values include the following:<br />16 - The user has the **Advertiser Campaign Manager** role.<br />33 - The user has the **Aggregator** role.<br />41 - The user has the **Super Admin** role.<br />100 - The user has the **ClientViewer** role.<br />203 - The user has the **Standard** role.<br /><br />For more information, see [User Roles and Available Service Operations](~/guides/customer-accounts.md#userroles).<br /><br />**Important**: The list above provides examples of possible return values. Other  values might be returned. Deprecated or internal roles can be included in the response.|**int** array|
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
      <User xmlns:e685="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e685:ContactInfo d4p1:nil="false">
          <e685:Address d4p1:nil="false">
            <e685:City d4p1:nil="false">ValueHere</e685:City>
            <e685:CountryCode d4p1:nil="false">ValueHere</e685:CountryCode>
            <e685:Id d4p1:nil="false">ValueHere</e685:Id>
            <e685:Line1 d4p1:nil="false">ValueHere</e685:Line1>
            <e685:Line2 d4p1:nil="false">ValueHere</e685:Line2>
            <e685:Line3 d4p1:nil="false">ValueHere</e685:Line3>
            <e685:Line4 d4p1:nil="false">ValueHere</e685:Line4>
            <e685:PostalCode d4p1:nil="false">ValueHere</e685:PostalCode>
            <e685:StateOrProvince d4p1:nil="false">ValueHere</e685:StateOrProvince>
            <e685:TimeStamp d4p1:nil="false">ValueHere</e685:TimeStamp>
          </e685:Address>
          <e685:ContactByPhone d4p1:nil="false">ValueHere</e685:ContactByPhone>
          <e685:ContactByPostalMail d4p1:nil="false">ValueHere</e685:ContactByPostalMail>
          <e685:Email d4p1:nil="false">ValueHere</e685:Email>
          <e685:EmailFormat d4p1:nil="false">ValueHere</e685:EmailFormat>
          <e685:Fax d4p1:nil="false">ValueHere</e685:Fax>
          <e685:HomePhone d4p1:nil="false">ValueHere</e685:HomePhone>
          <e685:Id d4p1:nil="false">ValueHere</e685:Id>
          <e685:Mobile d4p1:nil="false">ValueHere</e685:Mobile>
          <e685:Phone1 d4p1:nil="false">ValueHere</e685:Phone1>
          <e685:Phone2 d4p1:nil="false">ValueHere</e685:Phone2>
        </e685:ContactInfo>
        <e685:CustomerId d4p1:nil="false">ValueHere</e685:CustomerId>
        <e685:Id d4p1:nil="false">ValueHere</e685:Id>
        <e685:JobTitle d4p1:nil="false">ValueHere</e685:JobTitle>
        <e685:LastModifiedByUserId d4p1:nil="false">ValueHere</e685:LastModifiedByUserId>
        <e685:LastModifiedTime d4p1:nil="false">ValueHere</e685:LastModifiedTime>
        <e685:Lcid d4p1:nil="false">ValueHere</e685:Lcid>
        <e685:Name d4p1:nil="false">
          <e685:FirstName d4p1:nil="false">ValueHere</e685:FirstName>
          <e685:LastName d4p1:nil="false">ValueHere</e685:LastName>
          <e685:MiddleInitial d4p1:nil="false">ValueHere</e685:MiddleInitial>
        </e685:Name>
        <e685:Password d4p1:nil="false">ValueHere</e685:Password>
        <e685:SecretAnswer d4p1:nil="false">ValueHere</e685:SecretAnswer>
        <e685:SecretQuestion>ValueHere</e685:SecretQuestion>
        <e685:UserLifeCycleStatus d4p1:nil="false">ValueHere</e685:UserLifeCycleStatus>
        <e685:TimeStamp d4p1:nil="false">ValueHere</e685:TimeStamp>
        <e685:UserName d4p1:nil="false">ValueHere</e685:UserName>
        <e685:IsMigratedToMicrosoftAccount>ValueHere</e685:IsMigratedToMicrosoftAccount>
      </User>
      <Roles d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:int>ValueHere</a1:int>
      </Roles>
      <Accounts d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:long>ValueHere</a1:long>
      </Accounts>
      <Customers d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:long>ValueHere</a1:long>
      </Customers>
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

