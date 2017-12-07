---
title: SuggestKeywordsFromExistingKeywords Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Suggests keywords that could perform better than the specified keywords.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# SuggestKeywordsFromExistingKeywords Service Operation - Ad Insight
Suggests keywords that could perform better than the specified keywords.

## <a name="request"></a>Request Elements
The *SuggestKeywordsFromExistingKeywordsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group for suggested keywords.<br /><br /> This element is not yet supported and may be used to influence keyword suggestions in a future release|**long**|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign for suggested keywords.<br /><br /> This element is not yet supported and may be used to influence keyword suggestions in a future release|**long**|
|<a name="excludebrand"></a>ExcludeBrand|A value that determines whether the results exclude brand keywords. To exclude brand keywords in the result, set to true. The default is false.|**boolean**|
|<a name="keywords"></a>Keywords|An array of keywords for which you want to get suggested keywords that could perform better. The array can contain a maximum of 1,000 keywords, and each keyword can contain a maximum of 100 characters.|**string** array|
|<a name="language"></a>Language|The language in which the keyword is written.<br /><br />For possible values, see [Ad Languages](~/guides/ad-languages.md). See the [Remarks](#remarks) section below for a list of providers that are supported for each language.<br /><br />The default is English.|**string**|
|<a name="maxsuggestionsperkeyword"></a>MaxSuggestionsPerKeyword|The maximum number of keyword suggestions to return per specified keyword. If *SuggestionType* is set to 4, you can request a maximum of 200 suggestions per keyword; otherwise the maximum suggestions that you can request is 100.<br /><br />The default is 50.|**int**|
|<a name="publishercountries"></a>PublisherCountries|The country codes of the countries/regions to use as the source of data for determining the suggested keywords.<br /><br />You can specify one or more country codes. Each country that you specify must support the language that you specified in the *Language* element.<br /><br />For supported values, see the [Remarks](#remarks) section below.<br /><br />The default is all countries/regions that support the specified language.|**string** array|
|<a name="removeduplicates"></a>RemoveDuplicates|A Boolean value that determines whether to remove duplicate keywords from the list of suggested keywords. To remove duplicates, set to true. The default is false.|**boolean**|
|<a name="suggestiontype"></a>SuggestionType|The provider to use to generate the keyword suggestions. For a list of possible providers, the language and country restrictions of each provider, and the default provider by country, see the [Remarks](#remarks) section below.|**int**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SuggestKeywordsFromExistingKeywordsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywordsuggestions"></a>KeywordSuggestions|An array of [KeywordSuggestion](../ad-insight-service/keywordsuggestion.md) data objects. The array contains an item for each keyword specified in the request. The object contains a list of suggested keywords that may perform better than the specified keyword.<br /><br />For each suggested keyword, the object includes a score that indicates the probability that using the keyword would result in an ad being included in the results of a search query. If there are no suggestions for a keyword, the *SuggestionsAndConfidence* element will be null.|[KeywordSuggestion](keywordsuggestion.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
    <Action mustUnderstand="1">SuggestKeywordsFromExistingKeywords</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SuggestKeywordsFromExistingKeywordsRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <Keywords i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </Keywords>
      <Language i:nil="false">ValueHere</Language>
      <PublisherCountries i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </PublisherCountries>
      <MaxSuggestionsPerKeyword i:nil="false">ValueHere</MaxSuggestionsPerKeyword>
      <SuggestionType i:nil="false">ValueHere</SuggestionType>
      <RemoveDuplicates i:nil="false">ValueHere</RemoveDuplicates>
      <ExcludeBrand i:nil="false">ValueHere</ExcludeBrand>
      <AdGroupId i:nil="false">ValueHere</AdGroupId>
      <CampaignId i:nil="false">ValueHere</CampaignId>
    </SuggestKeywordsFromExistingKeywordsRequest>
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
    <SuggestKeywordsFromExistingKeywordsResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <KeywordSuggestions xmlns:e98="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e98:KeywordSuggestion>
          <e98:Keyword d4p1:nil="false">ValueHere</e98:Keyword>
          <e98:SuggestionsAndConfidence d4p1:nil="false">
            <e98:KeywordAndConfidence>
              <e98:SuggestedKeyword d4p1:nil="false">ValueHere</e98:SuggestedKeyword>
              <e98:ConfidenceScore>ValueHere</e98:ConfidenceScore>
            </e98:KeywordAndConfidence>
          </e98:SuggestionsAndConfidence>
        </e98:KeywordSuggestion>
      </KeywordSuggestions>
    </SuggestKeywordsFromExistingKeywordsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<SuggestKeywordsFromExistingKeywordsResponse> SuggestKeywordsFromExistingKeywordsAsync(
	IList<string> keywords,
	string language,
	IList<string> publisherCountries,
	int? maxSuggestionsPerKeyword,
	int? suggestionType,
	bool? removeDuplicates,
	bool? excludeBrand,
	long? adGroupId,
	long? campaignId)
{
	var request = new SuggestKeywordsFromExistingKeywordsRequest
	{
		Keywords = keywords,
		Language = language,
		PublisherCountries = publisherCountries,
		MaxSuggestionsPerKeyword = maxSuggestionsPerKeyword,
		SuggestionType = suggestionType,
		RemoveDuplicates = removeDuplicates,
		ExcludeBrand = excludeBrand,
		AdGroupId = adGroupId,
		CampaignId = campaignId
	};

	return (await AdInsightService.CallAsync((s, r) => s.SuggestKeywordsFromExistingKeywordsAsync(r), request));
}
```
```java
static SuggestKeywordsFromExistingKeywordsResponse suggestKeywordsFromExistingKeywords(
	ArrayOfstring keywords,
	java.lang.String language,
	ArrayOfstring publisherCountries,
	int maxSuggestionsPerKeyword,
	int suggestionType,
	boolean removeDuplicates,
	boolean excludeBrand,
	java.lang.Long adGroupId,
	java.lang.Long campaignId) throws RemoteException, Exception
{
	SuggestKeywordsFromExistingKeywordsRequest request = new SuggestKeywordsFromExistingKeywordsRequest();

	request.setKeywords(keywords);
	request.setLanguage(language);
	request.setPublisherCountries(publisherCountries);
	request.setMaxSuggestionsPerKeyword(maxSuggestionsPerKeyword);
	request.setSuggestionType(suggestionType);
	request.setRemoveDuplicates(removeDuplicates);
	request.setExcludeBrand(excludeBrand);
	request.setAdGroupId(adGroupId);
	request.setCampaignId(campaignId);

	return AdInsightService.getService().suggestKeywordsFromExistingKeywords(request);
}
```
```php
static function SuggestKeywordsFromExistingKeywords(
	$keywords,
	$language,
	$publisherCountries,
	$maxSuggestionsPerKeyword,
	$suggestionType,
	$removeDuplicates,
	$excludeBrand,
	$adGroupId,
	$campaignId)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new SuggestKeywordsFromExistingKeywordsRequest();

	$request->Keywords = $keywords;
	$request->Language = $language;
	$request->PublisherCountries = $publisherCountries;
	$request->MaxSuggestionsPerKeyword = $maxSuggestionsPerKeyword;
	$request->SuggestionType = $suggestionType;
	$request->RemoveDuplicates = $removeDuplicates;
	$request->ExcludeBrand = $excludeBrand;
	$request->AdGroupId = $adGroupId;
	$request->CampaignId = $campaignId;

	return $GLOBALS['AdInsightProxy']->GetService()->SuggestKeywordsFromExistingKeywords($request);
}
```
```python
response=adinsight_service.SuggestKeywordsFromExistingKeywords(
	Keywords=Keywords,
	Language=Language,
	PublisherCountries=PublisherCountries,
	MaxSuggestionsPerKeyword=MaxSuggestionsPerKeyword,
	SuggestionType=SuggestionType,
	RemoveDuplicates=RemoveDuplicates,
	ExcludeBrand=ExcludeBrand,
	AdGroupId=AdGroupId,
	CampaignId=CampaignId)
```

## <a name="remarks"></a>Remarks
The following are the possible suggestion providers that you can specify.

|Suggestion Type|Description|
|-------------------|---------------|
|1|Returns search queries that include the keyword.|
|2|Returns keywords from other ad groups that include the specified keyword.|
|3|Returns search queries that are related to the specified keyword.|
|4|Returns the best suggestions from the other providers.|
The following are the providers that each country supports.

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

