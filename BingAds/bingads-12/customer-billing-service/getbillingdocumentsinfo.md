---
title: GetBillingDocumentsInfo Service Operation - Customer Billing
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets a list of objects that contains billing document identification information, for example the billing document identifier, amount, and account identifier.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# GetBillingDocumentsInfo Service Operation - Customer Billing
Gets a list of objects that contains billing document identification information, for example the billing document identifier, amount, and account identifier.

## <a name="request"></a>Request Elements
The *GetBillingDocumentsInfoRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountids"></a>AccountIds|A list of identifiers of the accounts whose billing document information you want to get.|**long** array|
|<a name="enddate"></a>EndDate|The end date to use for specifying the billing documents to get.<br /><br />To specify today's date as the end date, set *EndDate* to NULL.<br /><br />The end date cannot be earlier than the start date. You must specify the date in Coordinated Universal Time (UTC).|**dateTime**|
|<a name="startdate"></a>StartDate|The start date to use for specifying the billing documents to get.<br /><br />The start date cannot be later than the end date. You must specify the date in Coordinated Universal Time (UTC).|**dateTime**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetBillingDocumentsInfoResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="billingdocumentsinfo"></a>BillingDocumentsInfo|The list of billing document information objects that were retrieved.|[BillingDocumentInfo](billingdocumentinfo.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Billing/v12">
    <Action mustUnderstand="1">GetBillingDocumentsInfo</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetBillingDocumentsInfoRequest xmlns="https://bingads.microsoft.com/Billing/v12">
      <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </AccountIds>
      <StartDate>ValueHere</StartDate>
      <EndDate i:nil="false">ValueHere</EndDate>
    </GetBillingDocumentsInfoRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Billing/v12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetBillingDocumentsInfoResponse xmlns="https://bingads.microsoft.com/Billing/v12">
      <BillingDocumentsInfo xmlns:e367="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e367:BillingDocumentInfo>
          <e367:AccountId>ValueHere</e367:AccountId>
          <e367:AccountName d4p1:nil="false">ValueHere</e367:AccountName>
          <e367:AccountNumber d4p1:nil="false">ValueHere</e367:AccountNumber>
          <e367:Amount>ValueHere</e367:Amount>
          <e367:CurrencyCode d4p1:nil="false">ValueHere</e367:CurrencyCode>
          <e367:DocumentDate d4p1:nil="false">ValueHere</e367:DocumentDate>
          <e367:DocumentId d4p1:nil="false">ValueHere</e367:DocumentId>
        </e367:BillingDocumentInfo>
      </BillingDocumentsInfo>
    </GetBillingDocumentsInfoResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetBillingDocumentsInfoResponse> GetBillingDocumentsInfoAsync(
	IList<long> accountIds,
	DateTime startDate,
	DateTime? endDate)
{
	var request = new GetBillingDocumentsInfoRequest
	{
		AccountIds = accountIds,
		StartDate = startDate,
		EndDate = endDate
	};

	return (await CustomerBillingService.CallAsync((s, r) => s.GetBillingDocumentsInfoAsync(r), request));
}
```
```java
static GetBillingDocumentsInfoResponse getBillingDocumentsInfo(
	ArrayOflong accountIds,
	Calendar startDate,
	Calendar endDate) throws RemoteException, Exception
{
	GetBillingDocumentsInfoRequest request = new GetBillingDocumentsInfoRequest();

	request.setAccountIds(accountIds);
	request.setStartDate(startDate);
	request.setEndDate(endDate);

	return CustomerBillingService.getService().getBillingDocumentsInfo(request);
}
```
```php
static function GetBillingDocumentsInfo(
	$accountIds,
	$startDate,
	$endDate)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerBillingProxy'];

	$request = new GetBillingDocumentsInfoRequest();

	$request->AccountIds = $accountIds;
	$request->StartDate = $startDate;
	$request->EndDate = $endDate;

	return $GLOBALS['CustomerBillingProxy']->GetService()->GetBillingDocumentsInfo($request);
}
```
```python
response=customerbilling_service.GetBillingDocumentsInfo(
	AccountIds=AccountIds,
	StartDate=StartDate,
	EndDate=EndDate)
```

## Requirements
Service: [CustomerBillingService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v12/CustomerBillingService.svc)  
Namespace: https\://bingads.microsoft.com/Billing/v12  

