---
title: SearchClientLinks Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: This feature is not supported in sandbox.Searches for the client links for the customer of the current authenticated user, filtered by the search criteria.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# SearchClientLinks Service Operation - Customer Management

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

This feature is not supported in sandbox.Searches for the client links for the customer of the current authenticated user, filtered by the search criteria. The operation returns the most recent link for each unique combination of agency customer and client account. For more information about the client link lifecycle, see [Link to Client Accounts](../guides/management-model-agencies.md#clientlink).

If your user is within a client customer that has one or more accounts managed by an agency, then you may search one at a time for individual accounts that were or are eligible to be linked. To search by individual account, set the predicate field to ClientAccountId and set the predicate value to the account identifier that you want to find.

The role of the user calling this operation must be Super Admin. For more information, see [User Roles and Available Service Operations](../guides/customer-accounts.md#userroles).

## <a name="request"></a>Request Elements
The *SearchClientLinksRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ordering"></a>Ordering|Determines the order of results.<br /><br /> If specified, you should only include one *OrderBy* element in the list. Additional elements are not supported and will be ignored by the service.<br /><br />For this service operation, the following values are supported in the *Field* element of a *OrderBy* object.<br /><br />*Id* - The order is determined by the *ClientAccountId* element of the returned [ClientLink](../customer-management-service/clientlink.md).<br /><br />*Name* - The order is determined by the *Name* element of the returned [ClientLink](../customer-management-service/clientlink.md).<br /><br />*Number* - The order is determined by the *ManagingCustomerNumber* element of the returned [ClientLink](../customer-management-service/clientlink.md).|[OrderBy](orderby.md) array|
|<a name="pageinfo"></a>PageInfo|Determines the index and size of  results per page.|[Paging](paging.md)|
|<a name="predicates"></a>Predicates|Determines the request conditions. This operation's response will include client links that match all of the specified predicates.<br /><br /> You can specify either one or two predicates.<br /><br />For a list of supported *Field* and *Operator* elements of a [Predicate](predicate.md) object for this service operation, see [Predicate Remarks](predicate.md#remarks).|[Predicate](predicate.md) array|

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
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">SearchClientLinks</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SearchClientLinksRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <Predicates xmlns:e26="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e26:Predicate>
          <e26:Field i:nil="false">ValueHere</e26:Field>
          <e26:Operator>ValueHere</e26:Operator>
          <e26:Value i:nil="false">ValueHere</e26:Value>
        </e26:Predicate>
      </Predicates>
      <Ordering xmlns:e27="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e27:OrderBy>
          <e27:Field>ValueHere</e27:Field>
          <e27:Order>ValueHere</e27:Order>
        </e27:OrderBy>
      </Ordering>
      <PageInfo xmlns:e28="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e28:Index>ValueHere</e28:Index>
        <e28:Size>ValueHere</e28:Size>
      </PageInfo>
    </SearchClientLinksRequest>
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
    <SearchClientLinksResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <ClientLinks xmlns:e29="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e29:ClientLink>
          <e29:ClientAccountId d4p1:nil="false">ValueHere</e29:ClientAccountId>
          <e29:ClientAccountNumber d4p1:nil="false">ValueHere</e29:ClientAccountNumber>
          <e29:ManagingCustomerId d4p1:nil="false">ValueHere</e29:ManagingCustomerId>
          <e29:ManagingCustomerNumber d4p1:nil="false">ValueHere</e29:ManagingCustomerNumber>
          <e29:Note d4p1:nil="false">ValueHere</e29:Note>
          <e29:Name d4p1:nil="false">ValueHere</e29:Name>
          <e29:InviterEmail d4p1:nil="false">ValueHere</e29:InviterEmail>
          <e29:InviterName d4p1:nil="false">ValueHere</e29:InviterName>
          <e29:InviterPhone d4p1:nil="false">ValueHere</e29:InviterPhone>
          <e29:IsBillToClient>ValueHere</e29:IsBillToClient>
          <e29:StartDate d4p1:nil="false">ValueHere</e29:StartDate>
          <e29:Status d4p1:nil="false">ValueHere</e29:Status>
          <e29:SuppressNotification>ValueHere</e29:SuppressNotification>
          <e29:LastModifiedDateTime>ValueHere</e29:LastModifiedDateTime>
          <e29:LastModifiedByUserId>ValueHere</e29:LastModifiedByUserId>
          <e29:Timestamp d4p1:nil="false">ValueHere</e29:Timestamp>
          <ForwardCompatibilityMap xmlns:e30="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e30:KeyValuePairOfstringstring>
              <e30:key d4p1:nil="false">ValueHere</e30:key>
              <e30:value d4p1:nil="false">ValueHere</e30:value>
            </e30:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
        </e29:ClientLink>
      </ClientLinks>
    </SearchClientLinksResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<SearchClientLinksResponse> SearchClientLinksAsync(
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

	return (await CustomerManagementService.CallAsync((s, r) => s.SearchClientLinksAsync(r), request));
}
```
```java
static SearchClientLinksResponse searchClientLinks(
	ArrayOfPredicate predicates,
	ArrayOfOrderBy ordering,
	Paging pageInfo) throws RemoteException, Exception
{
	SearchClientLinksRequest request = new SearchClientLinksRequest();

	request.setPredicates(predicates);
	request.setOrdering(ordering);
	request.setPageInfo(pageInfo);

	return CustomerManagementService.getService().searchClientLinks(request);
}
```
```php
static function SearchClientLinks(
	$predicates,
	$ordering,
	$pageInfo)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new SearchClientLinksRequest();

	$request->Predicates = $predicates;
	$request->Ordering = $ordering;
	$request->PageInfo = $pageInfo;

	return $GLOBALS['CustomerManagementProxy']->GetService()->SearchClientLinks($request);
}
```
```python
response=customermanagement_service.SearchClientLinks(
	Predicates=Predicates,
	Ordering=Ordering,
	PageInfo=PageInfo)
```

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

