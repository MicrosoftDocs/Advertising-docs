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
Searches for accounts that match a specified criteria.

## <a name="request"></a>Request Elements
The *SearchAccountsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ordering"></a>Ordering|Determines the order of results by the specified property of an account<br/><br/> You should only specify one *OrderBy* element in the array. Additional elements are not supported and will be ignored by the service.<br /><br />For this service operation, the following values are supported in the *Field* element of a *OrderBy* object.<br /><br />*Id* - The order is determined by the *Id*element of the returned [Account](account.md).<br /><br />*Name* - The order is determined by the *Name* element of the returned [Account](account.md).<br /><br />*Number* - The order is determined by the *Number* element of the returned [Account](account.md).|[OrderBy](orderby.md) array|
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
      <Predicates xmlns:e1236="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e1236:Predicate>
          <e1236:Field i:nil="false">ValueHere</e1236:Field>
          <e1236:Operator>ValueHere</e1236:Operator>
          <e1236:Value i:nil="false">ValueHere</e1236:Value>
        </e1236:Predicate>
      </Predicates>
      <Ordering xmlns:e1237="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e1237:OrderBy>
          <e1237:Field>ValueHere</e1237:Field>
          <e1237:Order>ValueHere</e1237:Order>
        </e1237:OrderBy>
      </Ordering>
      <PageInfo xmlns:e1238="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e1238:Index>ValueHere</e1238:Index>
        <e1238:Size>ValueHere</e1238:Size>
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
      <Accounts xmlns:e1239="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1239:AdvertiserAccount>
          <e1239:BillToCustomerId d4p1:nil="false">ValueHere</e1239:BillToCustomerId>
          <e1239:CountryCode d4p1:nil="false">ValueHere</e1239:CountryCode>
          <e1239:CurrencyCode d4p1:nil="false">ValueHere</e1239:CurrencyCode>
          <e1239:AccountFinancialStatus d4p1:nil="false">ValueHere</e1239:AccountFinancialStatus>
          <e1239:Id d4p1:nil="false">ValueHere</e1239:Id>
          <e1239:Language d4p1:nil="false">ValueHere</e1239:Language>
          <e1239:LastModifiedByUserId d4p1:nil="false">ValueHere</e1239:LastModifiedByUserId>
          <e1239:LastModifiedTime d4p1:nil="false">ValueHere</e1239:LastModifiedTime>
          <e1239:Name d4p1:nil="false">ValueHere</e1239:Name>
          <e1239:Number d4p1:nil="false">ValueHere</e1239:Number>
          <e1239:ParentCustomerId>ValueHere</e1239:ParentCustomerId>
          <e1239:PaymentMethodId d4p1:nil="false">ValueHere</e1239:PaymentMethodId>
          <e1239:PaymentMethodType d4p1:nil="false">ValueHere</e1239:PaymentMethodType>
          <e1239:PrimaryUserId d4p1:nil="false">ValueHere</e1239:PrimaryUserId>
          <e1239:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e1239:AccountLifeCycleStatus>
          <e1239:TimeStamp d4p1:nil="false">ValueHere</e1239:TimeStamp>
          <e1239:TimeZone d4p1:nil="false">ValueHere</e1239:TimeZone>
          <e1239:PauseReason d4p1:nil="false">ValueHere</e1239:PauseReason>
          <ForwardCompatibilityMap xmlns:e1240="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1240:KeyValuePairOfstringstring>
              <e1240:key d4p1:nil="false">ValueHere</e1240:key>
              <e1240:value d4p1:nil="false">ValueHere</e1240:value>
            </e1240:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <e1239:LinkedAgencies d4p1:nil="false">
            <e1239:CustomerInfo>
              <e1239:Id d4p1:nil="false">ValueHere</e1239:Id>
              <e1239:Name d4p1:nil="false">ValueHere</e1239:Name>
            </e1239:CustomerInfo>
          </e1239:LinkedAgencies>
          <e1239:SalesHouseCustomerId d4p1:nil="false">ValueHere</e1239:SalesHouseCustomerId>
          <TaxInformation xmlns:e1241="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1241:KeyValuePairOfstringstring>
              <e1241:key d4p1:nil="false">ValueHere</e1241:key>
              <e1241:value d4p1:nil="false">ValueHere</e1241:value>
            </e1241:KeyValuePairOfstringstring>
          </TaxInformation>
          <e1239:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e1239:BackUpPaymentInstrumentId>
          <e1239:BillingThresholdAmount d4p1:nil="false">ValueHere</e1239:BillingThresholdAmount>
          <e1239:BusinessAddress d4p1:nil="false">
            <e1239:City d4p1:nil="false">ValueHere</e1239:City>
            <e1239:CountryCode d4p1:nil="false">ValueHere</e1239:CountryCode>
            <e1239:Id d4p1:nil="false">ValueHere</e1239:Id>
            <e1239:Line1 d4p1:nil="false">ValueHere</e1239:Line1>
            <e1239:Line2 d4p1:nil="false">ValueHere</e1239:Line2>
            <e1239:Line3 d4p1:nil="false">ValueHere</e1239:Line3>
            <e1239:Line4 d4p1:nil="false">ValueHere</e1239:Line4>
            <e1239:PostalCode d4p1:nil="false">ValueHere</e1239:PostalCode>
            <e1239:StateOrProvince d4p1:nil="false">ValueHere</e1239:StateOrProvince>
            <e1239:TimeStamp d4p1:nil="false">ValueHere</e1239:TimeStamp>
          </e1239:BusinessAddress>
          <e1239:AutoTagType d4p1:nil="false">ValueHere</e1239:AutoTagType>
        </e1239:AdvertiserAccount>
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

