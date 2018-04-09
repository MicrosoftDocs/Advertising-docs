---
title: FindAccountsOrCustomersInfo Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets a list of the accounts and customers that match the specified filter criteria.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# FindAccountsOrCustomersInfo Service Operation - Customer Management
Gets a list of the accounts and customers that match the specified filter criteria.

## <a name="request"></a>Request Elements
The *FindAccountsOrCustomersInfoRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="filter"></a>Filter|The criteria to use to filter the list of accounts and customers. You can specify either an account name, account number, or customer name.<br /><br />The filter value can contain a partial or full name or number. The operation includes the account or customer in the result if the name or number begins with the specified filter value.<br /><br />The operation performs a case-insensitive comparison when it compares your filter value to the name or number. For example, if you specify "t" as the filter value, the list will include accounts and customers whose names begin with "t" or "T".<br /><br />The operation filters first for accounts that match the filter criteria. If the number of accounts that match the filter criteria is less than the specified *TopN* value, the operation searches for customers whose name matches the filter criteria.<br /><br />Setting this element to an empty string is the same as calling the [GetAccountsInfo](getaccountsinfo.md) followed by calling the [GetCustomersInfo](getcustomersinfo.md).|**string**|
|<a name="topn"></a>TopN|A nonzero positive integer that specifies the number of accounts to return in the result. You must specify a value from 1 through 5,000.|**int**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *FindAccountsOrCustomersInfoResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountinfowithcustomerdata"></a>AccountInfoWithCustomerData|A list of *AccountInfoWithCustomerData* objects of the accounts and customers that match the specified filter criteria.<br /><br />The objects contain information that identifies the account and customer. To get the complete details of an account in the list, access the *AccountId* element of the *AccountInfoWithCustomerData* object and use it to call [GetAccount](getaccount.md) operation.<br /><br />To get the complete details of a customer in the list, access the *CustomerId* element of the *AccountInfoWithCustomerData* object and use it to call [GetCustomer](getcustomer.md).|[AccountInfoWithCustomerData](accountinfowithcustomerdata.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">FindAccountsOrCustomersInfo</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <FindAccountsOrCustomersInfoRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <Filter i:nil="false">ValueHere</Filter>
      <TopN>ValueHere</TopN>
    </FindAccountsOrCustomersInfoRequest>
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
    <FindAccountsOrCustomersInfoResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <AccountInfoWithCustomerData xmlns:e868="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e868:AccountInfoWithCustomerData>
          <e868:CustomerId d4p1:nil="false">ValueHere</e868:CustomerId>
          <e868:CustomerName d4p1:nil="false">ValueHere</e868:CustomerName>
          <e868:AccountId>ValueHere</e868:AccountId>
          <e868:AccountName d4p1:nil="false">ValueHere</e868:AccountName>
          <e868:AccountNumber d4p1:nil="false">ValueHere</e868:AccountNumber>
          <e868:AccountLifeCycleStatus>ValueHere</e868:AccountLifeCycleStatus>
          <e868:PauseReason d4p1:nil="false">ValueHere</e868:PauseReason>
        </e868:AccountInfoWithCustomerData>
      </AccountInfoWithCustomerData>
    </FindAccountsOrCustomersInfoResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<FindAccountsOrCustomersInfoResponse> FindAccountsOrCustomersInfoAsync(
	string filter,
	int topN)
{
	var request = new FindAccountsOrCustomersInfoRequest
	{
		Filter = filter,
		TopN = topN
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.FindAccountsOrCustomersInfoAsync(r), request));
}
```
```java
static FindAccountsOrCustomersInfoResponse findAccountsOrCustomersInfo(
	java.lang.String filter,
	int topN) throws RemoteException, Exception
{
	FindAccountsOrCustomersInfoRequest request = new FindAccountsOrCustomersInfoRequest();

	request.setFilter(filter);
	request.setTopN(topN);

	return CustomerManagementService.getService().findAccountsOrCustomersInfo(request);
}
```
```php
static function FindAccountsOrCustomersInfo(
	$filter,
	$topN)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new FindAccountsOrCustomersInfoRequest();

	$request->Filter = $filter;
	$request->TopN = $topN;

	return $GLOBALS['CustomerManagementProxy']->GetService()->FindAccountsOrCustomersInfo($request);
}
```
```python
response=customermanagement_service.FindAccountsOrCustomersInfo(
	Filter=Filter,
	TopN=TopN)
```

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

