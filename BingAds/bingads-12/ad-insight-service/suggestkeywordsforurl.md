---
title: SuggestKeywordsForUrl Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Suggests the possible keywords for the content located at the specified URL.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# SuggestKeywordsForUrl Service Operation - Ad Insight
Suggests the possible keywords for the content located at the specified URL.

## <a name="request"></a>Request Elements
The *SuggestKeywordsForUrlRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="excludebrand"></a>ExcludeBrand|A value that determines whether the results exclude brand keywords. To exclude brand keywords in the result, set to true. The default is false.|**boolean**|
|<a name="language"></a>Language|The language used by the website.<br /><br />For possible values, see [Ad Languages](../guides/ad-languages.md).<br /><br />The default is English.|**string**|
|<a name="maxkeywords"></a>MaxKeywords|A positive integer value that specifies the maximum number of keywords to return. The maximum value that you can specify is 800.<br /><br />The default is 10.|**int**|
|<a name="minconfidencescore"></a>MinConfidenceScore|A filter value that limits the keywords that the service returns to those that have a confidence score that is greater than or equal to the specified score. For example, you can specify that you want the operation to return only keywords that have a confidence score of at least 80 percent (0.8).<br /><br />If null, the confidence score is not used to limit the results.|**double**|
|<a name="url"></a>Url|The URL of the webpage to scan for possible keywords. The URL can contain a maximum of 2,000 characters.|**string**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SuggestKeywordsForUrlResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywords"></a>Keywords|An array of [KeywordAndConfidence](keywordandconfidence.md) objects that contains the possible keywords found in the content of the specified URL. In addition, the object includes a score that indicates the probability that using the keyword would result in the URL being included in the results of a search query.<br /><br />The results are sorted in order from keywords with the highest confidence score to those with the lowest confidence score.|[KeywordAndConfidence](keywordandconfidence.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
    <Action mustUnderstand="1">SuggestKeywordsForUrl</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SuggestKeywordsForUrlRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <Url i:nil="false">ValueHere</Url>
      <Language i:nil="false">ValueHere</Language>
      <MaxKeywords i:nil="false">ValueHere</MaxKeywords>
      <MinConfidenceScore i:nil="false">ValueHere</MinConfidenceScore>
      <ExcludeBrand i:nil="false">ValueHere</ExcludeBrand>
    </SuggestKeywordsForUrlRequest>
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
    <SuggestKeywordsForUrlResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <Keywords xmlns:e1327="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1327:KeywordAndConfidence>
          <e1327:SuggestedKeyword d4p1:nil="false">ValueHere</e1327:SuggestedKeyword>
          <e1327:ConfidenceScore>ValueHere</e1327:ConfidenceScore>
        </e1327:KeywordAndConfidence>
      </Keywords>
    </SuggestKeywordsForUrlResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<SuggestKeywordsForUrlResponse> SuggestKeywordsForUrlAsync(
	string url,
	string language,
	int? maxKeywords,
	double? minConfidenceScore,
	bool? excludeBrand)
{
	var request = new SuggestKeywordsForUrlRequest
	{
		Url = url,
		Language = language,
		MaxKeywords = maxKeywords,
		MinConfidenceScore = minConfidenceScore,
		ExcludeBrand = excludeBrand
	};

	return (await AdInsightService.CallAsync((s, r) => s.SuggestKeywordsForUrlAsync(r), request));
}
```
```java
static SuggestKeywordsForUrlResponse suggestKeywordsForUrl(
	java.lang.String url,
	java.lang.String language,
	int maxKeywords,
	double minConfidenceScore,
	boolean excludeBrand) throws RemoteException, Exception
{
	SuggestKeywordsForUrlRequest request = new SuggestKeywordsForUrlRequest();

	request.setUrl(url);
	request.setLanguage(language);
	request.setMaxKeywords(maxKeywords);
	request.setMinConfidenceScore(minConfidenceScore);
	request.setExcludeBrand(excludeBrand);

	return AdInsightService.getService().suggestKeywordsForUrl(request);
}
```
```php
static function SuggestKeywordsForUrl(
	$url,
	$language,
	$maxKeywords,
	$minConfidenceScore,
	$excludeBrand)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new SuggestKeywordsForUrlRequest();

	$request->Url = $url;
	$request->Language = $language;
	$request->MaxKeywords = $maxKeywords;
	$request->MinConfidenceScore = $minConfidenceScore;
	$request->ExcludeBrand = $excludeBrand;

	return $GLOBALS['AdInsightProxy']->GetService()->SuggestKeywordsForUrl($request);
}
```
```python
response=adinsight_service.SuggestKeywordsForUrl(
	Url=Url,
	Language=Language,
	MaxKeywords=MaxKeywords,
	MinConfidenceScore=MinConfidenceScore,
	ExcludeBrand=ExcludeBrand)
```

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

