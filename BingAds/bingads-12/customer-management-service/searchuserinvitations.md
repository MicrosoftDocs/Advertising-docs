---
title: SearchUserInvitations Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Searches for user invitations that match a specified criteria.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# SearchUserInvitations Service Operation - Customer Management
Searches for user invitations that match a specified criteria.

This operation returns all pending invitations, whether or not they have expired. Accepted invitations are not included in the response.  

## <a name="request"></a>Request Elements
The *SearchUserInvitationsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="predicates"></a>Predicates|Determines the request conditions. This operation's response will include user invitations that match all of the specified predicates.<br /><br /> You may specify only one predicate.<br /><br />For a list of supported *Field* and *Operator* elements of a [Predicate](predicate.md) object for this service operation, see [Predicate Remarks](predicate.md#remarks).|[Predicate](predicate.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SearchUserInvitationsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="userinvitations"></a>UserInvitations|A  list of user invitations that meet the specified criteria.|[UserInvitation](userinvitation.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">SearchUserInvitations</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SearchUserInvitationsRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <Predicates xmlns:e1253="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e1253:Predicate>
          <e1253:Field i:nil="false">ValueHere</e1253:Field>
          <e1253:Operator>ValueHere</e1253:Operator>
          <e1253:Value i:nil="false">ValueHere</e1253:Value>
        </e1253:Predicate>
      </Predicates>
    </SearchUserInvitationsRequest>
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
    <SearchUserInvitationsResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <UserInvitations xmlns:e1254="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1254:UserInvitation>
          <e1254:Id>ValueHere</e1254:Id>
          <e1254:FirstName d4p1:nil="false">ValueHere</e1254:FirstName>
          <e1254:LastName d4p1:nil="false">ValueHere</e1254:LastName>
          <e1254:Email d4p1:nil="false">ValueHere</e1254:Email>
          <e1254:CustomerId>ValueHere</e1254:CustomerId>
          <e1254:RoleId>ValueHere</e1254:RoleId>
          <e1254:AccountIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </e1254:AccountIds>
          <e1254:ExpirationDate>ValueHere</e1254:ExpirationDate>
          <e1254:Lcid>ValueHere</e1254:Lcid>
        </e1254:UserInvitation>
      </UserInvitations>
    </SearchUserInvitationsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<SearchUserInvitationsResponse> SearchUserInvitationsAsync(
	IList<Predicate> predicates)
{
	var request = new SearchUserInvitationsRequest
	{
		Predicates = predicates
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.SearchUserInvitationsAsync(r), request));
}
```
```java
static SearchUserInvitationsResponse searchUserInvitations(
	ArrayOfPredicate predicates) throws RemoteException, Exception
{
	SearchUserInvitationsRequest request = new SearchUserInvitationsRequest();

	request.setPredicates(predicates);

	return CustomerManagementService.getService().searchUserInvitations(request);
}
```
```php
static function SearchUserInvitations(
	$predicates)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new SearchUserInvitationsRequest();

	$request->Predicates = $predicates;

	return $GLOBALS['CustomerManagementProxy']->GetService()->SearchUserInvitations($request);
}
```
```python
response=customermanagement_service.SearchUserInvitations(
	Predicates=Predicates)
```

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

