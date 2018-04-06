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
      <User xmlns:e876="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e876:ContactInfo d4p1:nil="false">
          <e876:Address d4p1:nil="false">
            <e876:City d4p1:nil="false">ValueHere</e876:City>
            <e876:CountryCode d4p1:nil="false">ValueHere</e876:CountryCode>
            <e876:Id d4p1:nil="false">ValueHere</e876:Id>
            <e876:Line1 d4p1:nil="false">ValueHere</e876:Line1>
            <e876:Line2 d4p1:nil="false">ValueHere</e876:Line2>
            <e876:Line3 d4p1:nil="false">ValueHere</e876:Line3>
            <e876:Line4 d4p1:nil="false">ValueHere</e876:Line4>
            <e876:PostalCode d4p1:nil="false">ValueHere</e876:PostalCode>
            <e876:StateOrProvince d4p1:nil="false">ValueHere</e876:StateOrProvince>
            <e876:TimeStamp d4p1:nil="false">ValueHere</e876:TimeStamp>
            <e876:BusinessName d4p1:nil="false">ValueHere</e876:BusinessName>
          </e876:Address>
          <e876:ContactByPhone d4p1:nil="false">ValueHere</e876:ContactByPhone>
          <e876:ContactByPostalMail d4p1:nil="false">ValueHere</e876:ContactByPostalMail>
          <e876:Email d4p1:nil="false">ValueHere</e876:Email>
          <e876:EmailFormat d4p1:nil="false">ValueHere</e876:EmailFormat>
          <e876:Fax d4p1:nil="false">ValueHere</e876:Fax>
          <e876:HomePhone d4p1:nil="false">ValueHere</e876:HomePhone>
          <e876:Id d4p1:nil="false">ValueHere</e876:Id>
          <e876:Mobile d4p1:nil="false">ValueHere</e876:Mobile>
          <e876:Phone1 d4p1:nil="false">ValueHere</e876:Phone1>
          <e876:Phone2 d4p1:nil="false">ValueHere</e876:Phone2>
        </e876:ContactInfo>
        <e876:CustomerId d4p1:nil="false">ValueHere</e876:CustomerId>
        <e876:Id d4p1:nil="false">ValueHere</e876:Id>
        <e876:JobTitle d4p1:nil="false">ValueHere</e876:JobTitle>
        <e876:LastModifiedByUserId d4p1:nil="false">ValueHere</e876:LastModifiedByUserId>
        <e876:LastModifiedTime d4p1:nil="false">ValueHere</e876:LastModifiedTime>
        <e876:Lcid d4p1:nil="false">ValueHere</e876:Lcid>
        <e876:Name d4p1:nil="false">
          <e876:FirstName d4p1:nil="false">ValueHere</e876:FirstName>
          <e876:LastName d4p1:nil="false">ValueHere</e876:LastName>
          <e876:MiddleInitial d4p1:nil="false">ValueHere</e876:MiddleInitial>
        </e876:Name>
        <e876:Password d4p1:nil="false">ValueHere</e876:Password>
        <e876:SecretAnswer d4p1:nil="false">ValueHere</e876:SecretAnswer>
        <e876:SecretQuestion>ValueHere</e876:SecretQuestion>
        <e876:UserLifeCycleStatus d4p1:nil="false">ValueHere</e876:UserLifeCycleStatus>
        <e876:TimeStamp d4p1:nil="false">ValueHere</e876:TimeStamp>
        <e876:UserName d4p1:nil="false">ValueHere</e876:UserName>
        <ForwardCompatibilityMap xmlns:e877="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e877:KeyValuePairOfstringstring>
            <e877:key d4p1:nil="false">ValueHere</e877:key>
            <e877:value d4p1:nil="false">ValueHere</e877:value>
          </e877:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
      </User>
      <CustomerRoles xmlns:e878="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e878:CustomerRole>
          <e878:RoleId>ValueHere</e878:RoleId>
          <e878:CustomerId>ValueHere</e878:CustomerId>
          <e878:AccountIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </e878:AccountIds>
        </e878:CustomerRole>
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

