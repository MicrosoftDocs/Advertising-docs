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
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# SearchAccounts Service Operation - Customer Management
Searches for accounts that match a specified criteria.

## <a name="request"></a>Request Elements
The *SearchAccountsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ordering"></a>Ordering|Determines the order of results by the specified property of an account<br/><br/> You should only specify one *OrderBy* element in the array. Additional elements are not supported and will be ignored by the service.<br /><br />For this service operation, the following values are supported in the *Field* element of a *OrderBy* object.<br /><br />*Id* - The order is determined by the *Id*element of the returned [AdvertiserAccount](advertiseraccount.md).<br /><br />*Name* - The order is determined by the *Name* element of the returned [AdvertiserAccount](advertiseraccount.md).<br /><br />*Number* - The order is determined by the *Number* element of the returned [AdvertiserAccount](advertiseraccount.md).|[OrderBy](orderby.md) array|
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
      <Predicates xmlns:e331="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e331:Predicate>
          <e331:Field i:nil="false">ValueHere</e331:Field>
          <e331:Operator>ValueHere</e331:Operator>
          <e331:Value i:nil="false">ValueHere</e331:Value>
        </e331:Predicate>
      </Predicates>
      <Ordering xmlns:e332="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e332:OrderBy>
          <e332:Field>ValueHere</e332:Field>
          <e332:Order>ValueHere</e332:Order>
        </e332:OrderBy>
      </Ordering>
      <PageInfo xmlns:e333="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e333:Index>ValueHere</e333:Index>
        <e333:Size>ValueHere</e333:Size>
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
      <Accounts xmlns:e334="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e334:AdvertiserAccount>
          <e334:BillToCustomerId d4p1:nil="false">ValueHere</e334:BillToCustomerId>
          <e334:CurrencyCode d4p1:nil="false">ValueHere</e334:CurrencyCode>
          <e334:AccountFinancialStatus d4p1:nil="false">ValueHere</e334:AccountFinancialStatus>
          <e334:Id d4p1:nil="false">ValueHere</e334:Id>
          <e334:Language d4p1:nil="false">ValueHere</e334:Language>
          <e334:LastModifiedByUserId d4p1:nil="false">ValueHere</e334:LastModifiedByUserId>
          <e334:LastModifiedTime d4p1:nil="false">ValueHere</e334:LastModifiedTime>
          <e334:Name d4p1:nil="false">ValueHere</e334:Name>
          <e334:Number d4p1:nil="false">ValueHere</e334:Number>
          <e334:ParentCustomerId>ValueHere</e334:ParentCustomerId>
          <e334:PaymentMethodId d4p1:nil="false">ValueHere</e334:PaymentMethodId>
          <e334:PaymentMethodType d4p1:nil="false">ValueHere</e334:PaymentMethodType>
          <e334:PrimaryUserId d4p1:nil="false">ValueHere</e334:PrimaryUserId>
          <e334:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e334:AccountLifeCycleStatus>
          <e334:TimeStamp d4p1:nil="false">ValueHere</e334:TimeStamp>
          <e334:TimeZone d4p1:nil="false">ValueHere</e334:TimeZone>
          <e334:PauseReason d4p1:nil="false">ValueHere</e334:PauseReason>
          <ForwardCompatibilityMap xmlns:e335="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e335:KeyValuePairOfstringstring>
              <e335:key d4p1:nil="false">ValueHere</e335:key>
              <e335:value d4p1:nil="false">ValueHere</e335:value>
            </e335:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <e334:LinkedAgencies d4p1:nil="false">
            <e334:CustomerInfo>
              <e334:Id d4p1:nil="false">ValueHere</e334:Id>
              <e334:Name d4p1:nil="false">ValueHere</e334:Name>
            </e334:CustomerInfo>
          </e334:LinkedAgencies>
          <e334:SalesHouseCustomerId d4p1:nil="false">ValueHere</e334:SalesHouseCustomerId>
          <TaxInformation xmlns:e336="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e336:KeyValuePairOfstringstring>
              <e336:key d4p1:nil="false">ValueHere</e336:key>
              <e336:value d4p1:nil="false">ValueHere</e336:value>
            </e336:KeyValuePairOfstringstring>
          </TaxInformation>
          <e334:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e334:BackUpPaymentInstrumentId>
          <e334:BillingThresholdAmount d4p1:nil="false">ValueHere</e334:BillingThresholdAmount>
          <e334:BusinessAddress d4p1:nil="false">
            <e334:City d4p1:nil="false">ValueHere</e334:City>
            <e334:CountryCode d4p1:nil="false">ValueHere</e334:CountryCode>
            <e334:Id d4p1:nil="false">ValueHere</e334:Id>
            <e334:Line1 d4p1:nil="false">ValueHere</e334:Line1>
            <e334:Line2 d4p1:nil="false">ValueHere</e334:Line2>
            <e334:Line3 d4p1:nil="false">ValueHere</e334:Line3>
            <e334:Line4 d4p1:nil="false">ValueHere</e334:Line4>
            <e334:PostalCode d4p1:nil="false">ValueHere</e334:PostalCode>
            <e334:StateOrProvince d4p1:nil="false">ValueHere</e334:StateOrProvince>
            <e334:TimeStamp d4p1:nil="false">ValueHere</e334:TimeStamp>
            <e334:BusinessName d4p1:nil="false">ValueHere</e334:BusinessName>
          </e334:BusinessAddress>
          <e334:AutoTagType d4p1:nil="false">ValueHere</e334:AutoTagType>
        </e334:AdvertiserAccount>
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

