---
title: SearchAccounts Service Operation
ms.service: bing-ads-customer-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# SearchAccounts Service Operation
Searches for accounts that match a specified criteria.

## <a name="request"></a>Request Elements
The *SearchAccountsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="predicates"></a>Predicates|Determines the request conditions. This operation's response will include accounts that match all of the specified predicates.<br/><br/>**Note:** With the exception of AccountLifeCycleStatus, you must specify exactly one predicate. When using the AccountLifeCycleStatus predicate field you must specify one additional predicate, for example with the *Field* set to UserId.<br /><br />For a list of supported *Field* and *Operator* elements of a *Predicate* object for this service operation, see [Predicate Field and Operator](#predicates).|[Predicate](predicate.md) array|
|<a name="ordering"></a>Ordering|Determines the order of results by the specified property of an account<br/><br/>**Note:** You should only specify one *OrderBy* element in the array. Additional elements are not supported and will be ignored by the service.<br /><br />For this service operation, the following values are supported in the *Field* element of a *OrderBy* object.<br /><br />*Id* - The order is determined by the *Id*element of the returned [Account](../customer-management/account.md).<br /><br />*Name* - The order is determined by the *Name* element of the returned [Account](../customer-management/account.md).<br /><br />*Number* - The order is determined by the *Number* element of the returned [Account](../customer-management/account.md).|[OrderBy](orderby.md) array|
|<a name="pageinfo"></a>PageInfo|Determines the index and size of  results per page.|[Paging](paging.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SearchAccountsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accounts"></a>Accounts|A  list of accounts that meet the specified criteria.|[Account](account.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">SearchAccounts</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SearchAccountsRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <Predicates xmlns:e422="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e422:Predicate>
          <e422:Field i:nil="false">ValueHere</e422:Field>
          <e422:Operator>ValueHere</e422:Operator>
          <e422:Value i:nil="false">ValueHere</e422:Value>
        </e422:Predicate>
      </Predicates>
      <Ordering xmlns:e423="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e423:OrderBy>
          <e423:Field>ValueHere</e423:Field>
          <e423:Order>ValueHere</e423:Order>
        </e423:OrderBy>
      </Ordering>
      <PageInfo xmlns:e424="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e424:Index>ValueHere</e424:Index>
        <e424:Size>ValueHere</e424:Size>
      </PageInfo>
    </SearchAccountsRequest>
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
    <SearchAccountsResponse xmlns="https://bingads.microsoft.com/Customer/v11">
      <Accounts xmlns:e425="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e425:Account d4p1:type="-- derived type specified here with the appropriate prefix --">
          <e425:AccountType>ValueHere</e425:AccountType>
          <e425:BillToCustomerId d4p1:nil="false">ValueHere</e425:BillToCustomerId>
          <e425:CountryCode d4p1:nil="false">ValueHere</e425:CountryCode>
          <e425:CurrencyType d4p1:nil="false">ValueHere</e425:CurrencyType>
          <e425:AccountFinancialStatus d4p1:nil="false">ValueHere</e425:AccountFinancialStatus>
          <e425:Id d4p1:nil="false">ValueHere</e425:Id>
          <e425:Language d4p1:nil="false">ValueHere</e425:Language>
          <ForwardCompatibilityMap xmlns:e426="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e426:KeyValuePairOfstringstring>
              <e426:key d4p1:nil="false">ValueHere</e426:key>
              <e426:value d4p1:nil="false">ValueHere</e426:value>
            </e426:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <e425:LastModifiedByUserId d4p1:nil="false">ValueHere</e425:LastModifiedByUserId>
          <e425:LastModifiedTime d4p1:nil="false">ValueHere</e425:LastModifiedTime>
          <e425:Name d4p1:nil="false">ValueHere</e425:Name>
          <e425:Number d4p1:nil="false">ValueHere</e425:Number>
          <e425:ParentCustomerId>ValueHere</e425:ParentCustomerId>
          <e425:PaymentMethodId d4p1:nil="false">ValueHere</e425:PaymentMethodId>
          <e425:PaymentMethodType d4p1:nil="false">ValueHere</e425:PaymentMethodType>
          <e425:PrimaryUserId d4p1:nil="false">ValueHere</e425:PrimaryUserId>
          <e425:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e425:AccountLifeCycleStatus>
          <e425:TimeStamp d4p1:nil="false">ValueHere</e425:TimeStamp>
          <e425:TimeZone d4p1:nil="false">ValueHere</e425:TimeZone>
          <e425:PauseReason d4p1:nil="false">ValueHere</e425:PauseReason>
          <!--These fields are applicable if the derived type attribute is set to AdvertiserAccount-->
          <e425:LinkedAgencies d4p1:nil="false">
            <e425:CustomerInfo>
              <e425:Id d4p1:nil="false">ValueHere</e425:Id>
              <e425:Name d4p1:nil="false">ValueHere</e425:Name>
            </e425:CustomerInfo>
          </e425:LinkedAgencies>
          <e425:SalesHouseCustomerId d4p1:nil="false">ValueHere</e425:SalesHouseCustomerId>
          <TaxInformation xmlns:e427="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e427:KeyValuePairOfstringstring>
              <e427:key d4p1:nil="false">ValueHere</e427:key>
              <e427:value d4p1:nil="false">ValueHere</e427:value>
            </e427:KeyValuePairOfstringstring>
          </TaxInformation>
          <e425:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e425:BackUpPaymentInstrumentId>
          <e425:BillingThresholdAmount d4p1:nil="false">ValueHere</e425:BillingThresholdAmount>
          <e425:BusinessAddress d4p1:nil="false">
            <e425:City d4p1:nil="false">ValueHere</e425:City>
            <e425:CountryCode d4p1:nil="false">ValueHere</e425:CountryCode>
            <e425:Id d4p1:nil="false">ValueHere</e425:Id>
            <e425:Line1 d4p1:nil="false">ValueHere</e425:Line1>
            <e425:Line2 d4p1:nil="false">ValueHere</e425:Line2>
            <e425:Line3 d4p1:nil="false">ValueHere</e425:Line3>
            <e425:Line4 d4p1:nil="false">ValueHere</e425:Line4>
            <e425:PostalCode d4p1:nil="false">ValueHere</e425:PostalCode>
            <e425:StateOrProvince d4p1:nil="false">ValueHere</e425:StateOrProvince>
            <e425:TimeStamp d4p1:nil="false">ValueHere</e425:TimeStamp>
          </e425:BusinessAddress>
        </e425:Account>
      </Accounts>
    </SearchAccountsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
```csharp
protected async Task<SearchAccountsResponse> SearchAccountsAsync(
	IList<Predicate> predicates,
	IList<OrderBy> ordering,
	Paging pageInfo)
{
	var request = new SearchAccountsRequest
	{
		Predicates = predicates,
		Ordering = ordering,
		PageInfo = pageInfo
	};

	return (await CustomerManagement.CallAsync((s, r) => s.SearchAccountsAsync(r), request));
}
```
```java
static SearchAccountsResponse searchAccounts(
	ArrayOfPredicate predicates,
	ArrayOfOrderBy ordering,
	Paging pageInfo)
{
	SearchAccountsRequest request = new SearchAccountsRequest();

	request.setPredicates(predicates);
	request.setOrdering(ordering);
	request.setPageInfo(pageInfo);

	return CustomerManagement.getService().searchAccounts(request);
}
```
```php
static function SearchAccounts(
	$predicates,
	$ordering,
	$pageInfo)

	$searchAccountsRequest = new SearchAccountsRequest();

	$request->Predicates = $predicates;
	$request->Ordering = $ordering;
	$request->PageInfo = $pageInfo;

	return $CustomerManagementProxy->GetService()->SearchAccounts($request);
}
```
```python
response=customermanagement.SearchAccounts(
	Predicates=PredicatesHere,
	Ordering=OrderingHere,
	PageInfo=PageInfoHere
)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

