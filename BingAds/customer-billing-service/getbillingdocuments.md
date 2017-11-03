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
# GetBillingDocuments Service Operation - Customer Billing
Gets the specified billing documents.

> [!NOTE]
> This operation will not return billing documents associated with Yahoo!-managed accounts.

## <a name="request"></a>Request Elements
The *GetBillingDocumentsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="documentids"></a>DocumentIds|A list of identifiers of the billing documents to get. To get a list of identifiers, call the [GetBillingDocumentsInfo](../customer-billing-service/getbillingdocumentsinfo.md) operation.|**long**|
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
  <s:Header xmlns="https://bingads.microsoft.com/Billing/v11">
    <Action mustUnderstand="1">GetBillingDocuments</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetBillingDocumentsRequest xmlns="https://bingads.microsoft.com/Billing/v11">
      <DocumentIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </DocumentIds>
      <Type>ValueHere</Type>
    </GetBillingDocumentsRequest>
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
    <GetBillingDocumentsResponse xmlns="https://bingads.microsoft.com/Billing/v11">
      <BillingDocuments xmlns:e52="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e52:BillingDocument>
          <e52:Data d4p1:nil="false">ValueHere</e52:Data>
          <e52:Id>ValueHere</e52:Id>
          <e52:Type>ValueHere</e52:Type>
        </e52:BillingDocument>
      </BillingDocuments>
    </GetBillingDocumentsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetBillingDocumentsResponse> GetBillingDocumentsAsync(
	IList<long> documentIds,
	DataType type)
{
	var request = new GetBillingDocumentsRequest
	{
		DocumentIds = documentIds,
		Type = type
	};

	return (await CustomerBillingService.CallAsync((s, r) => s.GetBillingDocumentsAsync(r), request));
}
```
```java
static GetBillingDocumentsResponse getBillingDocuments(
	ArrayOflong documentIds,
	DataType type) throws RemoteException, Exception
{
	GetBillingDocumentsRequest request = new GetBillingDocumentsRequest();

	request.setDocumentIds(documentIds);
	request.setType(type);

	return CustomerBillingService.getService().getBillingDocuments(request);
}
```
```php
static function GetBillingDocuments(
	$documentIds,
	$type)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerBillingProxy'];

	$request = new GetBillingDocumentsRequest();

	$request->DocumentIds = $documentIds;
	$request->Type = $type;

	return $GLOBALS['CustomerBillingProxy']->GetService()->GetBillingDocuments($request);
}
```
```python
response=customerbilling_service.GetBillingDocuments(
	DocumentIds=DocumentIds,
	Type=Type)
```

## Requirements
Service: [CustomerBillingService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v11/CustomerBillingService.svc)  
Namespace: https://bingads.microsoft.com/Billing/v11  

