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
|<a name="ordering"></a>Ordering|Determines the order of results by the specified property of an account<br/><br/> You should only specify one *OrderBy* element in the array. Additional elements are not supported and will be ignored by the service.<br /><br />For this service operation, the following values are supported in the *Field* element of a *OrderBy* object.<br /><br />*Id* - The order is determined by the *Id*element of the returned [Account](bingads/customer-management-service/account.md).<br /><br />*Name* - The order is determined by the *Name* element of the returned [Account](bingads/customer-management-service/account.md).<br /><br />*Number* - The order is determined by the *Number* element of the returned [Account](bingads/customer-management-service/account.md).|[OrderBy](orderby.md) array|
|<a name="pageinfo"></a>PageInfo|Determines the index and size of  results per page.|[Paging](paging.md)|
|<a name="predicates"></a>Predicates|Determines the request conditions. This operation's response will include accounts that match all of the specified predicates.<br/><br/> With the exception of AccountLifeCycleStatus, you must specify exactly one predicate. When using the AccountLifeCycleStatus predicate field you must specify one additional predicate, for example with the *Field* set to UserId.<br /><br />For a list of supported *Field* and *Operator* elements of a [Predicate](predicate.md) object for this service operation, see [Predicate Remarks](predicate.md#remarks).|[Predicate](predicate.md) array|

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
      <Predicates xmlns:e322="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e322:Predicate>
          <e322:Field i:nil="false">ValueHere</e322:Field>
          <e322:Operator>ValueHere</e322:Operator>
          <e322:Value i:nil="false">ValueHere</e322:Value>
        </e322:Predicate>
      </Predicates>
      <Ordering xmlns:e323="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e323:OrderBy>
          <e323:Field>ValueHere</e323:Field>
          <e323:Order>ValueHere</e323:Order>
        </e323:OrderBy>
      </Ordering>
      <PageInfo xmlns:e324="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e324:Index>ValueHere</e324:Index>
        <e324:Size>ValueHere</e324:Size>
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
      <Accounts xmlns:e325="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e325:Account d4p1:type="-- derived type specified here with the appropriate prefix --">
          <e325:AccountType>ValueHere</e325:AccountType>
          <e325:BillToCustomerId d4p1:nil="false">ValueHere</e325:BillToCustomerId>
          <e325:CountryCode d4p1:nil="false">ValueHere</e325:CountryCode>
          <e325:CurrencyType d4p1:nil="false">ValueHere</e325:CurrencyType>
          <e325:AccountFinancialStatus d4p1:nil="false">ValueHere</e325:AccountFinancialStatus>
          <e325:Id d4p1:nil="false">ValueHere</e325:Id>
          <e325:Language d4p1:nil="false">ValueHere</e325:Language>
          <ForwardCompatibilityMap xmlns:e326="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e326:KeyValuePairOfstringstring>
              <e326:key d4p1:nil="false">ValueHere</e326:key>
              <e326:value d4p1:nil="false">ValueHere</e326:value>
            </e326:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <e325:LastModifiedByUserId d4p1:nil="false">ValueHere</e325:LastModifiedByUserId>
          <e325:LastModifiedTime d4p1:nil="false">ValueHere</e325:LastModifiedTime>
          <e325:Name d4p1:nil="false">ValueHere</e325:Name>
          <e325:Number d4p1:nil="false">ValueHere</e325:Number>
          <e325:ParentCustomerId>ValueHere</e325:ParentCustomerId>
          <e325:PaymentMethodId d4p1:nil="false">ValueHere</e325:PaymentMethodId>
          <e325:PaymentMethodType d4p1:nil="false">ValueHere</e325:PaymentMethodType>
          <e325:PrimaryUserId d4p1:nil="false">ValueHere</e325:PrimaryUserId>
          <e325:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e325:AccountLifeCycleStatus>
          <e325:TimeStamp d4p1:nil="false">ValueHere</e325:TimeStamp>
          <e325:TimeZone d4p1:nil="false">ValueHere</e325:TimeZone>
          <e325:PauseReason d4p1:nil="false">ValueHere</e325:PauseReason>
          <!--These fields are applicable if the derived type attribute is set to AdvertiserAccount-->
          <e325:LinkedAgencies d4p1:nil="false">
            <e325:CustomerInfo>
              <e325:Id d4p1:nil="false">ValueHere</e325:Id>
              <e325:Name d4p1:nil="false">ValueHere</e325:Name>
            </e325:CustomerInfo>
          </e325:LinkedAgencies>
          <e325:SalesHouseCustomerId d4p1:nil="false">ValueHere</e325:SalesHouseCustomerId>
          <TaxInformation xmlns:e327="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e327:KeyValuePairOfstringstring>
              <e327:key d4p1:nil="false">ValueHere</e327:key>
              <e327:value d4p1:nil="false">ValueHere</e327:value>
            </e327:KeyValuePairOfstringstring>
          </TaxInformation>
          <e325:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e325:BackUpPaymentInstrumentId>
          <e325:BillingThresholdAmount d4p1:nil="false">ValueHere</e325:BillingThresholdAmount>
          <e325:BusinessAddress d4p1:nil="false">
            <e325:City d4p1:nil="false">ValueHere</e325:City>
            <e325:CountryCode d4p1:nil="false">ValueHere</e325:CountryCode>
            <e325:Id d4p1:nil="false">ValueHere</e325:Id>
            <e325:Line1 d4p1:nil="false">ValueHere</e325:Line1>
            <e325:Line2 d4p1:nil="false">ValueHere</e325:Line2>
            <e325:Line3 d4p1:nil="false">ValueHere</e325:Line3>
            <e325:Line4 d4p1:nil="false">ValueHere</e325:Line4>
            <e325:PostalCode d4p1:nil="false">ValueHere</e325:PostalCode>
            <e325:StateOrProvince d4p1:nil="false">ValueHere</e325:StateOrProvince>
            <e325:TimeStamp d4p1:nil="false">ValueHere</e325:TimeStamp>
          </e325:BusinessAddress>
        </e325:Account>
      </Accounts>
    </SearchAccountsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](bingads/guides/client-libraries.md). See [Bing Ads Code Examples](bingads/guides/code-examples.md) for more examples.
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
Namespace: https\://bingads.microsoft.com/Customer/v11  

