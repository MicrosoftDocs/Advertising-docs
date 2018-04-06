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
      <Predicates xmlns:e880="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e880:Predicate>
          <e880:Field i:nil="false">ValueHere</e880:Field>
          <e880:Operator>ValueHere</e880:Operator>
          <e880:Value i:nil="false">ValueHere</e880:Value>
        </e880:Predicate>
      </Predicates>
      <Ordering xmlns:e881="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e881:OrderBy>
          <e881:Field>ValueHere</e881:Field>
          <e881:Order>ValueHere</e881:Order>
        </e881:OrderBy>
      </Ordering>
      <PageInfo xmlns:e882="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e882:Index>ValueHere</e882:Index>
        <e882:Size>ValueHere</e882:Size>
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
      <Accounts xmlns:e883="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e883:AdvertiserAccount>
          <e883:BillToCustomerId d4p1:nil="false">ValueHere</e883:BillToCustomerId>
          <e883:CurrencyCode d4p1:nil="false">ValueHere</e883:CurrencyCode>
          <e883:AccountFinancialStatus d4p1:nil="false">ValueHere</e883:AccountFinancialStatus>
          <e883:Id d4p1:nil="false">ValueHere</e883:Id>
          <e883:Language d4p1:nil="false">ValueHere</e883:Language>
          <e883:LastModifiedByUserId d4p1:nil="false">ValueHere</e883:LastModifiedByUserId>
          <e883:LastModifiedTime d4p1:nil="false">ValueHere</e883:LastModifiedTime>
          <e883:Name d4p1:nil="false">ValueHere</e883:Name>
          <e883:Number d4p1:nil="false">ValueHere</e883:Number>
          <e883:ParentCustomerId>ValueHere</e883:ParentCustomerId>
          <e883:PaymentMethodId d4p1:nil="false">ValueHere</e883:PaymentMethodId>
          <e883:PaymentMethodType d4p1:nil="false">ValueHere</e883:PaymentMethodType>
          <e883:PrimaryUserId d4p1:nil="false">ValueHere</e883:PrimaryUserId>
          <e883:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e883:AccountLifeCycleStatus>
          <e883:TimeStamp d4p1:nil="false">ValueHere</e883:TimeStamp>
          <e883:TimeZone d4p1:nil="false">ValueHere</e883:TimeZone>
          <e883:PauseReason d4p1:nil="false">ValueHere</e883:PauseReason>
          <ForwardCompatibilityMap xmlns:e884="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e884:KeyValuePairOfstringstring>
              <e884:key d4p1:nil="false">ValueHere</e884:key>
              <e884:value d4p1:nil="false">ValueHere</e884:value>
            </e884:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <e883:LinkedAgencies d4p1:nil="false">
            <e883:CustomerInfo>
              <e883:Id d4p1:nil="false">ValueHere</e883:Id>
              <e883:Name d4p1:nil="false">ValueHere</e883:Name>
            </e883:CustomerInfo>
          </e883:LinkedAgencies>
          <e883:SalesHouseCustomerId d4p1:nil="false">ValueHere</e883:SalesHouseCustomerId>
          <TaxInformation xmlns:e885="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e885:KeyValuePairOfstringstring>
              <e885:key d4p1:nil="false">ValueHere</e885:key>
              <e885:value d4p1:nil="false">ValueHere</e885:value>
            </e885:KeyValuePairOfstringstring>
          </TaxInformation>
          <e883:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e883:BackUpPaymentInstrumentId>
          <e883:BillingThresholdAmount d4p1:nil="false">ValueHere</e883:BillingThresholdAmount>
          <e883:BusinessAddress d4p1:nil="false">
            <e883:City d4p1:nil="false">ValueHere</e883:City>
            <e883:CountryCode d4p1:nil="false">ValueHere</e883:CountryCode>
            <e883:Id d4p1:nil="false">ValueHere</e883:Id>
            <e883:Line1 d4p1:nil="false">ValueHere</e883:Line1>
            <e883:Line2 d4p1:nil="false">ValueHere</e883:Line2>
            <e883:Line3 d4p1:nil="false">ValueHere</e883:Line3>
            <e883:Line4 d4p1:nil="false">ValueHere</e883:Line4>
            <e883:PostalCode d4p1:nil="false">ValueHere</e883:PostalCode>
            <e883:StateOrProvince d4p1:nil="false">ValueHere</e883:StateOrProvince>
            <e883:TimeStamp d4p1:nil="false">ValueHere</e883:TimeStamp>
            <e883:BusinessName d4p1:nil="false">ValueHere</e883:BusinessName>
          </e883:BusinessAddress>
          <e883:AutoTagType d4p1:nil="false">ValueHere</e883:AutoTagType>
          <e883:SoldToPaymentInstrumentId d4p1:nil="false">ValueHere</e883:SoldToPaymentInstrumentId>
        </e883:AdvertiserAccount>
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

