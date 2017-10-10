---
title: GetUser Service Operation
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the details of a user.
---
# GetUser Service Operation
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
|<a name="accounts"></a>Accounts|An array of identifiers of the accounts to which the user has access permissions. If the *Roles* element contains an account role and the *Accounts* element contains a 0 (zero)-length array, it indicates that the user has access permissions to all of the customer's accounts.|**long**|
|<a name="customers"></a>Customers|An array of identifiers of the customers to which the user has access permissions. If the *Roles* element contains a customer role and the *Customers* element contains a 0 (zero)-length array, it indicates that the user has access permissions to all customers.|**long**|
|<a name="roles"></a>Roles|An array of roles that determines the permissions that the user has to manage the customer or account data.<br /><br />Possible values include the following:<br />16 - The user has the **Advertiser Campaign Manager** role.<br />33 - The user has the **Aggregator** role.<br />41 - The user has the **Super Admin** role.<br />100 - The user has the **ClientViewer** role.<br />203 - The user has the **Standard** role.<br /><br />For more information, see [User Roles and Available Service Operations](~/guides/customer-accounts.md#userroles).<br /><br />**Important**: The list above provides examples of possible return values. Other  values might be returned. Deprecated or internal roles can be included in the response.|**int**|
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
      <User xmlns:e626="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e626:ContactInfo d4p1:nil="false">
          <e626:Address d4p1:nil="false">
            <e626:City d4p1:nil="false">ValueHere</e626:City>
            <e626:CountryCode d4p1:nil="false">ValueHere</e626:CountryCode>
            <e626:Id d4p1:nil="false">ValueHere</e626:Id>
            <e626:Line1 d4p1:nil="false">ValueHere</e626:Line1>
            <e626:Line2 d4p1:nil="false">ValueHere</e626:Line2>
            <e626:Line3 d4p1:nil="false">ValueHere</e626:Line3>
            <e626:Line4 d4p1:nil="false">ValueHere</e626:Line4>
            <e626:PostalCode d4p1:nil="false">ValueHere</e626:PostalCode>
            <e626:StateOrProvince d4p1:nil="false">ValueHere</e626:StateOrProvince>
            <e626:TimeStamp d4p1:nil="false">ValueHere</e626:TimeStamp>
          </e626:Address>
          <e626:ContactByPhone d4p1:nil="false">ValueHere</e626:ContactByPhone>
          <e626:ContactByPostalMail d4p1:nil="false">ValueHere</e626:ContactByPostalMail>
          <e626:Email d4p1:nil="false">ValueHere</e626:Email>
          <e626:EmailFormat d4p1:nil="false">ValueHere</e626:EmailFormat>
          <e626:Fax d4p1:nil="false">ValueHere</e626:Fax>
          <e626:HomePhone d4p1:nil="false">ValueHere</e626:HomePhone>
          <e626:Id d4p1:nil="false">ValueHere</e626:Id>
          <e626:Mobile d4p1:nil="false">ValueHere</e626:Mobile>
          <e626:Phone1 d4p1:nil="false">ValueHere</e626:Phone1>
          <e626:Phone2 d4p1:nil="false">ValueHere</e626:Phone2>
        </e626:ContactInfo>
        <e626:CustomerAppScope d4p1:nil="false">ValueHere</e626:CustomerAppScope>
        <e626:CustomerId d4p1:nil="false">ValueHere</e626:CustomerId>
        <e626:Id d4p1:nil="false">ValueHere</e626:Id>
        <e626:JobTitle d4p1:nil="false">ValueHere</e626:JobTitle>
        <e626:LastModifiedByUserId d4p1:nil="false">ValueHere</e626:LastModifiedByUserId>
        <e626:LastModifiedTime d4p1:nil="false">ValueHere</e626:LastModifiedTime>
        <e626:Lcid d4p1:nil="false">ValueHere</e626:Lcid>
        <e626:Name d4p1:nil="false">
          <e626:FirstName d4p1:nil="false">ValueHere</e626:FirstName>
          <e626:LastName d4p1:nil="false">ValueHere</e626:LastName>
          <e626:MiddleInitial d4p1:nil="false">ValueHere</e626:MiddleInitial>
        </e626:Name>
        <e626:Password d4p1:nil="false">ValueHere</e626:Password>
        <e626:SecretAnswer d4p1:nil="false">ValueHere</e626:SecretAnswer>
        <e626:SecretQuestion>ValueHere</e626:SecretQuestion>
        <e626:UserLifeCycleStatus d4p1:nil="false">ValueHere</e626:UserLifeCycleStatus>
        <e626:TimeStamp d4p1:nil="false">ValueHere</e626:TimeStamp>
        <e626:UserName d4p1:nil="false">ValueHere</e626:UserName>
        <e626:IsMigratedToMicrosoftAccount>ValueHere</e626:IsMigratedToMicrosoftAccount>
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
	long userId)
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

	$getUserRequest = new GetUserRequest();

	$request->UserId = $userId;

	return $CustomerManagementProxy->GetService()->GetUser($request);
}
```
```python
response=customermanagement.GetUser(
	UserId=UserIdHere
)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

