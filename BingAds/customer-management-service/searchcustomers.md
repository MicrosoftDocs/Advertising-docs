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
|<a name="daterange"></a>DateRange|Determines the minimum and maximum customer creation date range.|[DateRange](daterange.md)|
|<a name="ordering"></a>Ordering|Determines the order of results by the specified property of a customer.<br /><br /> You should only specify one *OrderBy* element in the array. Additional elements are not supported and will be ignored by the service.<br /><br />For this service operation, the following values are supported in the *Field* element of a *OrderBy* object:<br /><br />*Id* - The order is determined by the *Id*element of the returned [Customer](../customer-management-service/customer.md).<br /><br />*Name* - The order is determined by the *Name* element of the returned [Customer](../customer-management-service/customer.md).<br /><br />*Number* - The order is determined by the *Number* element of the returned [Customer](../customer-management-service/customer.md).|[OrderBy](orderby.md) array|
|<a name="pageinfo"></a>PageInfo|Determines the index and size of  results per page.|[Paging](paging.md)|
|<a name="predicates"></a>Predicates|Determines the request conditions. This operation's response will include customers that match all of the specified predicates.<br /><br /> You may specify up to 10 predicates. You may use the CreatedDate predicate field twice to specify a created date range, and otherwise may only use each predicate field once.<br /><br />For a list of supported *Field* and *Operator* elements of a *Predicate* object for this service operation, see [Predicate Field and Operator](#predicates).|[Predicate](predicate.md) array|

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
      <Predicates xmlns:e639="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e639:Predicate>
          <e639:Field i:nil="false">ValueHere</e639:Field>
          <e639:Operator>ValueHere</e639:Operator>
          <e639:Value i:nil="false">ValueHere</e639:Value>
        </e639:Predicate>
      </Predicates>
      <DateRange xmlns:e640="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e640:MinDate i:nil="false">ValueHere</e640:MinDate>
        <e640:MaxDate i:nil="false">ValueHere</e640:MaxDate>
      </DateRange>
      <Ordering xmlns:e641="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e641:OrderBy>
          <e641:Field>ValueHere</e641:Field>
          <e641:Order>ValueHere</e641:Order>
        </e641:OrderBy>
      </Ordering>
      <PageInfo xmlns:e642="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e642:Index>ValueHere</e642:Index>
        <e642:Size>ValueHere</e642:Size>
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
      <Customers xmlns:e643="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e643:Customer>
          <e643:CustomerAddress d4p1:nil="false">
            <e643:City d4p1:nil="false">ValueHere</e643:City>
            <e643:CountryCode d4p1:nil="false">ValueHere</e643:CountryCode>
            <e643:Id d4p1:nil="false">ValueHere</e643:Id>
            <e643:Line1 d4p1:nil="false">ValueHere</e643:Line1>
            <e643:Line2 d4p1:nil="false">ValueHere</e643:Line2>
            <e643:Line3 d4p1:nil="false">ValueHere</e643:Line3>
            <e643:Line4 d4p1:nil="false">ValueHere</e643:Line4>
            <e643:PostalCode d4p1:nil="false">ValueHere</e643:PostalCode>
            <e643:StateOrProvince d4p1:nil="false">ValueHere</e643:StateOrProvince>
            <e643:TimeStamp d4p1:nil="false">ValueHere</e643:TimeStamp>
          </e643:CustomerAddress>
          <e643:CustomerFinancialStatus d4p1:nil="false">ValueHere</e643:CustomerFinancialStatus>
          <e643:Id d4p1:nil="false">ValueHere</e643:Id>
          <e643:Industry d4p1:nil="false">ValueHere</e643:Industry>
          <e643:LastModifiedByUserId d4p1:nil="false">ValueHere</e643:LastModifiedByUserId>
          <e643:LastModifiedTime d4p1:nil="false">ValueHere</e643:LastModifiedTime>
          <e643:MarketCountry d4p1:nil="false">ValueHere</e643:MarketCountry>
          <ForwardCompatibilityMap xmlns:e644="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e644:KeyValuePairOfstringstring>
              <e644:key d4p1:nil="false">ValueHere</e644:key>
              <e644:value d4p1:nil="false">ValueHere</e644:value>
            </e644:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <e643:MarketLanguage d4p1:nil="false">ValueHere</e643:MarketLanguage>
          <e643:Name d4p1:nil="false">ValueHere</e643:Name>
          <e643:ServiceLevel d4p1:nil="false">ValueHere</e643:ServiceLevel>
          <e643:CustomerLifeCycleStatus d4p1:nil="false">ValueHere</e643:CustomerLifeCycleStatus>
          <e643:TimeStamp d4p1:nil="false">ValueHere</e643:TimeStamp>
          <e643:Number d4p1:nil="false">ValueHere</e643:Number>
        </e643:Customer>
      </Customers>
    </SearchCustomersResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<SearchCustomersResponse> SearchCustomersAsync(
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

	return (await CustomerManagementService.CallAsync((s, r) => s.SearchCustomersAsync(r), request));
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

	return CustomerManagementService.getService().searchCustomers(request);
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

