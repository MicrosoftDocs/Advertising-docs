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
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

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
|<a name="customerroles"></a>CustomerRoles|The list of roles that a user has for each customer or list of accounts.<br/><br/>At minimum one list item will be returned. If a user's credentials can access multiple customers, then one [CustomerRole](customerrole.md) object per customer will be returned.<br/><br/>You can view all of your own roles across all customers; however, you will only see the roles of other users as it pertains to customers that you can access. For example let's say you@contoso.com and another-user@contoso.com can access Customer A. The other user might also have access to Customer B and C; however when you call this operation with their user identifier, you will only see their role under Customer A. When another-user@contoso.com calls this operation with their own credentials, the operation would return three [CustomerRole](customerrole.md) objects.|[CustomerRole](customerrole.md) array|
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
      <User xmlns:e328="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e328:ContactInfo d4p1:nil="false">
          <e328:Address d4p1:nil="false">
            <e328:City d4p1:nil="false">ValueHere</e328:City>
            <e328:CountryCode d4p1:nil="false">ValueHere</e328:CountryCode>
            <e328:Id d4p1:nil="false">ValueHere</e328:Id>
            <e328:Line1 d4p1:nil="false">ValueHere</e328:Line1>
            <e328:Line2 d4p1:nil="false">ValueHere</e328:Line2>
            <e328:Line3 d4p1:nil="false">ValueHere</e328:Line3>
            <e328:Line4 d4p1:nil="false">ValueHere</e328:Line4>
            <e328:PostalCode d4p1:nil="false">ValueHere</e328:PostalCode>
            <e328:StateOrProvince d4p1:nil="false">ValueHere</e328:StateOrProvince>
            <e328:TimeStamp d4p1:nil="false">ValueHere</e328:TimeStamp>
            <e328:BusinessName d4p1:nil="false">ValueHere</e328:BusinessName>
          </e328:Address>
          <e328:ContactByPhone d4p1:nil="false">ValueHere</e328:ContactByPhone>
          <e328:ContactByPostalMail d4p1:nil="false">ValueHere</e328:ContactByPostalMail>
          <e328:Email d4p1:nil="false">ValueHere</e328:Email>
          <e328:EmailFormat d4p1:nil="false">ValueHere</e328:EmailFormat>
          <e328:Fax d4p1:nil="false">ValueHere</e328:Fax>
          <e328:HomePhone d4p1:nil="false">ValueHere</e328:HomePhone>
          <e328:Id d4p1:nil="false">ValueHere</e328:Id>
          <e328:Mobile d4p1:nil="false">ValueHere</e328:Mobile>
          <e328:Phone1 d4p1:nil="false">ValueHere</e328:Phone1>
          <e328:Phone2 d4p1:nil="false">ValueHere</e328:Phone2>
        </e328:ContactInfo>
        <e328:CustomerId d4p1:nil="false">ValueHere</e328:CustomerId>
        <e328:Id d4p1:nil="false">ValueHere</e328:Id>
        <e328:JobTitle d4p1:nil="false">ValueHere</e328:JobTitle>
        <e328:LastModifiedByUserId d4p1:nil="false">ValueHere</e328:LastModifiedByUserId>
        <e328:LastModifiedTime d4p1:nil="false">ValueHere</e328:LastModifiedTime>
        <e328:Lcid d4p1:nil="false">ValueHere</e328:Lcid>
        <e328:Name d4p1:nil="false">
          <e328:FirstName d4p1:nil="false">ValueHere</e328:FirstName>
          <e328:LastName d4p1:nil="false">ValueHere</e328:LastName>
          <e328:MiddleInitial d4p1:nil="false">ValueHere</e328:MiddleInitial>
        </e328:Name>
        <e328:Password d4p1:nil="false">ValueHere</e328:Password>
        <e328:SecretAnswer d4p1:nil="false">ValueHere</e328:SecretAnswer>
        <e328:SecretQuestion>ValueHere</e328:SecretQuestion>
        <e328:UserLifeCycleStatus d4p1:nil="false">ValueHere</e328:UserLifeCycleStatus>
        <e328:TimeStamp d4p1:nil="false">ValueHere</e328:TimeStamp>
        <e328:UserName d4p1:nil="false">ValueHere</e328:UserName>
        <e328:IsMigratedToMicrosoftAccount>ValueHere</e328:IsMigratedToMicrosoftAccount>
      </User>
      <CustomerRoles xmlns:e329="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e329:CustomerRole>
          <e329:RoleId>ValueHere</e329:RoleId>
          <e329:CustomerId>ValueHere</e329:CustomerId>
          <e329:AccountIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </e329:AccountIds>
        </e329:CustomerRole>
      </CustomerRoles>
    </GetUserResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
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

