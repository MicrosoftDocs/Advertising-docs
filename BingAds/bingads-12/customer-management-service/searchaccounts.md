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
      <Predicates xmlns:e20="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e20:Predicate>
          <e20:Field i:nil="false">ValueHere</e20:Field>
          <e20:Operator>ValueHere</e20:Operator>
          <e20:Value i:nil="false">ValueHere</e20:Value>
        </e20:Predicate>
      </Predicates>
      <Ordering xmlns:e21="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e21:OrderBy>
          <e21:Field>ValueHere</e21:Field>
          <e21:Order>ValueHere</e21:Order>
        </e21:OrderBy>
      </Ordering>
      <PageInfo xmlns:e22="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e22:Index>ValueHere</e22:Index>
        <e22:Size>ValueHere</e22:Size>
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
      <Accounts xmlns:e23="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e23:AdvertiserAccount>
          <e23:BillToCustomerId d4p1:nil="false">ValueHere</e23:BillToCustomerId>
          <e23:CountryCode d4p1:nil="false">ValueHere</e23:CountryCode>
          <e23:CurrencyCode d4p1:nil="false">ValueHere</e23:CurrencyCode>
          <e23:AccountFinancialStatus d4p1:nil="false">ValueHere</e23:AccountFinancialStatus>
          <e23:Id d4p1:nil="false">ValueHere</e23:Id>
          <e23:Language d4p1:nil="false">ValueHere</e23:Language>
          <e23:LastModifiedByUserId d4p1:nil="false">ValueHere</e23:LastModifiedByUserId>
          <e23:LastModifiedTime d4p1:nil="false">ValueHere</e23:LastModifiedTime>
          <e23:Name d4p1:nil="false">ValueHere</e23:Name>
          <e23:Number d4p1:nil="false">ValueHere</e23:Number>
          <e23:ParentCustomerId>ValueHere</e23:ParentCustomerId>
          <e23:PaymentMethodId d4p1:nil="false">ValueHere</e23:PaymentMethodId>
          <e23:PaymentMethodType d4p1:nil="false">ValueHere</e23:PaymentMethodType>
          <e23:PrimaryUserId d4p1:nil="false">ValueHere</e23:PrimaryUserId>
          <e23:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e23:AccountLifeCycleStatus>
          <e23:TimeStamp d4p1:nil="false">ValueHere</e23:TimeStamp>
          <e23:TimeZone d4p1:nil="false">ValueHere</e23:TimeZone>
          <e23:PauseReason d4p1:nil="false">ValueHere</e23:PauseReason>
          <ForwardCompatibilityMap xmlns:e24="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e24:KeyValuePairOfstringstring>
              <e24:key d4p1:nil="false">ValueHere</e24:key>
              <e24:value d4p1:nil="false">ValueHere</e24:value>
            </e24:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <e23:LinkedAgencies d4p1:nil="false">
            <e23:CustomerInfo>
              <e23:Id d4p1:nil="false">ValueHere</e23:Id>
              <e23:Name d4p1:nil="false">ValueHere</e23:Name>
            </e23:CustomerInfo>
          </e23:LinkedAgencies>
          <e23:SalesHouseCustomerId d4p1:nil="false">ValueHere</e23:SalesHouseCustomerId>
          <TaxInformation xmlns:e25="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e25:KeyValuePairOfstringstring>
              <e25:key d4p1:nil="false">ValueHere</e25:key>
              <e25:value d4p1:nil="false">ValueHere</e25:value>
            </e25:KeyValuePairOfstringstring>
          </TaxInformation>
          <e23:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e23:BackUpPaymentInstrumentId>
          <e23:BillingThresholdAmount d4p1:nil="false">ValueHere</e23:BillingThresholdAmount>
          <e23:BusinessAddress d4p1:nil="false">
            <e23:City d4p1:nil="false">ValueHere</e23:City>
            <e23:CountryCode d4p1:nil="false">ValueHere</e23:CountryCode>
            <e23:Id d4p1:nil="false">ValueHere</e23:Id>
            <e23:Line1 d4p1:nil="false">ValueHere</e23:Line1>
            <e23:Line2 d4p1:nil="false">ValueHere</e23:Line2>
            <e23:Line3 d4p1:nil="false">ValueHere</e23:Line3>
            <e23:Line4 d4p1:nil="false">ValueHere</e23:Line4>
            <e23:PostalCode d4p1:nil="false">ValueHere</e23:PostalCode>
            <e23:StateOrProvince d4p1:nil="false">ValueHere</e23:StateOrProvince>
            <e23:TimeStamp d4p1:nil="false">ValueHere</e23:TimeStamp>
          </e23:BusinessAddress>
          <e23:AutoTagType d4p1:nil="false">ValueHere</e23:AutoTagType>
        </e23:AdvertiserAccount>
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

