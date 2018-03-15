---
title: GetKeywordIdeaCategories Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the list of keyword idea categories.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetKeywordIdeaCategories Service Operation - Ad Insight
Gets the list of keyword idea categories.

You can use the *CategoryId* element of a [KeywordCategory](keywordcategory.md) as a part of the [CategorySearchParameter](categorysearchparameter.md) when calling the [GetKeywordIdeas](getkeywordideas.md) operation.

## <a name="request"></a>Request Elements
The *GetKeywordIdeaCategoriesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements
There are not any elements in the operation's request body.

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetKeywordIdeaCategoriesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywordideacategories"></a>KeywordIdeaCategories|The list of keyword idea categories.|[KeywordIdeaCategory](keywordideacategory.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
    <Action mustUnderstand="1">GetKeywordIdeaCategories</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetKeywordIdeaCategoriesRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12" />
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetKeywordIdeaCategoriesResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <KeywordIdeaCategories xmlns:e1660="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1660:KeywordIdeaCategory>
          <e1660:CategoryId>ValueHere</e1660:CategoryId>
          <e1660:CategoryName d4p1:nil="false">ValueHere</e1660:CategoryName>
        </e1660:KeywordIdeaCategory>
      </KeywordIdeaCategories>
    </GetKeywordIdeaCategoriesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetKeywordIdeaCategoriesResponse> GetKeywordIdeaCategoriesAsync()
{
	var request = new GetKeywordIdeaCategoriesRequest
	{
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetKeywordIdeaCategoriesAsync(r), request));
}
```
```java
static GetKeywordIdeaCategoriesResponse getKeywordIdeaCategories() throws RemoteException, Exception
{
	GetKeywordIdeaCategoriesRequest request = new GetKeywordIdeaCategoriesRequest();


	return AdInsightService.getService().getKeywordIdeaCategories(request);
}
```
```php
static function GetKeywordIdeaCategories()
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetKeywordIdeaCategoriesRequest();


	return $GLOBALS['AdInsightProxy']->GetService()->GetKeywordIdeaCategories($request);
}
```
```python
response=adinsight_service.GetKeywordIdeaCategories()
```

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

