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
      <Predicates xmlns:e333="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e333:Predicate>
          <e333:Field i:nil="false">ValueHere</e333:Field>
          <e333:Operator>ValueHere</e333:Operator>
          <e333:Value i:nil="false">ValueHere</e333:Value>
        </e333:Predicate>
      </Predicates>
      <DateRange xmlns:e334="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e334:MinDate i:nil="false">ValueHere</e334:MinDate>
        <e334:MaxDate i:nil="false">ValueHere</e334:MaxDate>
      </DateRange>
      <Ordering xmlns:e335="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e335:OrderBy>
          <e335:Field>ValueHere</e335:Field>
          <e335:Order>ValueHere</e335:Order>
        </e335:OrderBy>
      </Ordering>
      <PageInfo xmlns:e336="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e336:Index>ValueHere</e336:Index>
        <e336:Size>ValueHere</e336:Size>
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
      <Customers xmlns:e337="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e337:Customer>
          <e337:CustomerAddress d4p1:nil="false">
            <e337:City d4p1:nil="false">ValueHere</e337:City>
            <e337:CountryCode d4p1:nil="false">ValueHere</e337:CountryCode>
            <e337:Id d4p1:nil="false">ValueHere</e337:Id>
            <e337:Line1 d4p1:nil="false">ValueHere</e337:Line1>
            <e337:Line2 d4p1:nil="false">ValueHere</e337:Line2>
            <e337:Line3 d4p1:nil="false">ValueHere</e337:Line3>
            <e337:Line4 d4p1:nil="false">ValueHere</e337:Line4>
            <e337:PostalCode d4p1:nil="false">ValueHere</e337:PostalCode>
            <e337:StateOrProvince d4p1:nil="false">ValueHere</e337:StateOrProvince>
            <e337:TimeStamp d4p1:nil="false">ValueHere</e337:TimeStamp>
          </e337:CustomerAddress>
          <e337:CustomerFinancialStatus d4p1:nil="false">ValueHere</e337:CustomerFinancialStatus>
          <e337:Id d4p1:nil="false">ValueHere</e337:Id>
          <e337:Industry d4p1:nil="false">ValueHere</e337:Industry>
          <e337:LastModifiedByUserId d4p1:nil="false">ValueHere</e337:LastModifiedByUserId>
          <e337:LastModifiedTime d4p1:nil="false">ValueHere</e337:LastModifiedTime>
          <e337:MarketCountry d4p1:nil="false">ValueHere</e337:MarketCountry>
          <ForwardCompatibilityMap xmlns:e338="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e338:KeyValuePairOfstringstring>
              <e338:key d4p1:nil="false">ValueHere</e338:key>
              <e338:value d4p1:nil="false">ValueHere</e338:value>
            </e338:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <e337:MarketLanguage d4p1:nil="false">ValueHere</e337:MarketLanguage>
          <e337:Name d4p1:nil="false">ValueHere</e337:Name>
          <e337:ServiceLevel d4p1:nil="false">ValueHere</e337:ServiceLevel>
          <e337:CustomerLifeCycleStatus d4p1:nil="false">ValueHere</e337:CustomerLifeCycleStatus>
          <e337:TimeStamp d4p1:nil="false">ValueHere</e337:TimeStamp>
          <e337:Number d4p1:nil="false">ValueHere</e337:Number>
        </e337:Customer>
      </Customers>
    </SearchCustomersResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](/bingads/guides/client-libraries.md). See [Bing Ads Code Examples](/bingads/guides/code-examples.md) for more examples.
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
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new SearchCustomersRequest();

	$request->ApplicationScope = $applicationScope;
	$request->Predicates = $predicates;
	$request->DateRange = $dateRange;
	$request->Ordering = $ordering;
	$request->PageInfo = $pageInfo;

	return $GLOBALS['CustomerManagementProxy']->GetService()->SearchCustomers($request);
}
```
```python
response=customermanagement_service.SearchCustomers(
	ApplicationScope=ApplicationScope,
	Predicates=Predicates,
	DateRange=DateRange,
	Ordering=Ordering,
	PageInfo=PageInfo)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11  

