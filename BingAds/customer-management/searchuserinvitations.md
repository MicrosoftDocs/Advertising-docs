---
title: SearchUserInvitations Service Operation
ms.service: bing-ads-customer-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# SearchUserInvitations Service Operation
Searches for user invitations that match a specified criteria.

This operation returns all pending invitations, whether or not they have expired. Accepted invitations are not included in the response.  

## <a name="request"></a>Request Elements
The *SearchUserInvitationsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="predicates"></a>Predicates|Determines the request conditions. This operation's response will include user invitations that match all of the specified predicates.<br /><br />**Note**: You may specify only one predicate.<br /><br />For a list of supported *Field* and *Operator* elements of a *Predicate* object for this service operation, see [Predicate Field and Operator](#predicates).|[Predicate](predicate.md) array|

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
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">SearchUserInvitations</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SearchUserInvitationsRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <Predicates xmlns:e33="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e33:Predicate>
          <e33:Field i:nil="false">ValueHere</e33:Field>
          <e33:Operator>ValueHere</e33:Operator>
          <e33:Value i:nil="false">ValueHere</e33:Value>
        </e33:Predicate>
      </Predicates>
    </SearchUserInvitationsRequest>
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
    <SearchUserInvitationsResponse xmlns="https://bingads.microsoft.com/Customer/v11">
      <UserInvitations xmlns:e34="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e34:UserInvitation>
          <e34:Id>ValueHere</e34:Id>
          <e34:FirstName d4p1:nil="false">ValueHere</e34:FirstName>
          <e34:LastName d4p1:nil="false">ValueHere</e34:LastName>
          <e34:Email d4p1:nil="false">ValueHere</e34:Email>
          <e34:CustomerId>ValueHere</e34:CustomerId>
          <e34:Role>ValueHere</e34:Role>
          <e34:AccountIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </e34:AccountIds>
          <e34:ExpirationDate>ValueHere</e34:ExpirationDate>
          <e34:Lcid>ValueHere</e34:Lcid>
        </e34:UserInvitation>
      </UserInvitations>
    </SearchUserInvitationsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
protected async Task<SearchUserInvitationsResponse> SearchUserInvitationsAsync(
	IList<Predicate> predicates)
{
	var request = new SearchUserInvitationsRequest
	{
		Predicates = predicates
	};

	return (await CustomerManagement.CallAsync((s, r) => s.SearchUserInvitationsAsync(r), request));
}
```
```java
static SearchUserInvitationsResponse searchUserInvitations(
	ArrayOfPredicate predicates)
{
	SearchUserInvitationsRequest request = new SearchUserInvitationsRequest();

	request.setPredicates(predicates);

	return CustomerManagement.getService().searchUserInvitations(request);
}
```
```php
static function SearchUserInvitations(
	$predicates)

	$searchUserInvitationsRequest = new SearchUserInvitationsRequest();

	$request->Predicates = $predicates;

	return $CustomerManagementProxy->GetService()->SearchUserInvitations($request);
}
```
```python
response=customermanagement.SearchUserInvitations(
	Predicates=PredicatesHere
)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

