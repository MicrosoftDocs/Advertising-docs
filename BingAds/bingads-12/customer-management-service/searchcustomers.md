---
title: SearchCustomers Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Searches for customers that match a specified criteria.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# SearchCustomers Service Operation - Customer Management

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Searches for customers that match a specified criteria.

## <a name="request"></a>Request Elements
The *SearchCustomersRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="daterange"></a>DateRange|Determines the minimum and maximum customer creation date range.|[DateRange](daterange.md)|
|<a name="ordering"></a>Ordering|Determines the order of results by the specified property of a customer.<br /><br /> You should only specify one *OrderBy* element in the array. Additional elements are not supported and will be ignored by the service.<br /><br />For this service operation, the following values are supported in the *Field* element of a *OrderBy* object:<br /><br />*Id* - The order is determined by the *Id*element of the returned [Customer](../customer-management-service/customer.md).<br /><br />*Name* - The order is determined by the *Name* element of the returned [Customer](../customer-management-service/customer.md).<br /><br />*Number* - The order is determined by the *Number* element of the returned [Customer](../customer-management-service/customer.md).|[OrderBy](orderby.md) array|
|<a name="pageinfo"></a>PageInfo|Determines the index and size of  results per page.|[Paging](paging.md)|
|<a name="predicates"></a>Predicates|Determines the request conditions. This operation's response will include customers that match all of the specified predicates.<br /><br /> You may specify up to 10 predicates. You may use the CreatedDate predicate field twice to specify a created date range, and otherwise may only use each predicate field once.<br /><br />For a list of supported *Field* and *Operator* elements of a [Predicate](predicate.md) object for this service operation, see [Predicate Remarks](predicate.md#remarks).|[Predicate](predicate.md) array|

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
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">SearchCustomers</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SearchCustomersRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <Predicates xmlns:e698="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e698:Predicate>
          <e698:Field i:nil="false">ValueHere</e698:Field>
          <e698:Operator>ValueHere</e698:Operator>
          <e698:Value i:nil="false">ValueHere</e698:Value>
        </e698:Predicate>
      </Predicates>
      <DateRange xmlns:e699="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e699:MinDate i:nil="false">ValueHere</e699:MinDate>
        <e699:MaxDate i:nil="false">ValueHere</e699:MaxDate>
      </DateRange>
      <Ordering xmlns:e700="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e700:OrderBy>
          <e700:Field>ValueHere</e700:Field>
          <e700:Order>ValueHere</e700:Order>
        </e700:OrderBy>
      </Ordering>
      <PageInfo xmlns:e701="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e701:Index>ValueHere</e701:Index>
        <e701:Size>ValueHere</e701:Size>
      </PageInfo>
    </SearchCustomersRequest>
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
    <SearchCustomersResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <Customers xmlns:e702="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e702:Customer>
          <e702:CustomerAddress d4p1:nil="false">
            <e702:City d4p1:nil="false">ValueHere</e702:City>
            <e702:CountryCode d4p1:nil="false">ValueHere</e702:CountryCode>
            <e702:Id d4p1:nil="false">ValueHere</e702:Id>
            <e702:Line1 d4p1:nil="false">ValueHere</e702:Line1>
            <e702:Line2 d4p1:nil="false">ValueHere</e702:Line2>
            <e702:Line3 d4p1:nil="false">ValueHere</e702:Line3>
            <e702:Line4 d4p1:nil="false">ValueHere</e702:Line4>
            <e702:PostalCode d4p1:nil="false">ValueHere</e702:PostalCode>
            <e702:StateOrProvince d4p1:nil="false">ValueHere</e702:StateOrProvince>
            <e702:TimeStamp d4p1:nil="false">ValueHere</e702:TimeStamp>
          </e702:CustomerAddress>
          <e702:CustomerFinancialStatus d4p1:nil="false">ValueHere</e702:CustomerFinancialStatus>
          <e702:Id d4p1:nil="false">ValueHere</e702:Id>
          <e702:Industry d4p1:nil="false">ValueHere</e702:Industry>
          <e702:LastModifiedByUserId d4p1:nil="false">ValueHere</e702:LastModifiedByUserId>
          <e702:LastModifiedTime d4p1:nil="false">ValueHere</e702:LastModifiedTime>
          <e702:MarketCountry d4p1:nil="false">ValueHere</e702:MarketCountry>
          <ForwardCompatibilityMap xmlns:e703="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e703:KeyValuePairOfstringstring>
              <e703:key d4p1:nil="false">ValueHere</e703:key>
              <e703:value d4p1:nil="false">ValueHere</e703:value>
            </e703:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <e702:MarketLanguage d4p1:nil="false">ValueHere</e702:MarketLanguage>
          <e702:Name d4p1:nil="false">ValueHere</e702:Name>
          <e702:ServiceLevel d4p1:nil="false">ValueHere</e702:ServiceLevel>
          <e702:CustomerLifeCycleStatus d4p1:nil="false">ValueHere</e702:CustomerLifeCycleStatus>
          <e702:TimeStamp d4p1:nil="false">ValueHere</e702:TimeStamp>
          <e702:Number d4p1:nil="false">ValueHere</e702:Number>
        </e702:Customer>
      </Customers>
    </SearchCustomersResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<SearchCustomersResponse> SearchCustomersAsync(
	IList<Predicate> predicates,
	DateRange dateRange,
	IList<OrderBy> ordering,
	Paging pageInfo)
{
	var request = new SearchCustomersRequest
	{
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
	ArrayOfPredicate predicates,
	DateRange dateRange,
	ArrayOfOrderBy ordering,
	Paging pageInfo) throws RemoteException, Exception
{
	SearchCustomersRequest request = new SearchCustomersRequest();

	request.setPredicates(predicates);
	request.setDateRange(dateRange);
	request.setOrdering(ordering);
	request.setPageInfo(pageInfo);

	return CustomerManagementService.getService().searchCustomers(request);
}
```
```php
static function SearchCustomers(
	$predicates,
	$dateRange,
	$ordering,
	$pageInfo)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new SearchCustomersRequest();

	$request->Predicates = $predicates;
	$request->DateRange = $dateRange;
	$request->Ordering = $ordering;
	$request->PageInfo = $pageInfo;

	return $GLOBALS['CustomerManagementProxy']->GetService()->SearchCustomers($request);
}
```
```python
response=customermanagement_service.SearchCustomers(
	Predicates=Predicates,
	DateRange=DateRange,
	Ordering=Ordering,
	PageInfo=PageInfo)
```

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

