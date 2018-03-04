---
title: GetInsertionOrdersByAccount Service Operation - Customer Billing
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets a list of insertion orders for the specified account.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetInsertionOrdersByAccount Service Operation - Customer Billing
Gets a list of insertion orders for the specified account.

> [!NOTE]
> This operation is deprecated and will be removed in a future API version. To get insertion orders, you should use the [SearchInsertionOrders](searchinsertionorders.md) operation.

## <a name="request"></a>Request Elements
The *GetInsertionOrdersByAccountRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account that contains the insertion orders to get.|**long**|
|<a name="insertionorderids"></a>InsertionOrderIds|A list of identifiers of the insertion orders to get. To get all insertion orders, including those that have expired, set to NULL.|**long** array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetInsertionOrdersByAccountResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="insertionorders"></a>InsertionOrders|A list of insertion orders.|[InsertionOrder](insertionorder.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Billing/v11">
    <Action mustUnderstand="1">GetInsertionOrdersByAccount</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetInsertionOrdersByAccountRequest xmlns="https://bingads.microsoft.com/Billing/v11">
      <AccountId>ValueHere</AccountId>
      <InsertionOrderIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </InsertionOrderIds>
    </GetInsertionOrdersByAccountRequest>
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
    <GetInsertionOrdersByAccountResponse xmlns="https://bingads.microsoft.com/Billing/v11">
      <InsertionOrders xmlns:e360="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e360:InsertionOrder>
          <e360:AccountId>ValueHere</e360:AccountId>
          <e360:BalanceAmount d4p1:nil="false">ValueHere</e360:BalanceAmount>
          <e360:BookingCountryCode d4p1:nil="false">ValueHere</e360:BookingCountryCode>
          <e360:Comment d4p1:nil="false">ValueHere</e360:Comment>
          <e360:EndDate>ValueHere</e360:EndDate>
          <e360:InsertionOrderId d4p1:nil="false">ValueHere</e360:InsertionOrderId>
          <e360:LastModifiedByUserId d4p1:nil="false">ValueHere</e360:LastModifiedByUserId>
          <e360:LastModifiedTime d4p1:nil="false">ValueHere</e360:LastModifiedTime>
          <e360:NotificationThreshold d4p1:nil="false">ValueHere</e360:NotificationThreshold>
          <e360:ReferenceId d4p1:nil="false">ValueHere</e360:ReferenceId>
          <e360:SpendCapAmount>ValueHere</e360:SpendCapAmount>
          <e360:StartDate>ValueHere</e360:StartDate>
          <e360:Name d4p1:nil="false">ValueHere</e360:Name>
          <e360:Status d4p1:nil="false">ValueHere</e360:Status>
          <e360:PurchaseOrder d4p1:nil="false">ValueHere</e360:PurchaseOrder>
          <e360:ChangePendingReview d4p1:nil="false">ValueHere</e360:ChangePendingReview>
        </e360:InsertionOrder>
      </InsertionOrders>
    </GetInsertionOrdersByAccountResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetInsertionOrdersByAccountResponse> GetInsertionOrdersByAccountAsync(
	long accountId,
	IList<long> insertionOrderIds)
{
	var request = new GetInsertionOrdersByAccountRequest
	{
		AccountId = accountId,
		InsertionOrderIds = insertionOrderIds
	};

	return (await CustomerBillingService.CallAsync((s, r) => s.GetInsertionOrdersByAccountAsync(r), request));
}
```
```java
static GetInsertionOrdersByAccountResponse getInsertionOrdersByAccount(
	java.lang.Long accountId,
	ArrayOflong insertionOrderIds) throws RemoteException, Exception
{
	GetInsertionOrdersByAccountRequest request = new GetInsertionOrdersByAccountRequest();

	request.setAccountId(accountId);
	request.setInsertionOrderIds(insertionOrderIds);

	return CustomerBillingService.getService().getInsertionOrdersByAccount(request);
}
```
```php
static function GetInsertionOrdersByAccount(
	$accountId,
	$insertionOrderIds)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerBillingProxy'];

	$request = new GetInsertionOrdersByAccountRequest();

	$request->AccountId = $accountId;
	$request->InsertionOrderIds = $insertionOrderIds;

	return $GLOBALS['CustomerBillingProxy']->GetService()->GetInsertionOrdersByAccount($request);
}
```
```python
response=customerbilling_service.GetInsertionOrdersByAccount(
	AccountId=AccountId,
	InsertionOrderIds=InsertionOrderIds)
```

## Requirements
Service: [CustomerBillingService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v11/CustomerBillingService.svc)  
Namespace: https\://bingads.microsoft.com/Billing/v11  

