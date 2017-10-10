---
title: SearchInsertionOrders Service Operation
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Searches for insertion orders that match a specified criteria.
---
# SearchInsertionOrders Service Operation
Searches for insertion orders that match a specified criteria.

## <a name="request"></a>Request Elements
The *SearchInsertionOrdersRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ordering"></a>Ordering|Determines the order of results by the specified property of an account.<br /><br /> You should only specify one *OrderBy* element in the array. Additional elements are not supported and will be ignored by the service.<br /><br />For this service operation, the following values are supported in the *Field* element of a *OrderBy* object.<br /><br />*Id* - The order is determined by the *InsertionOrderId*element of the returned [InsertionOrder](../customer-billing-service/insertionorder.md).<br /><br />*Name* - The order is determined by the *Name* element of the returned [InsertionOrder](../customer-billing-service/insertionorder.md).|[OrderBy](orderby.md) array|
|<a name="pageinfo"></a>PageInfo|Determines the index and size of  results per page.|[Paging](paging.md)|
|<a name="predicates"></a>Predicates|Determines the request conditions. This operation's response will include accounts that match all of the specified predicates.<br /><br /> You may specify up to 6 predicates, and one of the predicate fields must be AccountId. You may use the StartDate and EndDate predicate fields twice each to specify start and end date ranges, and otherwise may only use each predicate field once.<br /><br />For a list of supported *Field* and *Operator* elements of a *Predicate* object for this service operation, see [Predicate Field and Operator](#predicates).|[Predicate](predicate.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SearchInsertionOrdersResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="insertionorders"></a>InsertionOrders|A  list of insertion orders that meet the specified criteria.|[InsertionOrder](insertionorder.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Billing/v11">
    <Action mustUnderstand="1">SearchInsertionOrders</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SearchInsertionOrdersRequest xmlns="https://bingads.microsoft.com/Billing/v11">
      <Predicates xmlns:e667="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e667:Predicate>
          <e667:Field i:nil="false">ValueHere</e667:Field>
          <e667:Operator>ValueHere</e667:Operator>
          <e667:Value i:nil="false">ValueHere</e667:Value>
        </e667:Predicate>
      </Predicates>
      <Ordering xmlns:e668="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e668:OrderBy>
          <e668:Field>ValueHere</e668:Field>
          <e668:Order>ValueHere</e668:Order>
        </e668:OrderBy>
      </Ordering>
      <PageInfo xmlns:e669="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e669:Index>ValueHere</e669:Index>
        <e669:Size>ValueHere</e669:Size>
      </PageInfo>
    </SearchInsertionOrdersRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Billing/v11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <SearchInsertionOrdersResponse xmlns="https://bingads.microsoft.com/Billing/v11">
      <InsertionOrders xmlns:e670="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e670:InsertionOrder>
          <e670:AccountId>ValueHere</e670:AccountId>
          <e670:BalanceAmount d4p1:nil="false">ValueHere</e670:BalanceAmount>
          <e670:BookingCountryCode d4p1:nil="false">ValueHere</e670:BookingCountryCode>
          <e670:Comment d4p1:nil="false">ValueHere</e670:Comment>
          <e670:EndDate>ValueHere</e670:EndDate>
          <e670:InsertionOrderId d4p1:nil="false">ValueHere</e670:InsertionOrderId>
          <e670:LastModifiedByUserId d4p1:nil="false">ValueHere</e670:LastModifiedByUserId>
          <e670:LastModifiedTime d4p1:nil="false">ValueHere</e670:LastModifiedTime>
          <e670:NotificationThreshold d4p1:nil="false">ValueHere</e670:NotificationThreshold>
          <e670:ReferenceId d4p1:nil="false">ValueHere</e670:ReferenceId>
          <e670:SpendCapAmount>ValueHere</e670:SpendCapAmount>
          <e670:StartDate>ValueHere</e670:StartDate>
          <e670:Name d4p1:nil="false">ValueHere</e670:Name>
          <e670:Status d4p1:nil="false">ValueHere</e670:Status>
          <e670:PurchaseOrder d4p1:nil="false">ValueHere</e670:PurchaseOrder>
          <e670:ChangePendingReview d4p1:nil="false">ValueHere</e670:ChangePendingReview>
        </e670:InsertionOrder>
      </InsertionOrders>
    </SearchInsertionOrdersResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<SearchInsertionOrdersResponse> SearchInsertionOrdersAsync(
	IList<Predicate> predicates,
	IList<OrderBy> ordering,
	Paging pageInfo)
{
	var request = new SearchInsertionOrdersRequest
	{
		Predicates = predicates,
		Ordering = ordering,
		PageInfo = pageInfo
	};

	return (await CustomerBillingService.CallAsync((s, r) => s.SearchInsertionOrdersAsync(r), request));
}
```
```java
static SearchInsertionOrdersResponse searchInsertionOrders(
	ArrayOfPredicate predicates,
	ArrayOfOrderBy ordering,
	Paging pageInfo) throws RemoteException, Exception
{
	SearchInsertionOrdersRequest request = new SearchInsertionOrdersRequest();

	request.setPredicates(predicates);
	request.setOrdering(ordering);
	request.setPageInfo(pageInfo);

	return CustomerBillingService.getService().searchInsertionOrders(request);
}
```
```php
static function SearchInsertionOrders(
	$predicates,
	$ordering,
	$pageInfo)

	$searchInsertionOrdersRequest = new SearchInsertionOrdersRequest();

	$request->Predicates = $predicates;
	$request->Ordering = $ordering;
	$request->PageInfo = $pageInfo;

	return $CustomerBillingProxy->GetService()->SearchInsertionOrders($request);
}
```
```python
response=customerbilling.SearchInsertionOrders(
	Predicates=PredicatesHere,
	Ordering=OrderingHere,
	PageInfo=PageInfoHere
)
```

## Requirements
Service: [CustomerBillingService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v11/CustomerBillingService.svc)  
Namespace: https://bingads.microsoft.com/Billing/v11  

