---
title: SearchCustomers Service Operation
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Searches for customers that match a specified criteria.
---
# SearchCustomers Service Operation
Searches for customers that match a specified criteria.

## <a name="request"></a>Request Elements
The *SearchCustomersRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="applicationscope"></a>ApplicationScope|A value that determines whether to return results for advertising customers or publishing customers. If you do not specify the scope, the list may include both types of customers.|[ApplicationType](applicationtype.md)|
|<a name="predicates"></a>Predicates|Determines the request conditions. This operation's response will include customers that match all of the specified predicates.<br /><br />**Note**: You may specify up to 10 predicates. You may use the CreatedDate predicate field twice to specify a created date range, and otherwise may only use each predicate field once.<br /><br />For a list of supported *Field* and *Operator* elements of a *Predicate* object for this service operation, see [Predicate Field and Operator](#predicates).|[Predicate](predicate.md) array|
|<a name="daterange"></a>DateRange|Determines the minimum and maximum customer creation date range.|[DateRange](daterange.md)|
|<a name="ordering"></a>Ordering|Determines the order of results by the specified property of a customer.<br /><br />**Note**: You should only specify one *OrderBy* element in the array. Additional elements are not supported and will be ignored by the service.<br /><br />For this service operation, the following values are supported in the *Field* element of a *OrderBy* object:<br /><br />*Id* - The order is determined by the *Id*element of the returned [Customer](../customer-management-service/customer.md).<br /><br />*Name* - The order is determined by the *Name* element of the returned [Customer](../customer-management-service/customer.md).<br /><br />*Number* - The order is determined by the *Number* element of the returned [Customer](../customer-management-service/customer.md).|[OrderBy](orderby.md) array|
|<a name="pageinfo"></a>PageInfo|Determines the index and size of  results per page.|[Paging](paging.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SearchCustomersResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customers"></a>Customers|A  list of customers that meet the specified criteria.|[Customer](customer.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">SearchCustomers</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SearchCustomersRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <ApplicationScope>ValueHere</ApplicationScope>
      <Predicates xmlns:e27="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e27:Predicate>
          <e27:Field i:nil="false">ValueHere</e27:Field>
          <e27:Operator>ValueHere</e27:Operator>
          <e27:Value i:nil="false">ValueHere</e27:Value>
        </e27:Predicate>
      </Predicates>
      <DateRange xmlns:e28="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e28:MinDate i:nil="false">ValueHere</e28:MinDate>
        <e28:MaxDate i:nil="false">ValueHere</e28:MaxDate>
      </DateRange>
      <Ordering xmlns:e29="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e29:OrderBy>
          <e29:Field>ValueHere</e29:Field>
          <e29:Order>ValueHere</e29:Order>
        </e29:OrderBy>
      </Ordering>
      <PageInfo xmlns:e30="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e30:Index>ValueHere</e30:Index>
        <e30:Size>ValueHere</e30:Size>
      </PageInfo>
    </SearchCustomersRequest>
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
    <SearchCustomersResponse xmlns="https://bingads.microsoft.com/Customer/v11">
      <Customers xmlns:e31="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e31:Customer>
          <e31:CustomerAddress d4p1:nil="false">
            <e31:City d4p1:nil="false">ValueHere</e31:City>
            <e31:CountryCode d4p1:nil="false">ValueHere</e31:CountryCode>
            <e31:Id d4p1:nil="false">ValueHere</e31:Id>
            <e31:Line1 d4p1:nil="false">ValueHere</e31:Line1>
            <e31:Line2 d4p1:nil="false">ValueHere</e31:Line2>
            <e31:Line3 d4p1:nil="false">ValueHere</e31:Line3>
            <e31:Line4 d4p1:nil="false">ValueHere</e31:Line4>
            <e31:PostalCode d4p1:nil="false">ValueHere</e31:PostalCode>
            <e31:StateOrProvince d4p1:nil="false">ValueHere</e31:StateOrProvince>
            <e31:TimeStamp d4p1:nil="false">ValueHere</e31:TimeStamp>
          </e31:CustomerAddress>
          <e31:CustomerFinancialStatus d4p1:nil="false">ValueHere</e31:CustomerFinancialStatus>
          <e31:Id d4p1:nil="false">ValueHere</e31:Id>
          <e31:Industry d4p1:nil="false">ValueHere</e31:Industry>
          <e31:LastModifiedByUserId d4p1:nil="false">ValueHere</e31:LastModifiedByUserId>
          <e31:LastModifiedTime d4p1:nil="false">ValueHere</e31:LastModifiedTime>
          <e31:MarketCountry d4p1:nil="false">ValueHere</e31:MarketCountry>
          <ForwardCompatibilityMap xmlns:e32="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e32:KeyValuePairOfstringstring>
              <e32:key d4p1:nil="false">ValueHere</e32:key>
              <e32:value d4p1:nil="false">ValueHere</e32:value>
            </e32:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <e31:MarketLanguage d4p1:nil="false">ValueHere</e31:MarketLanguage>
          <e31:Name d4p1:nil="false">ValueHere</e31:Name>
          <e31:ServiceLevel d4p1:nil="false">ValueHere</e31:ServiceLevel>
          <e31:CustomerLifeCycleStatus d4p1:nil="false">ValueHere</e31:CustomerLifeCycleStatus>
          <e31:TimeStamp d4p1:nil="false">ValueHere</e31:TimeStamp>
          <e31:Number d4p1:nil="false">ValueHere</e31:Number>
        </e31:Customer>
      </Customers>
    </SearchCustomersResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
protected async Task<SearchCustomersResponse> SearchCustomersAsync(
	ApplicationType applicationScope,
	IList<Predicate> predicates,
	DateRange dateRange,
	IList<OrderBy> ordering,
	Paging pageInfo)
{
	var request = new SearchCustomersRequest
	{
		ApplicationScope = applicationScope,
		Predicates = predicates,
		DateRange = dateRange,
		Ordering = ordering,
		PageInfo = pageInfo
	};

	return (await CustomerManagement.CallAsync((s, r) => s.SearchCustomersAsync(r), request));
}
```
```java
static SearchCustomersResponse searchCustomers(
	ApplicationType applicationScope,
	ArrayOfPredicate predicates,
	DateRange dateRange,
	ArrayOfOrderBy ordering,
	Paging pageInfo) throws RemoteException, Exception
{
	SearchCustomersRequest request = new SearchCustomersRequest();

	request.setApplicationScope(applicationScope);
	request.setPredicates(predicates);
	request.setDateRange(dateRange);
	request.setOrdering(ordering);
	request.setPageInfo(pageInfo);

	return CustomerManagement.getService().searchCustomers(request);
}
```
```php
static function SearchCustomers(
	$applicationScope,
	$predicates,
	$dateRange,
	$ordering,
	$pageInfo)

	$searchCustomersRequest = new SearchCustomersRequest();

	$request->ApplicationScope = $applicationScope;
	$request->Predicates = $predicates;
	$request->DateRange = $dateRange;
	$request->Ordering = $ordering;
	$request->PageInfo = $pageInfo;

	return $CustomerManagementProxy->GetService()->SearchCustomers($request);
}
```
```python
response=customermanagement.SearchCustomers(
	ApplicationScope=ApplicationScopeHere,
	Predicates=PredicatesHere,
	DateRange=DateRangeHere,
	Ordering=OrderingHere,
	PageInfo=PageInfoHere
)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

