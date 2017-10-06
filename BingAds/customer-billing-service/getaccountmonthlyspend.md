---
title: GetAccountMonthlySpend Service Operation
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the amount spent by the account in the specified month.
---
# GetAccountMonthlySpend Service Operation
Gets the amount spent by the account in the specified month.

## <a name="request"></a>Request Elements
The *GetAccountMonthlySpendRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account that contains the spend information to get.<br /><br />The account must use the invoice payment method; credit card accounts are not supported.<br /><br />The account must be a Yahoo!-managed account.<br /><br />If the account identifier belongs to a reseller, the operation sums the account balances for all the accounts of all the customers that the reseller manages. If the reseller has ten customers and each customer has ten accounts, the operation returns the sum of the monthly spend of all 100 accounts. To get the monthly spend of a single account of a customer that the reseller manages, set the *AccountId* element to the specified account identifier. To get the monthly spend of all the accounts of a customer that the reseller manages, call this operation for each account, and then sum the monthly spend amounts.|**long**|
|<a name="monthyear"></a>MonthYear|The month and year for which you want to get the monthly spend information (the operation ignores the day and time values).  **Note**: The service uses the month and year components corresponding to the specified *dateTime*. For example 2013-06-15T00:00:00 and 2013-06 are both valid and will return the same results.<br /><br />If you specify the current month, the operation returns the month-to-date spend amount. For example, if the current date is June 15, 2013 and you set *MonthYear* to June 2013, the operation returns the spend amount for June 1 to June 15, inclusively.<br /><br />You cannot specify a future month and year. If you specify a prior month for which there is no data, the call returns 0 (zero).<br /><br />The spend amount can span multiple insertion orders (IOs). If the credits are greater than the actual spend, the returned monthly spend amount is a negative value.|**dateTime**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAccountMonthlySpendResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="amount"></a>Amount|The amount spent by the account in the specified period.<br /><br />The account must be Yahoo!-managed.<br /><br />If the account is not Yahoo!-managed, the return value is 0.|**double**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Billing/v11">
    <Action mustUnderstand="1">GetAccountMonthlySpend</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAccountMonthlySpendRequest xmlns="https://bingads.microsoft.com/Billing/v11">
      <AccountId>ValueHere</AccountId>
      <MonthYear>ValueHere</MonthYear>
    </GetAccountMonthlySpendRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Billing/v11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetAccountMonthlySpendResponse xmlns="https://bingads.microsoft.com/Billing/v11">
      <Amount>ValueHere</Amount>
    </GetAccountMonthlySpendResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetAccountMonthlySpendResponse> GetAccountMonthlySpendAsync(
	long accountId,
	DateTime monthYear)
{
	var request = new GetAccountMonthlySpendRequest
	{
		AccountId = accountId,
		MonthYear = monthYear
	};

	return (await CustomerBilling.CallAsync((s, r) => s.GetAccountMonthlySpendAsync(r), request));
}
```
```java
static GetAccountMonthlySpendResponse getAccountMonthlySpend(
	java.lang.Long accountId,
	Calendar monthYear) throws RemoteException, Exception
{
	GetAccountMonthlySpendRequest request = new GetAccountMonthlySpendRequest();

	request.setAccountId(accountId);
	request.setMonthYear(monthYear);

	return CustomerBilling.getService().getAccountMonthlySpend(request);
}
```
```php
static function GetAccountMonthlySpend(
	$accountId,
	$monthYear)

	$getAccountMonthlySpendRequest = new GetAccountMonthlySpendRequest();

	$request->AccountId = $accountId;
	$request->MonthYear = $monthYear;

	return $CustomerBillingProxy->GetService()->GetAccountMonthlySpend($request);
}
```
```python
response=customerbilling.GetAccountMonthlySpend(
	AccountId=AccountIdHere,
	MonthYear=MonthYearHere
)
```

## Requirements
Service: [CustomerBillingService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v11/CustomerBillingService.svc)  
Namespace: https://bingads.microsoft.com/Billing/v11  

