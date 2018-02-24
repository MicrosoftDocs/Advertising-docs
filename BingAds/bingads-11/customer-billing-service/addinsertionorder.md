---
title: AddInsertionOrder Service Operation - Customer Billing
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Adds an insertion order to the specified account.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# AddInsertionOrder Service Operation - Customer Billing
Adds an insertion order to the specified account.

## <a name="request"></a>Request Elements
The *AddInsertionOrderRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="insertionorder"></a>InsertionOrder|An insertion order to add to the account.|[InsertionOrder](insertionorder.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddInsertionOrderResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="createtime"></a>CreateTime|Identifies the server time in UTC when the insertion order was added.|**dateTime**|
|<a name="insertionorderid"></a>InsertionOrderId|A *long* value that represents the identifier for the insertion order that was added.|**long**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Billing/v11">
    <Action mustUnderstand="1">AddInsertionOrder</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <AddInsertionOrderRequest xmlns="https://bingads.microsoft.com/Billing/v11">
      <InsertionOrder xmlns:e357="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e357:AccountId>ValueHere</e357:AccountId>
        <e357:BalanceAmount i:nil="false">ValueHere</e357:BalanceAmount>
        <e357:BookingCountryCode i:nil="false">ValueHere</e357:BookingCountryCode>
        <e357:Comment i:nil="false">ValueHere</e357:Comment>
        <e357:EndDate>ValueHere</e357:EndDate>
        <e357:InsertionOrderId i:nil="false">ValueHere</e357:InsertionOrderId>
        <e357:LastModifiedByUserId i:nil="false">ValueHere</e357:LastModifiedByUserId>
        <e357:LastModifiedTime i:nil="false">ValueHere</e357:LastModifiedTime>
        <e357:NotificationThreshold i:nil="false">ValueHere</e357:NotificationThreshold>
        <e357:ReferenceId i:nil="false">ValueHere</e357:ReferenceId>
        <e357:SpendCapAmount>ValueHere</e357:SpendCapAmount>
        <e357:StartDate>ValueHere</e357:StartDate>
        <e357:Name i:nil="false">ValueHere</e357:Name>
        <e357:Status i:nil="false">ValueHere</e357:Status>
        <e357:PurchaseOrder i:nil="false">ValueHere</e357:PurchaseOrder>
        <e357:ChangePendingReview i:nil="false">ValueHere</e357:ChangePendingReview>
      </InsertionOrder>
    </AddInsertionOrderRequest>
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
    <AddInsertionOrderResponse xmlns="https://bingads.microsoft.com/Billing/v11">
      <InsertionOrderId>ValueHere</InsertionOrderId>
      <CreateTime>ValueHere</CreateTime>
    </AddInsertionOrderResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<AddInsertionOrderResponse> AddInsertionOrderAsync(
	InsertionOrder insertionOrder)
{
	var request = new AddInsertionOrderRequest
	{
		InsertionOrder = insertionOrder
	};

	return (await CustomerBillingService.CallAsync((s, r) => s.AddInsertionOrderAsync(r), request));
}
```
```java
static AddInsertionOrderResponse addInsertionOrder(
	InsertionOrder insertionOrder) throws RemoteException, Exception
{
	AddInsertionOrderRequest request = new AddInsertionOrderRequest();

	request.setInsertionOrder(insertionOrder);

	return CustomerBillingService.getService().addInsertionOrder(request);
}
```
```php
static function AddInsertionOrder(
	$insertionOrder)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerBillingProxy'];

	$request = new AddInsertionOrderRequest();

	$request->InsertionOrder = $insertionOrder;

	return $GLOBALS['CustomerBillingProxy']->GetService()->AddInsertionOrder($request);
}
```
```python
response=customerbilling_service.AddInsertionOrder(
	InsertionOrder=InsertionOrder)
```

## Requirements
Service: [CustomerBillingService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v11/CustomerBillingService.svc)  
Namespace: https\://bingads.microsoft.com/Billing/v11  

