---
title: GetBillingDocuments Service Operation - Customer Billing
ms.service: bing-ads-customer-billing-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the specified billing documents.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetBillingDocuments Service Operation - Customer Billing
Gets the specified billing documents.

## <a name="request"></a>Request Elements
The *GetBillingDocumentsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="billingdocumentsinfo"></a>BillingDocumentsInfo|Identifies the list of billing documents that you want to get.<br/><br/>Each [BillingDocumentInfo](billingdocumentinfo.md) object in the list must contain the CustomerId and DocumentId. The other properties are ignored.<br/><br/>You can include up to 25 items in the list.|[BillingDocumentInfo](billingdocumentinfo.md) array|
|<a name="type"></a>Type|The format to use to generate the billing document. For example, you can generate the billing document in PDF or XML format.|[DataType](datatype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetBillingDocumentsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="billingdocuments"></a>BillingDocuments|The list of billing documents that were retrieved.|[BillingDocument](billingdocument.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Billing/v12">
    <Action mustUnderstand="1">GetBillingDocuments</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetBillingDocumentsRequest xmlns="https://bingads.microsoft.com/Billing/v12">
      <BillingDocumentsInfo xmlns:e367="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e367:BillingDocumentInfo>
          <e367:AccountId>ValueHere</e367:AccountId>
          <e367:AccountName i:nil="false">ValueHere</e367:AccountName>
          <e367:AccountNumber i:nil="false">ValueHere</e367:AccountNumber>
          <e367:Amount>ValueHere</e367:Amount>
          <e367:CurrencyCode i:nil="false">ValueHere</e367:CurrencyCode>
          <e367:DocumentDate i:nil="false">ValueHere</e367:DocumentDate>
          <e367:DocumentId i:nil="false">ValueHere</e367:DocumentId>
          <e367:CustomerId i:nil="false">ValueHere</e367:CustomerId>
        </e367:BillingDocumentInfo>
      </BillingDocumentsInfo>
      <Type>ValueHere</Type>
    </GetBillingDocumentsRequest>
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
    <GetBillingDocumentsResponse xmlns="https://bingads.microsoft.com/Billing/v12">
      <BillingDocuments xmlns:e368="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e368:BillingDocument>
          <e368:Data d4p1:nil="false">ValueHere</e368:Data>
          <e368:Id>ValueHere</e368:Id>
          <e368:Type>ValueHere</e368:Type>
        </e368:BillingDocument>
      </BillingDocuments>
    </GetBillingDocumentsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetBillingDocumentsResponse> GetBillingDocumentsAsync(
	IList<BillingDocumentInfo> billingDocumentsInfo,
	DataType type)
{
	var request = new GetBillingDocumentsRequest
	{
		BillingDocumentsInfo = billingDocumentsInfo,
		Type = type
	};

	return (await CustomerBillingService.CallAsync((s, r) => s.GetBillingDocumentsAsync(r), request));
}
```
```java
static GetBillingDocumentsResponse getBillingDocuments(
	ArrayOfBillingDocumentInfo billingDocumentsInfo,
	DataType type) throws RemoteException, Exception
{
	GetBillingDocumentsRequest request = new GetBillingDocumentsRequest();

	request.setBillingDocumentsInfo(billingDocumentsInfo);
	request.setType(type);

	return CustomerBillingService.getService().getBillingDocuments(request);
}
```
```php
static function GetBillingDocuments(
	$billingDocumentsInfo,
	$type)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerBillingProxy'];

	$request = new GetBillingDocumentsRequest();

	$request->BillingDocumentsInfo = $billingDocumentsInfo;
	$request->Type = $type;

	return $GLOBALS['CustomerBillingProxy']->GetService()->GetBillingDocuments($request);
}
```
```python
response=customerbilling_service.GetBillingDocuments(
	BillingDocumentsInfo=BillingDocumentsInfo,
	Type=Type)
```

## Requirements
Service: [CustomerBillingService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v12/CustomerBillingService.svc)  
Namespace: https\://bingads.microsoft.com/Billing/v12  

