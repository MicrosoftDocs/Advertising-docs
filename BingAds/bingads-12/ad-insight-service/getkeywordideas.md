---
title: GetKeywordIdeas Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the list of keyword ideas.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetKeywordIdeas Service Operation - Ad Insight
Gets the list of keyword ideas.

Suggests new ad groups and keywords based on your existing keywords, website, and product category. You can also request historical statistics for keywords e.g., monthly searches, competition, average CPC, and ad impression share. You can use the returned suggested keyword bids as input to the [GetKeywordTrafficEstimates](getkeywordtrafficestimates.md) operation.

## <a name="request"></a>Request Elements
The *GetKeywordIdeasRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="expandideas"></a>ExpandIdeas|Determines whether you want new keyword ideas, or if you only want keyword attributes for the set of keywords that you specified in the *SearchParameters* list. If you set this element false, the [QuerySearchParameter](querysearchparameter.md) object must be included in the *SearchParameters* list. |**boolean**|
|<a name="ideaattributes"></a>IdeaAttributes|The keyword idea attributes that you want included in the response e.g., *Keyword*, *Competition*, *MonthlySearchCounts*, and *SuggestedBid*.<br/><br/>The *Competition* attribute is required.<br/><br/>The *Keyword* attribute will always be returned for each returned [KeywordIdea](keywordidea.md) whether or not you include the *Keyword* value in the requested list of idea attributes.|[KeywordIdeaAttribute](keywordideaattribute.md) array|
|<a name="searchparameters"></a>SearchParameters|The search parameters define your criteria and filters for the requested keyword ideas.<br/><br/>Do not try to instantiate a [SearchParameter](searchparameter.md). You can include one or more the following objects that derive from it: [CategorySearchParameter](categorysearchparameter.md), [CompetitionSearchParameter](competitionsearchparameter.md), [DateRangeSearchParameter](daterangesearchparameter.md), [DeviceSearchParameter](devicesearchparameter.md), [ExcludeAccountKeywordsSearchParameter](excludeaccountkeywordssearchparameter.md), [IdeaTextSearchParameter](ideatextsearchparameter.md), [ImpressionShareSearchParameter](impressionsharesearchparameter.md), [LanguageSearchParameter](languagesearchparameter.md), [LocationSearchParameter](locationsearchparameter.md), [NetworkSearchParameter](networksearchparameter.md), [QuerySearchParameter](querysearchparameter.md), [SearchVolumeSearchParameter](searchvolumesearchparameter.md), [SuggestedBidSearchParameter](suggestedbidsearchparameter.md) and [UrlSearchParameter](urlsearchparameter.md). Other objects that derive from [SearchParameter](searchparameter.md) are not valid for this operation.<br/><br/>You cannot include duplicates of any search parameter type.<br/><br/>The list must include all of these search parameters: [LanguageSearchParameter](languagesearchparameter.md), [LocationSearchParameter](locationsearchparameter.md), and [NetworkSearchParameter](networksearchparameter.md).<br/><br/>The list must include one or more of these search parameters: [CategorySearchParameter](categorysearchparameter.md), [QuerySearchParameter](querysearchparameter.md), or [UrlSearchParameter](urlsearchparameter.md). If the *ExpandIdeas* element is false, then the [QuerySearchParameter](querysearchparameter.md) is required whether or not you included additional search parameters.<br/><br/>It can take up to 72 hours for the previous calendar month's data to be available. For example, if you request keyword ideas on August 1st, 2nd or 3rd, and July's data is not ready, the response will be based on June's data. If you do not include the [DateRangeSearchParameter](daterangesearchparameter.md) in the [GetKeywordIdeas](getkeywordideas.md) request, then you will not be able to confirm whether the first list item is data for the previous month, or the month prior. If the date range is specified and the most recent month's data is not yet available, then [GetKeywordIdeas](getkeywordideas.md) will return an error.|[SearchParameter](searchparameter.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetKeywordIdeasResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywordideas"></a>KeywordIdeas|The list of keyword ideas.|[KeywordIdea](keywordidea.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-header) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
    <Action mustUnderstand="1">GetKeywordIdeas</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <GetKeywordIdeasRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <ExpandIdeas i:nil="false">ValueHere</ExpandIdeas>
      <IdeaAttributes i:nil="false">
        <KeywordIdeaAttribute>ValueHere</KeywordIdeaAttribute>
      </IdeaAttributes>
      <SearchParameters xmlns:e333="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.SearchParameters" i:nil="false">
        <e333:SearchParameter i:type="-- derived type specified here with the appropriate prefix --">
          <!--This field is applicable if the derived type attribute is set to QuerySearchParameter-->
          <e333:Queries i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </e333:Queries>
          <!--This field is applicable if the derived type attribute is set to UrlSearchParameter-->
          <e333:Url i:nil="false">ValueHere</e333:Url>
          <!--This field is applicable if the derived type attribute is set to CategorySearchParameter-->
          <e333:CategoryId>ValueHere</e333:CategoryId>
          <!--These fields are applicable if the derived type attribute is set to SearchVolumeSearchParameter-->
          <e333:Maximum i:nil="false">ValueHere</e333:Maximum>
          <e333:Minimum i:nil="false">ValueHere</e333:Minimum>
          <!--These fields are applicable if the derived type attribute is set to SuggestedBidSearchParameter-->
          <e333:Maximum i:nil="false">ValueHere</e333:Maximum>
          <e333:Minimum i:nil="false">ValueHere</e333:Minimum>
          <!--These fields are applicable if the derived type attribute is set to IdeaTextSearchParameter-->
          <e333:Excluded xmlns:e334="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" i:nil="false">
            <e334:Keyword>
              <e334:Id i:nil="false">ValueHere</e334:Id>
              <e334:MatchType>ValueHere</e334:MatchType>
              <e334:Text i:nil="false">ValueHere</e334:Text>
            </e334:Keyword>
          </e333:Excluded>
          <e333:Included xmlns:e335="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" i:nil="false">
            <e335:Keyword>
              <e335:Id i:nil="false">ValueHere</e335:Id>
              <e335:MatchType>ValueHere</e335:MatchType>
              <e335:Text i:nil="false">ValueHere</e335:Text>
            </e335:Keyword>
          </e333:Included>
          <!--This field is applicable if the derived type attribute is set to ExcludeAccountKeywordsSearchParameter-->
          <e333:ExcludeAccountKeywords>ValueHere</e333:ExcludeAccountKeywords>
          <!--These fields are applicable if the derived type attribute is set to ImpressionShareSearchParameter-->
          <e333:Maximum i:nil="false">ValueHere</e333:Maximum>
          <e333:Minimum i:nil="false">ValueHere</e333:Minimum>
          <!--This field is applicable if the derived type attribute is set to LocationSearchParameter-->
          <e333:Locations xmlns:e336="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e336:LocationCriterion>
              <e336:LocationId>ValueHere</e336:LocationId>
            </e336:LocationCriterion>
          </e333:Locations>
          <!--This field is applicable if the derived type attribute is set to NetworkSearchParameter-->
          <e333:Network xmlns:e337="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e337:Network>ValueHere</e337:Network>
          </e333:Network>
          <!--This field is applicable if the derived type attribute is set to DeviceSearchParameter-->
          <e333:Device xmlns:e338="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e338:DeviceName i:nil="false">ValueHere</e338:DeviceName>
          </e333:Device>
          <!--This field is applicable if the derived type attribute is set to LanguageSearchParameter-->
          <e333:Languages xmlns:e339="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e339:LanguageCriterion>
              <e339:Language i:nil="false">ValueHere</e339:Language>
            </e339:LanguageCriterion>
          </e333:Languages>
          <!--This field is applicable if the derived type attribute is set to CompetitionSearchParameter-->
          <e333:CompetitionLevels i:nil="false">
            <CompetitionLevel>ValueHere</CompetitionLevel>
          </e333:CompetitionLevels>
          <!--These fields are applicable if the derived type attribute is set to DateRangeSearchParameter-->
          <e333:EndDate xmlns:e340="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" i:nil="false">
            <e340:Day>ValueHere</e340:Day>
            <e340:Month>ValueHere</e340:Month>
            <e340:Year>ValueHere</e340:Year>
          </e333:EndDate>
          <e333:StartDate xmlns:e341="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" i:nil="false">
            <e341:Day>ValueHere</e341:Day>
            <e341:Month>ValueHere</e341:Month>
            <e341:Year>ValueHere</e341:Year>
          </e333:StartDate>
        </e333:SearchParameter>
      </SearchParameters>
    </GetKeywordIdeasRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
This template was generated by a tool to show the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetKeywordIdeasResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <KeywordIdeas xmlns:e342="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e342:KeywordIdea>
          <e342:AdGroupId d4p1:nil="false">ValueHere</e342:AdGroupId>
          <e342:AdGroupName d4p1:nil="false">ValueHere</e342:AdGroupName>
          <e342:AdImpressionShare d4p1:nil="false">ValueHere</e342:AdImpressionShare>
          <e342:Competition d4p1:nil="false">ValueHere</e342:Competition>
          <e342:Keyword d4p1:nil="false">ValueHere</e342:Keyword>
          <e342:MonthlySearchCounts d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </e342:MonthlySearchCounts>
          <e342:Relevance d4p1:nil="false">ValueHere</e342:Relevance>
          <e342:Source d4p1:nil="false">ValueHere</e342:Source>
          <e342:SuggestedBid d4p1:nil="false">ValueHere</e342:SuggestedBid>
        </e342:KeywordIdea>
      </KeywordIdeas>
    </GetKeywordIdeasResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetKeywordIdeasResponse> GetKeywordIdeasAsync(
	bool? expandIdeas,
	IList<KeywordIdeaAttribute> ideaAttributes,
	IList<SearchParameter> searchParameters)
{
	var request = new GetKeywordIdeasRequest
	{
		ExpandIdeas = expandIdeas,
		IdeaAttributes = ideaAttributes,
		SearchParameters = searchParameters
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetKeywordIdeasAsync(r), request));
}
```
```java
static GetKeywordIdeasResponse getKeywordIdeas(
	boolean expandIdeas,
	ArrayOfKeywordIdeaAttribute ideaAttributes,
	ArrayOfSearchParameter searchParameters) throws RemoteException, Exception
{
	GetKeywordIdeasRequest request = new GetKeywordIdeasRequest();

	request.setExpandIdeas(expandIdeas);
	request.setIdeaAttributes(ideaAttributes);
	request.setSearchParameters(searchParameters);

	return AdInsightService.getService().getKeywordIdeas(request);
}
```
```php
static function GetKeywordIdeas(
	$expandIdeas,
	$ideaAttributes,
	$searchParameters)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetKeywordIdeasRequest();

	$request->ExpandIdeas = $expandIdeas;
	$request->IdeaAttributes = $ideaAttributes;
	$request->SearchParameters = $searchParameters;

	return $GLOBALS['AdInsightProxy']->GetService()->GetKeywordIdeas($request);
}
```
```python
response=adinsight_service.GetKeywordIdeas(
	ExpandIdeas=ExpandIdeas,
	IdeaAttributes=IdeaAttributes,
	SearchParameters=SearchParameters)
```

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

