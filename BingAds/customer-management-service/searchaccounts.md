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
      <Predicates xmlns:e16="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e16:Predicate>
          <e16:Field i:nil="false">ValueHere</e16:Field>
          <e16:Operator>ValueHere</e16:Operator>
          <e16:Value i:nil="false">ValueHere</e16:Value>
        </e16:Predicate>
      </Predicates>
      <Ordering xmlns:e17="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e17:OrderBy>
          <e17:Field>ValueHere</e17:Field>
          <e17:Order>ValueHere</e17:Order>
        </e17:OrderBy>
      </Ordering>
      <PageInfo xmlns:e18="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e18:Index>ValueHere</e18:Index>
        <e18:Size>ValueHere</e18:Size>
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
      <Accounts xmlns:e19="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e19:Account d4p1:type="-- derived type specified here with the appropriate prefix --">
          <e19:AccountType>ValueHere</e19:AccountType>
          <e19:BillToCustomerId d4p1:nil="false">ValueHere</e19:BillToCustomerId>
          <e19:CountryCode d4p1:nil="false">ValueHere</e19:CountryCode>
          <e19:CurrencyType d4p1:nil="false">ValueHere</e19:CurrencyType>
          <e19:AccountFinancialStatus d4p1:nil="false">ValueHere</e19:AccountFinancialStatus>
          <e19:Id d4p1:nil="false">ValueHere</e19:Id>
          <e19:Language d4p1:nil="false">ValueHere</e19:Language>
          <ForwardCompatibilityMap xmlns:e20="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e20:KeyValuePairOfstringstring>
              <e20:key d4p1:nil="false">ValueHere</e20:key>
              <e20:value d4p1:nil="false">ValueHere</e20:value>
            </e20:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <e19:LastModifiedByUserId d4p1:nil="false">ValueHere</e19:LastModifiedByUserId>
          <e19:LastModifiedTime d4p1:nil="false">ValueHere</e19:LastModifiedTime>
          <e19:Name d4p1:nil="false">ValueHere</e19:Name>
          <e19:Number d4p1:nil="false">ValueHere</e19:Number>
          <e19:ParentCustomerId>ValueHere</e19:ParentCustomerId>
          <e19:PaymentMethodId d4p1:nil="false">ValueHere</e19:PaymentMethodId>
          <e19:PaymentMethodType d4p1:nil="false">ValueHere</e19:PaymentMethodType>
          <e19:PrimaryUserId d4p1:nil="false">ValueHere</e19:PrimaryUserId>
          <e19:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e19:AccountLifeCycleStatus>
          <e19:TimeStamp d4p1:nil="false">ValueHere</e19:TimeStamp>
          <e19:TimeZone d4p1:nil="false">ValueHere</e19:TimeZone>
          <e19:PauseReason d4p1:nil="false">ValueHere</e19:PauseReason>
          <!--These fields are applicable if the derived type attribute is set to AdvertiserAccount-->
          <e19:LinkedAgencies d4p1:nil="false">
            <e19:CustomerInfo>
              <e19:Id d4p1:nil="false">ValueHere</e19:Id>
              <e19:Name d4p1:nil="false">ValueHere</e19:Name>
            </e19:CustomerInfo>
          </e19:LinkedAgencies>
          <e19:SalesHouseCustomerId d4p1:nil="false">ValueHere</e19:SalesHouseCustomerId>
          <TaxInformation xmlns:e21="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e21:KeyValuePairOfstringstring>
              <e21:key d4p1:nil="false">ValueHere</e21:key>
              <e21:value d4p1:nil="false">ValueHere</e21:value>
            </e21:KeyValuePairOfstringstring>
          </TaxInformation>
          <e19:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e19:BackUpPaymentInstrumentId>
          <e19:BillingThresholdAmount d4p1:nil="false">ValueHere</e19:BillingThresholdAmount>
          <e19:BusinessAddress d4p1:nil="false">
            <e19:City d4p1:nil="false">ValueHere</e19:City>
            <e19:CountryCode d4p1:nil="false">ValueHere</e19:CountryCode>
            <e19:Id d4p1:nil="false">ValueHere</e19:Id>
            <e19:Line1 d4p1:nil="false">ValueHere</e19:Line1>
            <e19:Line2 d4p1:nil="false">ValueHere</e19:Line2>
            <e19:Line3 d4p1:nil="false">ValueHere</e19:Line3>
            <e19:Line4 d4p1:nil="false">ValueHere</e19:Line4>
            <e19:PostalCode d4p1:nil="false">ValueHere</e19:PostalCode>
            <e19:StateOrProvince d4p1:nil="false">ValueHere</e19:StateOrProvince>
            <e19:TimeStamp d4p1:nil="false">ValueHere</e19:TimeStamp>
          </e19:BusinessAddress>
        </e19:Account>
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
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: ```https://bingads.microsoft.com/Customer/v11```  

