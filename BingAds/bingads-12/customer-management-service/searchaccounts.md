---
title: SearchAccounts Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Searches for accounts that match a specified criteria.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# SearchAccounts Service Operation - Customer Management

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Searches for accounts that match a specified criteria.

## <a name="request"></a>Request Elements
The *SearchAccountsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ordering"></a>Ordering|Determines the order of results by the specified property of an account<br/><br/> You should only specify one *OrderBy* element in the array. Additional elements are not supported and will be ignored by the service.<br /><br />For this service operation, the following values are supported in the *Field* element of a *OrderBy* object.<br /><br />*Id* - The order is determined by the *Id*element of the returned [Account](../customer-management-service/account.md).<br /><br />*Name* - The order is determined by the *Name* element of the returned [Account](../customer-management-service/account.md).<br /><br />*Number* - The order is determined by the *Number* element of the returned [Account](../customer-management-service/account.md).|[OrderBy](orderby.md) array|
|<a name="pageinfo"></a>PageInfo|Determines the index and size of  results per page.|[Paging](paging.md)|
|<a name="predicates"></a>Predicates|Determines the request conditions. This operation's response will include accounts that match all of the specified predicates.<br/><br/> With the exception of AccountLifeCycleStatus, you must specify exactly one predicate. When using the AccountLifeCycleStatus predicate field you must specify one additional predicate, for example with the *Field* set to UserId.<br /><br />For a list of supported *Field* and *Operator* elements of a [Predicate](predicate.md) object for this service operation, see [Predicate Remarks](predicate.md#remarks).|[Predicate](predicate.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SearchAccountsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accounts"></a>Accounts|A  list of accounts that meet the specified criteria.|[AdvertiserAccount](advertiseraccount.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">SearchAccounts</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SearchAccountsRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <Predicates xmlns:e687="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e687:Predicate>
          <e687:Field i:nil="false">ValueHere</e687:Field>
          <e687:Operator>ValueHere</e687:Operator>
          <e687:Value i:nil="false">ValueHere</e687:Value>
        </e687:Predicate>
      </Predicates>
      <Ordering xmlns:e688="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e688:OrderBy>
          <e688:Field>ValueHere</e688:Field>
          <e688:Order>ValueHere</e688:Order>
        </e688:OrderBy>
      </Ordering>
      <PageInfo xmlns:e689="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e689:Index>ValueHere</e689:Index>
        <e689:Size>ValueHere</e689:Size>
      </PageInfo>
    </SearchAccountsRequest>
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
    <SearchAccountsResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <Accounts xmlns:e690="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e690:AdvertiserAccount>
          <e690:BillToCustomerId d4p1:nil="false">ValueHere</e690:BillToCustomerId>
          <e690:CountryCode d4p1:nil="false">ValueHere</e690:CountryCode>
          <e690:CurrencyType d4p1:nil="false">ValueHere</e690:CurrencyType>
          <e690:AccountFinancialStatus d4p1:nil="false">ValueHere</e690:AccountFinancialStatus>
          <e690:Id d4p1:nil="false">ValueHere</e690:Id>
          <e690:Language d4p1:nil="false">ValueHere</e690:Language>
          <e690:LastModifiedByUserId d4p1:nil="false">ValueHere</e690:LastModifiedByUserId>
          <e690:LastModifiedTime d4p1:nil="false">ValueHere</e690:LastModifiedTime>
          <e690:Name d4p1:nil="false">ValueHere</e690:Name>
          <e690:Number d4p1:nil="false">ValueHere</e690:Number>
          <e690:ParentCustomerId>ValueHere</e690:ParentCustomerId>
          <e690:PaymentMethodId d4p1:nil="false">ValueHere</e690:PaymentMethodId>
          <e690:PaymentMethodType d4p1:nil="false">ValueHere</e690:PaymentMethodType>
          <e690:PrimaryUserId d4p1:nil="false">ValueHere</e690:PrimaryUserId>
          <e690:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e690:AccountLifeCycleStatus>
          <e690:TimeStamp d4p1:nil="false">ValueHere</e690:TimeStamp>
          <e690:TimeZone d4p1:nil="false">ValueHere</e690:TimeZone>
          <e690:PauseReason d4p1:nil="false">ValueHere</e690:PauseReason>
          <ForwardCompatibilityMap xmlns:e691="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e691:KeyValuePairOfstringstring>
              <e691:key d4p1:nil="false">ValueHere</e691:key>
              <e691:value d4p1:nil="false">ValueHere</e691:value>
            </e691:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <e690:LinkedAgencies d4p1:nil="false">
            <e690:CustomerInfo>
              <e690:Id d4p1:nil="false">ValueHere</e690:Id>
              <e690:Name d4p1:nil="false">ValueHere</e690:Name>
            </e690:CustomerInfo>
          </e690:LinkedAgencies>
          <e690:SalesHouseCustomerId d4p1:nil="false">ValueHere</e690:SalesHouseCustomerId>
          <TaxInformation xmlns:e692="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e692:KeyValuePairOfstringstring>
              <e692:key d4p1:nil="false">ValueHere</e692:key>
              <e692:value d4p1:nil="false">ValueHere</e692:value>
            </e692:KeyValuePairOfstringstring>
          </TaxInformation>
          <e690:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e690:BackUpPaymentInstrumentId>
          <e690:BillingThresholdAmount d4p1:nil="false">ValueHere</e690:BillingThresholdAmount>
          <e690:BusinessAddress d4p1:nil="false">
            <e690:City d4p1:nil="false">ValueHere</e690:City>
            <e690:CountryCode d4p1:nil="false">ValueHere</e690:CountryCode>
            <e690:Id d4p1:nil="false">ValueHere</e690:Id>
            <e690:Line1 d4p1:nil="false">ValueHere</e690:Line1>
            <e690:Line2 d4p1:nil="false">ValueHere</e690:Line2>
            <e690:Line3 d4p1:nil="false">ValueHere</e690:Line3>
            <e690:Line4 d4p1:nil="false">ValueHere</e690:Line4>
            <e690:PostalCode d4p1:nil="false">ValueHere</e690:PostalCode>
            <e690:StateOrProvince d4p1:nil="false">ValueHere</e690:StateOrProvince>
            <e690:TimeStamp d4p1:nil="false">ValueHere</e690:TimeStamp>
          </e690:BusinessAddress>
          <e690:AutoTagType d4p1:nil="false">ValueHere</e690:AutoTagType>
        </e690:AdvertiserAccount>
      </Accounts>
    </SearchAccountsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
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
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new SearchAccountsRequest();

	$request->Predicates = $predicates;
	$request->Ordering = $ordering;
	$request->PageInfo = $pageInfo;

	return $GLOBALS['CustomerManagementProxy']->GetService()->SearchAccounts($request);
}
```
```python
response=customermanagement_service.SearchAccounts(
	Predicates=Predicates,
	Ordering=Ordering,
	PageInfo=PageInfo)
```

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

