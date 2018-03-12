---
title: SearchInsertionOrders Service Operation - Customer Billing
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Searches for insertion orders that match a specified criteria.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# SearchInsertionOrders Service Operation - Customer Billing
Searches for insertion orders that match a specified criteria.

## <a name="request"></a>Request Elements
The *SearchInsertionOrdersRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ordering"></a>Ordering|Determines the order of results by the specified property of an account.<br /><br /> You should only specify one *OrderBy* element in the array. Additional elements are not supported and will be ignored by the service.<br /><br />For this service operation, the following values are supported in the *Field* element of a *OrderBy* object.<br /><br />*Id* - The order is determined by the *InsertionOrderId*element of the returned [InsertionOrder](insertionorder.md).<br /><br />*Name* - The order is determined by the *Name* element of the returned [InsertionOrder](insertionorder.md).|[OrderBy](orderby.md) array|
|<a name="pageinfo"></a>PageInfo|Determines the index and size of  results per page.|[Paging](paging.md)|
|<a name="predicates"></a>Predicates|Determines the request conditions. This operation's response will include accounts that match all of the specified predicates.<br /><br /> You may specify up to 6 predicates, and one of the predicate fields must be AccountId. You may use the StartDate and EndDate predicate fields twice each to specify start and end date ranges, and otherwise may only use each predicate field once.<br /><br />For a list of supported *Field* and *Operator* elements of a [Predicate](predicate.md) object for this service operation, see [Predicate Remarks](predicate.md#remarks).|[Predicate](predicate.md) array|

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
  <s:Header xmlns="https://bingads.microsoft.com/Billing/v12">
    <Action mustUnderstand="1">SearchInsertionOrders</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SearchInsertionOrdersRequest xmlns="https://bingads.microsoft.com/Billing/v12">
      <Predicates xmlns:e371="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e371:Predicate>
          <e371:Field i:nil="false">ValueHere</e371:Field>
          <e371:Operator>ValueHere</e371:Operator>
          <e371:Value i:nil="false">ValueHere</e371:Value>
        </e371:Predicate>
      </Predicates>
      <Ordering xmlns:e372="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e372:OrderBy>
          <e372:Field>ValueHere</e372:Field>
          <e372:Order>ValueHere</e372:Order>
        </e372:OrderBy>
      </Ordering>
      <PageInfo xmlns:e373="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e373:Index>ValueHere</e373:Index>
        <e373:Size>ValueHere</e373:Size>
      </PageInfo>
    </SearchInsertionOrdersRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Billing/v12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <SearchInsertionOrdersResponse xmlns="https://bingads.microsoft.com/Billing/v12">
      <InsertionOrders xmlns:e374="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e374:InsertionOrder>
          <e374:AccountId>ValueHere</e374:AccountId>
          <e374:BalanceAmount d4p1:nil="false">ValueHere</e374:BalanceAmount>
          <e374:BookingCountryCode d4p1:nil="false">ValueHere</e374:BookingCountryCode>
          <e374:Comment d4p1:nil="false">ValueHere</e374:Comment>
          <e374:EndDate d4p1:nil="false">ValueHere</e374:EndDate>
          <e374:InsertionOrderId d4p1:nil="false">ValueHere</e374:InsertionOrderId>
          <e374:LastModifiedByUserId d4p1:nil="false">ValueHere</e374:LastModifiedByUserId>
          <e374:LastModifiedTime d4p1:nil="false">ValueHere</e374:LastModifiedTime>
          <e374:NotificationThreshold d4p1:nil="false">ValueHere</e374:NotificationThreshold>
          <e374:ReferenceId d4p1:nil="false">ValueHere</e374:ReferenceId>
          <e374:SpendCapAmount>ValueHere</e374:SpendCapAmount>
          <e374:StartDate d4p1:nil="false">ValueHere</e374:StartDate>
          <e374:Name d4p1:nil="false">ValueHere</e374:Name>
          <e374:Status d4p1:nil="false">ValueHere</e374:Status>
          <e374:PurchaseOrder d4p1:nil="false">ValueHere</e374:PurchaseOrder>
          <e374:ChangePendingReview d4p1:nil="false">ValueHere</e374:ChangePendingReview>
          <e374:PendingChanges d4p1:nil="false">
            <e374:Comment d4p1:nil="false">ValueHere</e374:Comment>
            <e374:EndDate d4p1:nil="false">ValueHere</e374:EndDate>
            <e374:RequestedByUserId d4p1:nil="false">ValueHere</e374:RequestedByUserId>
            <e374:ModifiedDateTime d4p1:nil="false">ValueHere</e374:ModifiedDateTime>
            <e374:NotificationThreshold d4p1:nil="false">ValueHere</e374:NotificationThreshold>
            <e374:ReferenceId d4p1:nil="false">ValueHere</e374:ReferenceId>
            <e374:SpendCapAmount>ValueHere</e374:SpendCapAmount>
            <e374:StartDate d4p1:nil="false">ValueHere</e374:StartDate>
            <e374:Name d4p1:nil="false">ValueHere</e374:Name>
            <e374:PurchaseOrder d4p1:nil="false">ValueHere</e374:PurchaseOrder>
            <e374:ChangeStatus d4p1:nil="false">ValueHere</e374:ChangeStatus>
          </e374:PendingChanges>
        </e374:InsertionOrder>
      </InsertionOrders>
    </SearchInsertionOrdersResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
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
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerBillingProxy'];

	$request = new SearchInsertionOrdersRequest();

	$request->Predicates = $predicates;
	$request->Ordering = $ordering;
	$request->PageInfo = $pageInfo;

	return $GLOBALS['CustomerBillingProxy']->GetService()->SearchInsertionOrders($request);
}
```
```python
response=customerbilling_service.SearchInsertionOrders(
	Predicates=Predicates,
	Ordering=Ordering,
	PageInfo=PageInfo)
```

## Requirements
Service: [CustomerBillingService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v12/CustomerBillingService.svc)  
Namespace: https\://bingads.microsoft.com/Billing/v12  

