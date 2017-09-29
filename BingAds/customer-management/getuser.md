---
title: GetUser Service Operation
ms.service: bing-ads-customer-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# GetUser Service Operation
Gets the details of a user.

## <a name="request"></a>Request Elements
The *GetUserRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="userid"></a>UserId|The identifier of the user to get.<br /><br />**Note**: If this element is null or not provided, the response will include details for the authenticated user specified in the request header.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetUserResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="user"></a>User|A user object that contains information about the user.|[User](user.md)|
|<a name="roles"></a>Roles|An array of roles that determines the permissions that the user has to manage the customer or account data.<br /><br />Possible values include the following:<br />16 - The user has the **Advertiser Campaign Manager** role.<br />33 - The user has the **Aggregator** role.<br />41 - The user has the **Super Admin** role.<br />100 - The user has the **ClientViewer** role.<br />203 - The user has the **Standard** role.<br /><br />For more information, see [User Roles and Available Service Operations](~/guides/customer-accounts.md#userroles).<br /><br />**Important**: The list above provides examples of possible return values. Other  values might be returned. Deprecated or internal roles can be included in the response.|**int**|
|<a name="accounts"></a>Accounts|An array of identifiers of the accounts to which the user has access permissions. If the *Roles* element contains an account role and the *Accounts* element contains a 0 (zero)-length array, it indicates that the user has access permissions to all of the customer?s accounts.|**long**|
|<a name="customers"></a>Customers|An array of identifiers of the customers to which the user has access permissions. If the *Roles* element contains a customer role and the *Customers* element contains a 0 (zero)-length array, it indicates that the user has access permissions to all customers.|**long**|

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
      <User xmlns:e420="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e420:ContactInfo d4p1:nil="false">
          <e420:Address d4p1:nil="false">
            <e420:City d4p1:nil="false">ValueHere</e420:City>
            <e420:CountryCode d4p1:nil="false">ValueHere</e420:CountryCode>
            <e420:Id d4p1:nil="false">ValueHere</e420:Id>
            <e420:Line1 d4p1:nil="false">ValueHere</e420:Line1>
            <e420:Line2 d4p1:nil="false">ValueHere</e420:Line2>
            <e420:Line3 d4p1:nil="false">ValueHere</e420:Line3>
            <e420:Line4 d4p1:nil="false">ValueHere</e420:Line4>
            <e420:PostalCode d4p1:nil="false">ValueHere</e420:PostalCode>
            <e420:StateOrProvince d4p1:nil="false">ValueHere</e420:StateOrProvince>
            <e420:TimeStamp d4p1:nil="false">ValueHere</e420:TimeStamp>
          </e420:Address>
          <e420:ContactByPhone d4p1:nil="false">ValueHere</e420:ContactByPhone>
          <e420:ContactByPostalMail d4p1:nil="false">ValueHere</e420:ContactByPostalMail>
          <e420:Email d4p1:nil="false">ValueHere</e420:Email>
          <e420:EmailFormat d4p1:nil="false">ValueHere</e420:EmailFormat>
          <e420:Fax d4p1:nil="false">ValueHere</e420:Fax>
          <e420:HomePhone d4p1:nil="false">ValueHere</e420:HomePhone>
          <e420:Id d4p1:nil="false">ValueHere</e420:Id>
          <e420:Mobile d4p1:nil="false">ValueHere</e420:Mobile>
          <e420:Phone1 d4p1:nil="false">ValueHere</e420:Phone1>
          <e420:Phone2 d4p1:nil="false">ValueHere</e420:Phone2>
        </e420:ContactInfo>
        <e420:CustomerAppScope d4p1:nil="false">ValueHere</e420:CustomerAppScope>
        <e420:CustomerId d4p1:nil="false">ValueHere</e420:CustomerId>
        <e420:Id d4p1:nil="false">ValueHere</e420:Id>
        <e420:JobTitle d4p1:nil="false">ValueHere</e420:JobTitle>
        <e420:LastModifiedByUserId d4p1:nil="false">ValueHere</e420:LastModifiedByUserId>
        <e420:LastModifiedTime d4p1:nil="false">ValueHere</e420:LastModifiedTime>
        <e420:Lcid d4p1:nil="false">ValueHere</e420:Lcid>
        <e420:Name d4p1:nil="false">
          <e420:FirstName d4p1:nil="false">ValueHere</e420:FirstName>
          <e420:LastName d4p1:nil="false">ValueHere</e420:LastName>
          <e420:MiddleInitial d4p1:nil="false">ValueHere</e420:MiddleInitial>
        </e420:Name>
        <e420:Password d4p1:nil="false">ValueHere</e420:Password>
        <e420:SecretAnswer d4p1:nil="false">ValueHere</e420:SecretAnswer>
        <e420:SecretQuestion>ValueHere</e420:SecretQuestion>
        <e420:UserLifeCycleStatus d4p1:nil="false">ValueHere</e420:UserLifeCycleStatus>
        <e420:TimeStamp d4p1:nil="false">ValueHere</e420:TimeStamp>
        <e420:UserName d4p1:nil="false">ValueHere</e420:UserName>
        <e420:IsMigratedToMicrosoftAccount>ValueHere</e420:IsMigratedToMicrosoftAccount>
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
```csharp
protected async Task<GetUserResponse> GetUserAsync(
	long userId)
{
	var request = new GetUserRequest
	{
		UserId = userId
	};

	return (await CustomerManagement.CallAsync((s, r) => s.GetUserAsync(r), request));
}
```
```java
static GetUserResponse getUser(
	long userId)
{
	GetUserRequest request = new GetUserRequest();

	request.setUserId(userId);

	return CustomerManagement.getService().getUser(request);
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

