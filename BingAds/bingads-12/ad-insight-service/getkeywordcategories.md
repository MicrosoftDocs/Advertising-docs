---
title: GetKeywordCategories Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the keyword categories to which the specified keywords belong.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetKeywordCategories Service Operation - Ad Insight

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Gets the keyword categories to which the specified keywords belong.

## <a name="request"></a>Request Elements
The *GetKeywordCategoriesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywords"></a>Keywords|An array of keywords for which you want to determine the possible keyword categories that each keyword belongs to. The array can contain a maximum of 1,000 keywords, and each keyword can contain a maximum of 100 characters.|**string** array|
|<a name="language"></a>Language|The language in which the keywords are written. You must set this element to English.|**string**|
|<a name="maxcategories"></a>MaxCategories|The number of categories to include in the results. The maximum number of categories that you can request is 5.<br /><br />The default is 5.|**int**|
|<a name="publishercountry"></a>PublisherCountry|The country code of the country/region to use as the source of the category data.<br /><br /> You must set this element to US.|**string**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetKeywordCategoriesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="result"></a>Result|An array of [KeywordCategoryResult](/bingads/ad-insight-service/keywordcategoryresult.md) data objects. Each object contains the keyword and a list of categories to which it belongs.<br /><br />The list will include an item for each keyword that you specified in the request. If the keyword category cannot be determined, the *KeywordCategories* list will contain a single [KeywordCategory](/bingads/ad-insight-service/keywordcategory.md). The value of *Category* will be Unknown Category and the value of *ConfidenceScore* will be 0.0.|[KeywordCategoryResult](keywordcategoryresult.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
    <Action mustUnderstand="1">GetKeywordCategories</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetKeywordCategoriesRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <Keywords i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </Keywords>
      <Language i:nil="false">ValueHere</Language>
      <PublisherCountry i:nil="false">ValueHere</PublisherCountry>
      <MaxCategories i:nil="false">ValueHere</MaxCategories>
    </GetKeywordCategoriesRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetKeywordCategoriesResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <Result xmlns:e747="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e747:KeywordCategoryResult>
          <e747:Keyword d4p1:nil="false">ValueHere</e747:Keyword>
          <e747:KeywordCategories d4p1:nil="false">
            <e747:KeywordCategory>
              <e747:Category d4p1:nil="false">ValueHere</e747:Category>
              <e747:ConfidenceScore>ValueHere</e747:ConfidenceScore>
            </e747:KeywordCategory>
          </e747:KeywordCategories>
        </e747:KeywordCategoryResult>
      </Result>
    </GetKeywordCategoriesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](/bingads/guides/client-libraries.md). See [Bing Ads Code Examples](/bingads/guides/code-examples.md) for more examples.
```csharp
public async Task<GetKeywordCategoriesResponse> GetKeywordCategoriesAsync(
	IList<string> keywords,
	string language,
	string publisherCountry,
	int? maxCategories)
{
	var request = new GetKeywordCategoriesRequest
	{
		Keywords = keywords,
		Language = language,
		PublisherCountry = publisherCountry,
		MaxCategories = maxCategories
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetKeywordCategoriesAsync(r), request));
}
```
```java
static GetKeywordCategoriesResponse getKeywordCategories(
	ArrayOfstring keywords,
	java.lang.String language,
	java.lang.String publisherCountry,
	int maxCategories) throws RemoteException, Exception
{
	GetKeywordCategoriesRequest request = new GetKeywordCategoriesRequest();

	request.setKeywords(keywords);
	request.setLanguage(language);
	request.setPublisherCountry(publisherCountry);
	request.setMaxCategories(maxCategories);

	return AdInsightService.getService().getKeywordCategories(request);
}
```
```php
static function GetKeywordCategories(
	$keywords,
	$language,
	$publisherCountry,
	$maxCategories)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetKeywordCategoriesRequest();

	$request->Keywords = $keywords;
	$request->Language = $language;
	$request->PublisherCountry = $publisherCountry;
	$request->MaxCategories = $maxCategories;

	return $GLOBALS['AdInsightProxy']->GetService()->GetKeywordCategories($request);
}
```
```python
response=adinsight_service.GetKeywordCategories(
	Keywords=Keywords,
	Language=Language,
	PublisherCountry=PublisherCountry,
	MaxCategories=MaxCategories)
```

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

