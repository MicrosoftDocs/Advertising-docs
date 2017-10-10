---
title: SearchAccounts Service Operation
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Searches for accounts that match a specified criteria.
---
# SearchAccounts Service Operation
Searches for accounts that match a specified criteria.

## <a name="request"></a>Request Elements
The *SearchAccountsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ordering"></a>Ordering|Determines the order of results by the specified property of an account<br/><br/> You should only specify one *OrderBy* element in the array. Additional elements are not supported and will be ignored by the service.<br /><br />For this service operation, the following values are supported in the *Field* element of a *OrderBy* object.<br /><br />*Id* - The order is determined by the *Id*element of the returned [Account](../customer-management-service/account.md).<br /><br />*Name* - The order is determined by the *Name* element of the returned [Account](../customer-management-service/account.md).<br /><br />*Number* - The order is determined by the *Number* element of the returned [Account](../customer-management-service/account.md).|[OrderBy](orderby.md) array|
|<a name="pageinfo"></a>PageInfo|Determines the index and size of  results per page.|[Paging](paging.md)|
|<a name="predicates"></a>Predicates|Determines the request conditions. This operation's response will include accounts that match all of the specified predicates.<br/><br/> With the exception of AccountLifeCycleStatus, you must specify exactly one predicate. When using the AccountLifeCycleStatus predicate field you must specify one additional predicate, for example with the *Field* set to UserId.<br /><br />For a list of supported *Field* and *Operator* elements of a *Predicate* object for this service operation, see [Predicate Field and Operator](#predicates).|[Predicate](predicate.md) array|

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
      <Predicates xmlns:e628="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e628:Predicate>
          <e628:Field i:nil="false">ValueHere</e628:Field>
          <e628:Operator>ValueHere</e628:Operator>
          <e628:Value i:nil="false">ValueHere</e628:Value>
        </e628:Predicate>
      </Predicates>
      <Ordering xmlns:e629="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e629:OrderBy>
          <e629:Field>ValueHere</e629:Field>
          <e629:Order>ValueHere</e629:Order>
        </e629:OrderBy>
      </Ordering>
      <PageInfo xmlns:e630="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e630:Index>ValueHere</e630:Index>
        <e630:Size>ValueHere</e630:Size>
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
      <Accounts xmlns:e631="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e631:Account d4p1:type="-- derived type specified here with the appropriate prefix --">
          <e631:AccountType>ValueHere</e631:AccountType>
          <e631:BillToCustomerId d4p1:nil="false">ValueHere</e631:BillToCustomerId>
          <e631:CountryCode d4p1:nil="false">ValueHere</e631:CountryCode>
          <e631:CurrencyType d4p1:nil="false">ValueHere</e631:CurrencyType>
          <e631:AccountFinancialStatus d4p1:nil="false">ValueHere</e631:AccountFinancialStatus>
          <e631:Id d4p1:nil="false">ValueHere</e631:Id>
          <e631:Language d4p1:nil="false">ValueHere</e631:Language>
          <ForwardCompatibilityMap xmlns:e632="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e632:KeyValuePairOfstringstring>
              <e632:key d4p1:nil="false">ValueHere</e632:key>
              <e632:value d4p1:nil="false">ValueHere</e632:value>
            </e632:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <e631:LastModifiedByUserId d4p1:nil="false">ValueHere</e631:LastModifiedByUserId>
          <e631:LastModifiedTime d4p1:nil="false">ValueHere</e631:LastModifiedTime>
          <e631:Name d4p1:nil="false">ValueHere</e631:Name>
          <e631:Number d4p1:nil="false">ValueHere</e631:Number>
          <e631:ParentCustomerId>ValueHere</e631:ParentCustomerId>
          <e631:PaymentMethodId d4p1:nil="false">ValueHere</e631:PaymentMethodId>
          <e631:PaymentMethodType d4p1:nil="false">ValueHere</e631:PaymentMethodType>
          <e631:PrimaryUserId d4p1:nil="false">ValueHere</e631:PrimaryUserId>
          <e631:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e631:AccountLifeCycleStatus>
          <e631:TimeStamp d4p1:nil="false">ValueHere</e631:TimeStamp>
          <e631:TimeZone d4p1:nil="false">ValueHere</e631:TimeZone>
          <e631:PauseReason d4p1:nil="false">ValueHere</e631:PauseReason>
          <!--These fields are applicable if the derived type attribute is set to AdvertiserAccount-->
          <e631:LinkedAgencies d4p1:nil="false">
            <e631:CustomerInfo>
              <e631:Id d4p1:nil="false">ValueHere</e631:Id>
              <e631:Name d4p1:nil="false">ValueHere</e631:Name>
            </e631:CustomerInfo>
          </e631:LinkedAgencies>
          <e631:SalesHouseCustomerId d4p1:nil="false">ValueHere</e631:SalesHouseCustomerId>
          <TaxInformation xmlns:e633="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e633:KeyValuePairOfstringstring>
              <e633:key d4p1:nil="false">ValueHere</e633:key>
              <e633:value d4p1:nil="false">ValueHere</e633:value>
            </e633:KeyValuePairOfstringstring>
          </TaxInformation>
          <e631:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e631:BackUpPaymentInstrumentId>
          <e631:BillingThresholdAmount d4p1:nil="false">ValueHere</e631:BillingThresholdAmount>
          <e631:BusinessAddress d4p1:nil="false">
            <e631:City d4p1:nil="false">ValueHere</e631:City>
            <e631:CountryCode d4p1:nil="false">ValueHere</e631:CountryCode>
            <e631:Id d4p1:nil="false">ValueHere</e631:Id>
            <e631:Line1 d4p1:nil="false">ValueHere</e631:Line1>
            <e631:Line2 d4p1:nil="false">ValueHere</e631:Line2>
            <e631:Line3 d4p1:nil="false">ValueHere</e631:Line3>
            <e631:Line4 d4p1:nil="false">ValueHere</e631:Line4>
            <e631:PostalCode d4p1:nil="false">ValueHere</e631:PostalCode>
            <e631:StateOrProvince d4p1:nil="false">ValueHere</e631:StateOrProvince>
            <e631:TimeStamp d4p1:nil="false">ValueHere</e631:TimeStamp>
          </e631:BusinessAddress>
        </e631:Account>
      </Accounts>
    </SearchAccountsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<SearchAccountsResponse> SearchAccountsAsync(
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

	return (await CustomerManagementService.CallAsync((s, r) => s.SearchAccountsAsync(r), request));
}
```
```java
static SearchAccountsResponse searchAccounts(
	ArrayOfPredicate predicates,
	ArrayOfOrderBy ordering,
	Paging pageInfo) throws RemoteException, Exception
{
	SearchAccountsRequest request = new SearchAccountsRequest();

	request.setPredicates(predicates);
	request.setOrdering(ordering);
	request.setPageInfo(pageInfo);

	return CustomerManagementService.getService().searchAccounts(request);
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

