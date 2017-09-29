---
title: SearchClientLinks Service Operation
ms.service: bing-ads-customer-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# SearchClientLinks Service Operation
This feature is not supported in sandbox.Searches for the client links for the customer of the current authenticated user, filtered by the search criteria. The operation returns the most recent link for each unique combination of agency customer and client account. For more information about the client link lifecycle, see [Link to Client Accounts](~/guides/management-model-agencies.md#clientlink).

If your user is within a client customer that has one or more accounts managed by an agency, then you may search one at a time for individual accounts that were or are eligible to be linked. To search by individual account, set the predicate field to ClientAccountId and set the predicate value to the account identifier that you want to find.

The role of the user calling this operation must be Super Admin. For more information, see [User Roles and Available Service Operations](~/guides/customer-accounts.md#userroles).

## <a name="request"></a>Request Elements
The *SearchClientLinksRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="predicates"></a>Predicates|Determines the request conditions. This operation's response will include client links that match all of the specified predicates.<br /><br />**Note**: You can specify either one or two predicates.<br /><br />For a list of supported *Field* and *Operator* elements of a *Predicate* object for this service operation, see [Predicate Field and Operator](#predicates).|[Predicate](predicate.md) array|
|<a name="ordering"></a>Ordering|Determines the order of results.<br /><br />**Note**: If specified, you should only include one *OrderBy* element in the list. Additional elements are not supported and will be ignored by the service.<br /><br />For this service operation, the following values are supported in the *Field* element of a *OrderBy* object.<br /><br />*Id* - The order is determined by the *ClientAccountId* element of the returned [ClientLink](../customer-management/clientlink.md).<br /><br />*Name* - The order is determined by the *Name* element of the returned [ClientLink](../customer-management/clientlink.md).<br /><br />*Number* - The order is determined by the *ManagingCustomerNumber* element of the returned [ClientLink](../customer-management/clientlink.md).|[OrderBy](orderby.md) array|
|<a name="pageinfo"></a>PageInfo|Determines the index and size of  results per page.|[Paging](paging.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SearchClientLinksResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="clientlinks"></a>ClientLinks|The list of client link invitations.|[ClientLink](clientlink.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">SearchClientLinks</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SearchClientLinksRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <Predicates xmlns:e428="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e428:Predicate>
          <e428:Field i:nil="false">ValueHere</e428:Field>
          <e428:Operator>ValueHere</e428:Operator>
          <e428:Value i:nil="false">ValueHere</e428:Value>
        </e428:Predicate>
      </Predicates>
      <Ordering xmlns:e429="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e429:OrderBy>
          <e429:Field>ValueHere</e429:Field>
          <e429:Order>ValueHere</e429:Order>
        </e429:OrderBy>
      </Ordering>
      <PageInfo xmlns:e430="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e430:Index>ValueHere</e430:Index>
        <e430:Size>ValueHere</e430:Size>
      </PageInfo>
    </SearchClientLinksRequest>
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
    <SearchClientLinksResponse xmlns="https://bingads.microsoft.com/Customer/v11">
      <ClientLinks xmlns:e431="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e431:ClientLink>
          <e431:ClientAccountId d4p1:nil="false">ValueHere</e431:ClientAccountId>
          <e431:ClientAccountNumber d4p1:nil="false">ValueHere</e431:ClientAccountNumber>
          <e431:ManagingCustomerId d4p1:nil="false">ValueHere</e431:ManagingCustomerId>
          <e431:ManagingCustomerNumber d4p1:nil="false">ValueHere</e431:ManagingCustomerNumber>
          <e431:Note d4p1:nil="false">ValueHere</e431:Note>
          <e431:Name d4p1:nil="false">ValueHere</e431:Name>
          <e431:InviterEmail d4p1:nil="false">ValueHere</e431:InviterEmail>
          <e431:InviterName d4p1:nil="false">ValueHere</e431:InviterName>
          <e431:InviterPhone d4p1:nil="false">ValueHere</e431:InviterPhone>
          <e431:IsBillToClient>ValueHere</e431:IsBillToClient>
          <e431:StartDate d4p1:nil="false">ValueHere</e431:StartDate>
          <e431:Status d4p1:nil="false">ValueHere</e431:Status>
          <e431:SuppressNotification>ValueHere</e431:SuppressNotification>
          <e431:LastModifiedDateTime>ValueHere</e431:LastModifiedDateTime>
          <e431:LastModifiedByUserId>ValueHere</e431:LastModifiedByUserId>
          <e431:Timestamp d4p1:nil="false">ValueHere</e431:Timestamp>
          <ForwardCompatibilityMap xmlns:e432="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e432:KeyValuePairOfstringstring>
              <e432:key d4p1:nil="false">ValueHere</e432:key>
              <e432:value d4p1:nil="false">ValueHere</e432:value>
            </e432:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
        </e431:ClientLink>
      </ClientLinks>
    </SearchClientLinksResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
```csharp
protected async Task<SearchClientLinksResponse> SearchClientLinksAsync(
	IList<Predicate> predicates,
	IList<OrderBy> ordering,
	Paging pageInfo)
{
	var request = new SearchClientLinksRequest
	{
		Predicates = predicates,
		Ordering = ordering,
		PageInfo = pageInfo
	};

	return (await CustomerManagement.CallAsync((s, r) => s.SearchClientLinksAsync(r), request));
}
```
```java
static SearchClientLinksResponse searchClientLinks(
	ArrayOfPredicate predicates,
	ArrayOfOrderBy ordering,
	Paging pageInfo)
{
	SearchClientLinksRequest request = new SearchClientLinksRequest();

	request.setPredicates(predicates);
	request.setOrdering(ordering);
	request.setPageInfo(pageInfo);

	return CustomerManagement.getService().searchClientLinks(request);
}
```
```php
static function SearchClientLinks(
	$predicates,
	$ordering,
	$pageInfo)

	$searchClientLinksRequest = new SearchClientLinksRequest();

	$request->Predicates = $predicates;
	$request->Ordering = $ordering;
	$request->PageInfo = $pageInfo;

	return $CustomerManagementProxy->GetService()->SearchClientLinks($request);
}
```
```python
response=customermanagement.SearchClientLinks(
	Predicates=PredicatesHere,
	Ordering=OrderingHere,
	PageInfo=PageInfoHere
)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

