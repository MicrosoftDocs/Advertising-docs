---
title: FindAccounts Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets a list of accounts owned by the specified customer that match the specified filter criteria.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# FindAccounts Service Operation - Customer Management
Gets a list of accounts owned by the specified customer that match the specified filter criteria.

## <a name="request"></a>Request Elements
The *FindAccountsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountfilter"></a>AccountFilter|The criteria to use to filter the list of accounts. You can specify either an account name or an account number. If your filter value is of the form, X*nnnnn*, where *nnnnn* is a series of digits, the operation filters by account number.<br /><br />The filter value can contain a partial or full account name or number of the accounts that you want to get. The operation includes the account in the result if the name or number of the account begins with the specified filter value.<br /><br />The operation performs a case-insensitive comparison when it compares your filter value to the account name or number. For example, if you specify "t" as the filter value, the list will include accounts whose names begin with "t" or "T".<br /><br />Setting this element to an empty string is the same as calling the [GetAccountsInfo](getaccountsinfo.md).|**string**|
|<a name="customerid"></a>CustomerId|The identifier of the customer whose accounts you want to get.<br /><br />If null, the operation searches for a match among all of the accounts of the customers that the user manages and owns.|**long**|
|<a name="topn"></a>TopN|A nonzero positive integer that specifies the number of accounts to return in the result. You must specify a value from 1 through 5,000.|**int**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *FindAccountsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountsinfo"></a>AccountsInfo|A list of *AccountInfo* objects of the accounts that match the specified filter criteria.<br /><br />To get the complete details of an account in the list, access the *Id* element of the *AccountInfo* object and use it to call [GetAccount](getaccount.md).|[AccountInfo](accountinfo.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">FindAccounts</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <FindAccountsRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <CustomerId i:nil="false">ValueHere</CustomerId>
      <AccountFilter i:nil="false">ValueHere</AccountFilter>
      <TopN>ValueHere</TopN>
    </FindAccountsRequest>
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
    <FindAccountsResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <AccountsInfo xmlns:e319="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e319:AccountInfo>
          <e319:Id>ValueHere</e319:Id>
          <e319:Name d4p1:nil="false">ValueHere</e319:Name>
          <e319:Number d4p1:nil="false">ValueHere</e319:Number>
          <e319:AccountLifeCycleStatus>ValueHere</e319:AccountLifeCycleStatus>
          <e319:PauseReason d4p1:nil="false">ValueHere</e319:PauseReason>
        </e319:AccountInfo>
      </AccountsInfo>
    </FindAccountsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<FindAccountsResponse> FindAccountsAsync(
	long? customerId,
	string accountFilter,
	int topN)
{
	var request = new FindAccountsRequest
	{
		CustomerId = customerId,
		AccountFilter = accountFilter,
		TopN = topN
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.FindAccountsAsync(r), request));
}
```
```java
static FindAccountsResponse findAccounts(
	java.lang.Long customerId,
	java.lang.String accountFilter,
	int topN) throws RemoteException, Exception
{
	FindAccountsRequest request = new FindAccountsRequest();

	request.setCustomerId(customerId);
	request.setAccountFilter(accountFilter);
	request.setTopN(topN);

	return CustomerManagementService.getService().findAccounts(request);
}
```
```php
static function FindAccounts(
	$customerId,
	$accountFilter,
	$topN)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new FindAccountsRequest();

	$request->CustomerId = $customerId;
	$request->AccountFilter = $accountFilter;
	$request->TopN = $topN;

	return $GLOBALS['CustomerManagementProxy']->GetService()->FindAccounts($request);
}
```
```python
response=customermanagement_service.FindAccounts(
	CustomerId=CustomerId,
	AccountFilter=AccountFilter,
	TopN=TopN)
```

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

