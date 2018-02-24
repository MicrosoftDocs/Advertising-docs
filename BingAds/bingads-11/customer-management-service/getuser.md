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
|<a name="roles"></a>Roles|An array of roles that determines the permissions that the user has to manage the customer or account data.<br /><br />Possible values include the following:<br />16 - The user has the **Advertiser Campaign Manager** role.<br />33 - The user has the **Aggregator** role.<br />41 - The user has the **Super Admin** role.<br />100 - The user has the **ClientViewer** role.<br />203 - The user has the **Standard** role.<br /><br />For more information, see [User Roles and Available Service Operations](bingads/guides/customer-accounts.md#userroles).<br /><br />**Important**: The list above provides examples of possible return values. Other  values might be returned. Deprecated or internal roles can be included in the response.|**int** array|
|<a name="user"></a>User|A user object that contains information about the user.|[User](user.md)|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">GetUser</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetUserRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <UserId i:nil="false">ValueHere</UserId>
    </GetUserRequest>
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
    <GetUserResponse xmlns="https://bingads.microsoft.com/Customer/v11">
      <User xmlns:e320="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e320:ContactInfo d4p1:nil="false">
          <e320:Address d4p1:nil="false">
            <e320:City d4p1:nil="false">ValueHere</e320:City>
            <e320:CountryCode d4p1:nil="false">ValueHere</e320:CountryCode>
            <e320:Id d4p1:nil="false">ValueHere</e320:Id>
            <e320:Line1 d4p1:nil="false">ValueHere</e320:Line1>
            <e320:Line2 d4p1:nil="false">ValueHere</e320:Line2>
            <e320:Line3 d4p1:nil="false">ValueHere</e320:Line3>
            <e320:Line4 d4p1:nil="false">ValueHere</e320:Line4>
            <e320:PostalCode d4p1:nil="false">ValueHere</e320:PostalCode>
            <e320:StateOrProvince d4p1:nil="false">ValueHere</e320:StateOrProvince>
            <e320:TimeStamp d4p1:nil="false">ValueHere</e320:TimeStamp>
          </e320:Address>
          <e320:ContactByPhone d4p1:nil="false">ValueHere</e320:ContactByPhone>
          <e320:ContactByPostalMail d4p1:nil="false">ValueHere</e320:ContactByPostalMail>
          <e320:Email d4p1:nil="false">ValueHere</e320:Email>
          <e320:EmailFormat d4p1:nil="false">ValueHere</e320:EmailFormat>
          <e320:Fax d4p1:nil="false">ValueHere</e320:Fax>
          <e320:HomePhone d4p1:nil="false">ValueHere</e320:HomePhone>
          <e320:Id d4p1:nil="false">ValueHere</e320:Id>
          <e320:Mobile d4p1:nil="false">ValueHere</e320:Mobile>
          <e320:Phone1 d4p1:nil="false">ValueHere</e320:Phone1>
          <e320:Phone2 d4p1:nil="false">ValueHere</e320:Phone2>
        </e320:ContactInfo>
        <e320:CustomerAppScope d4p1:nil="false">ValueHere</e320:CustomerAppScope>
        <e320:CustomerId d4p1:nil="false">ValueHere</e320:CustomerId>
        <e320:Id d4p1:nil="false">ValueHere</e320:Id>
        <e320:JobTitle d4p1:nil="false">ValueHere</e320:JobTitle>
        <e320:LastModifiedByUserId d4p1:nil="false">ValueHere</e320:LastModifiedByUserId>
        <e320:LastModifiedTime d4p1:nil="false">ValueHere</e320:LastModifiedTime>
        <e320:Lcid d4p1:nil="false">ValueHere</e320:Lcid>
        <e320:Name d4p1:nil="false">
          <e320:FirstName d4p1:nil="false">ValueHere</e320:FirstName>
          <e320:LastName d4p1:nil="false">ValueHere</e320:LastName>
          <e320:MiddleInitial d4p1:nil="false">ValueHere</e320:MiddleInitial>
        </e320:Name>
        <e320:Password d4p1:nil="false">ValueHere</e320:Password>
        <e320:SecretAnswer d4p1:nil="false">ValueHere</e320:SecretAnswer>
        <e320:SecretQuestion>ValueHere</e320:SecretQuestion>
        <e320:UserLifeCycleStatus d4p1:nil="false">ValueHere</e320:UserLifeCycleStatus>
        <e320:TimeStamp d4p1:nil="false">ValueHere</e320:TimeStamp>
        <e320:UserName d4p1:nil="false">ValueHere</e320:UserName>
        <e320:IsMigratedToMicrosoftAccount>ValueHere</e320:IsMigratedToMicrosoftAccount>
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
The example syntax can be used with [Bing Ads SDKs](bingads/guides/client-libraries.md). See [Bing Ads Code Examples](bingads/guides/code-examples.md) for more examples.
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
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11  

