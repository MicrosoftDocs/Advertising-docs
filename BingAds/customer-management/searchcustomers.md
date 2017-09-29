---
title: SearchCustomers Service Operation
ms.service: bing-ads-customer-management
ms.topic: article
author: eric-urban
ms.author: eur
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
|<a name="ordering"></a>Ordering|Determines the order of results by the specified property of a customer.<br /><br />**Note**: You should only specify one *OrderBy* element in the array. Additional elements are not supported and will be ignored by the service.<br /><br />For this service operation, the following values are supported in the *Field* element of a *OrderBy* object:<br /><br />*Id* - The order is determined by the *Id*element of the returned [Customer](../customer-management/customer.md).<br /><br />*Name* - The order is determined by the *Name* element of the returned [Customer](../customer-management/customer.md).<br /><br />*Number* - The order is determined by the *Number* element of the returned [Customer](../customer-management/customer.md).|[OrderBy](orderby.md) array|
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
      <Predicates xmlns:e433="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e433:Predicate>
          <e433:Field i:nil="false">ValueHere</e433:Field>
          <e433:Operator>ValueHere</e433:Operator>
          <e433:Value i:nil="false">ValueHere</e433:Value>
        </e433:Predicate>
      </Predicates>
      <DateRange xmlns:e434="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e434:MinDate i:nil="false">ValueHere</e434:MinDate>
        <e434:MaxDate i:nil="false">ValueHere</e434:MaxDate>
      </DateRange>
      <Ordering xmlns:e435="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e435:OrderBy>
          <e435:Field>ValueHere</e435:Field>
          <e435:Order>ValueHere</e435:Order>
        </e435:OrderBy>
      </Ordering>
      <PageInfo xmlns:e436="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e436:Index>ValueHere</e436:Index>
        <e436:Size>ValueHere</e436:Size>
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
      <Customers xmlns:e437="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e437:Customer>
          <e437:CustomerAddress d4p1:nil="false">
            <e437:City d4p1:nil="false">ValueHere</e437:City>
            <e437:CountryCode d4p1:nil="false">ValueHere</e437:CountryCode>
            <e437:Id d4p1:nil="false">ValueHere</e437:Id>
            <e437:Line1 d4p1:nil="false">ValueHere</e437:Line1>
            <e437:Line2 d4p1:nil="false">ValueHere</e437:Line2>
            <e437:Line3 d4p1:nil="false">ValueHere</e437:Line3>
            <e437:Line4 d4p1:nil="false">ValueHere</e437:Line4>
            <e437:PostalCode d4p1:nil="false">ValueHere</e437:PostalCode>
            <e437:StateOrProvince d4p1:nil="false">ValueHere</e437:StateOrProvince>
            <e437:TimeStamp d4p1:nil="false">ValueHere</e437:TimeStamp>
          </e437:CustomerAddress>
          <e437:CustomerFinancialStatus d4p1:nil="false">ValueHere</e437:CustomerFinancialStatus>
          <e437:Id d4p1:nil="false">ValueHere</e437:Id>
          <e437:Industry d4p1:nil="false">ValueHere</e437:Industry>
          <e437:LastModifiedByUserId d4p1:nil="false">ValueHere</e437:LastModifiedByUserId>
          <e437:LastModifiedTime d4p1:nil="false">ValueHere</e437:LastModifiedTime>
          <e437:MarketCountry d4p1:nil="false">ValueHere</e437:MarketCountry>
          <ForwardCompatibilityMap xmlns:e438="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e438:KeyValuePairOfstringstring>
              <e438:key d4p1:nil="false">ValueHere</e438:key>
              <e438:value d4p1:nil="false">ValueHere</e438:value>
            </e438:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <e437:MarketLanguage d4p1:nil="false">ValueHere</e437:MarketLanguage>
          <e437:Name d4p1:nil="false">ValueHere</e437:Name>
          <e437:ServiceLevel d4p1:nil="false">ValueHere</e437:ServiceLevel>
          <e437:CustomerLifeCycleStatus d4p1:nil="false">ValueHere</e437:CustomerLifeCycleStatus>
          <e437:TimeStamp d4p1:nil="false">ValueHere</e437:TimeStamp>
          <e437:Number d4p1:nil="false">ValueHere</e437:Number>
        </e437:Customer>
      </Customers>
    </SearchCustomersResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
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
	Paging pageInfo)
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

