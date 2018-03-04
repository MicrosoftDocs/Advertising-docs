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

> [!IMPORTANT] 
> If you do not request AdImpressionShare, Relevance, Source, and SuggestedBid via the IdeaAttributes element, the operation will return default values (AdImpressionShare=0; Relevance=0; Source=Unknown; SuggestedBid=0) which should not be used. To get meaningful values for each [KeywordIdea](keywordidea.md) please request these attributes. 

## <a name="request"></a>Request Elements
The *GetKeywordIdeasRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="expandideas"></a>ExpandIdeas|Determines whether you want new keyword ideas, or if you only want keyword attributes for the set of keywords that you specified in the *SearchParameters* list. If you set this element false, the [QuerySearchParameter](querysearchparameter.md) object must be included in the *SearchParameters* list. |**boolean**|
|<a name="ideaattributes"></a>IdeaAttributes|The keyword idea attributes that you want included in the response e.g., *Keyword*, *Competition*, *MonthlySearchCounts*, and *SuggestedBid*.<br/><br/>The *Competition* attribute is required.<br/><br/>The *Keyword* attribute will always be returned for each returned [KeywordIdea](keywordidea.md) whether or not you include the *Keyword* value in the requested list of idea attributes.|[KeywordIdeaAttribute](keywordideaattribute.md) array|
|<a name="searchparameters"></a>SearchParameters|The search parameters define your criteria and filters for the requested keyword ideas.<br/><br/>Do not try to instantiate a [SearchParameter](searchparameter.md). You can include one or more the following objects that derive from it: [CategorySearchParameter](categorysearchparameter.md), [CompetitionSearchParameter](competitionsearchparameter.md), [DateRangeSearchParameter](daterangesearchparameter.md), [DeviceSearchParameter](devicesearchparameter.md), [ExcludeAccountKeywordsSearchParameter](excludeaccountkeywordssearchparameter.md), [IdeaTextSearchParameter](ideatextsearchparameter.md), [ImpressionShareSearchParameter](impressionsharesearchparameter.md), [LanguageSearchParameter](languagesearchparameter.md), [LocationSearchParameter](locationsearchparameter.md), [NetworkSearchParameter](networksearchparameter.md), [QuerySearchParameter](querysearchparameter.md), [SearchVolumeSearchParameter](searchvolumesearchparameter.md), [SuggestedBidSearchParameter](suggestedbidsearchparameter.md) and [UrlSearchParameter](urlsearchparameter.md).<br/><br/>You cannot include duplicates of any search parameter type.<br/><br/>The list must include all of these search parameters: [LanguageSearchParameter](languagesearchparameter.md), [LocationSearchParameter](locationsearchparameter.md), and [NetworkSearchParameter](networksearchparameter.md).<br/><br/>The list must include one or more of these search parameters: [CategorySearchParameter](categorysearchparameter.md), [QuerySearchParameter](querysearchparameter.md), or [UrlSearchParameter](urlsearchparameter.md). If the *ExpandIdeas* element is false, then the [QuerySearchParameter](querysearchparameter.md) is required whether or not you included additional search parameters.<br/><br/> It can take up to 72 hours for the previous calendar month's data to be available. For example, if you request keyword ideas on August 1st, 2nd or 3rd, and July's data is not ready, the response will be based on June's data. If you do not include the [DateRangeSearchParameter](daterangesearchparameter.md) in the [GetKeywordIdeas](getkeywordideas.md) request, then you will not be able to confirm whether the first list item is data for the previous month, or the month prior. If the date range is specified and the most recent month's data is not yet available, then [GetKeywordIdeas](getkeywordideas.md) will return an error.|[SearchParameter](searchparameter.md) array|

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
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
    <Action mustUnderstand="1">GetKeywordIdeas</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetKeywordIdeasRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <ExpandIdeas i:nil="false">ValueHere</ExpandIdeas>
      <IdeaAttributes i:nil="false">
        <KeywordIdeaAttribute>ValueHere</KeywordIdeaAttribute>
      </IdeaAttributes>
      <SearchParameters xmlns:e385="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.SearchParameters" i:nil="false">
        <e385:SearchParameter i:type="-- derived type specified here with the appropriate prefix --">
          <!--This field is applicable if the derived type attribute is set to QuerySearchParameter-->
          <e385:Queries i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </e385:Queries>
          <!--This field is applicable if the derived type attribute is set to UrlSearchParameter-->
          <e385:Url i:nil="false">ValueHere</e385:Url>
          <!--This field is applicable if the derived type attribute is set to CategorySearchParameter-->
          <e385:CategoryId>ValueHere</e385:CategoryId>
          <!--These fields are applicable if the derived type attribute is set to SearchVolumeSearchParameter-->
          <e385:Maximum i:nil="false">ValueHere</e385:Maximum>
          <e385:Minimum i:nil="false">ValueHere</e385:Minimum>
          <!--These fields are applicable if the derived type attribute is set to SuggestedBidSearchParameter-->
          <e385:Maximum i:nil="false">ValueHere</e385:Maximum>
          <e385:Minimum i:nil="false">ValueHere</e385:Minimum>
          <!--These fields are applicable if the derived type attribute is set to IdeaTextSearchParameter-->
          <Excluded xmlns:e386="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" i:nil="false">
            <e386:Keyword>
              <e386:Id i:nil="false">ValueHere</e386:Id>
              <e386:MatchType>ValueHere</e386:MatchType>
              <e386:Text i:nil="false">ValueHere</e386:Text>
            </e386:Keyword>
          </Excluded>
          <Included xmlns:e387="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" i:nil="false">
            <e387:Keyword>
              <e387:Id i:nil="false">ValueHere</e387:Id>
              <e387:MatchType>ValueHere</e387:MatchType>
              <e387:Text i:nil="false">ValueHere</e387:Text>
            </e387:Keyword>
          </Included>
          <!--This field is applicable if the derived type attribute is set to ExcludeAccountKeywordsSearchParameter-->
          <e385:ExcludeAccountKeywords>ValueHere</e385:ExcludeAccountKeywords>
          <!--These fields are applicable if the derived type attribute is set to ImpressionShareSearchParameter-->
          <e385:Maximum i:nil="false">ValueHere</e385:Maximum>
          <e385:Minimum i:nil="false">ValueHere</e385:Minimum>
          <!--This field is applicable if the derived type attribute is set to LocationSearchParameter-->
          <Locations xmlns:e388="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions" i:nil="false">
            <e388:LocationCriterion>
              <e388:LocationId>ValueHere</e388:LocationId>
            </e388:LocationCriterion>
          </Locations>
          <!--This field is applicable if the derived type attribute is set to NetworkSearchParameter-->
          <Network xmlns:e389="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions" i:nil="false">
            <e389:Network>ValueHere</e389:Network>
          </Network>
          <!--This field is applicable if the derived type attribute is set to DeviceSearchParameter-->
          <Device xmlns:e390="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions" i:nil="false">
            <e390:DeviceName i:nil="false">ValueHere</e390:DeviceName>
          </Device>
          <!--This field is applicable if the derived type attribute is set to LanguageSearchParameter-->
          <Languages xmlns:e391="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions" i:nil="false">
            <e391:LanguageCriterion>
              <e391:Language i:nil="false">ValueHere</e391:Language>
            </e391:LanguageCriterion>
          </Languages>
          <!--This field is applicable if the derived type attribute is set to CompetitionSearchParameter-->
          <e385:CompetitionLevels i:nil="false">
            <CompetitionLevel>ValueHere</CompetitionLevel>
          </e385:CompetitionLevels>
          <!--These fields are applicable if the derived type attribute is set to DateRangeSearchParameter-->
          <EndDate xmlns:e392="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" i:nil="false">
            <e392:Day>ValueHere</e392:Day>
            <e392:Month>ValueHere</e392:Month>
            <e392:Year>ValueHere</e392:Year>
          </EndDate>
          <StartDate xmlns:e393="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" i:nil="false">
            <e393:Day>ValueHere</e393:Day>
            <e393:Month>ValueHere</e393:Month>
            <e393:Year>ValueHere</e393:Year>
          </StartDate>
        </e385:SearchParameter>
      </SearchParameters>
    </GetKeywordIdeasRequest>
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
    <GetKeywordIdeasResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <KeywordIdeas xmlns:e394="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e394:KeywordIdea>
          <e394:AdGroupId d4p1:nil="false">ValueHere</e394:AdGroupId>
          <e394:AdGroupName d4p1:nil="false">ValueHere</e394:AdGroupName>
          <e394:AdImpressionShare>ValueHere</e394:AdImpressionShare>
          <e394:Competition>ValueHere</e394:Competition>
          <e394:Keyword d4p1:nil="false">ValueHere</e394:Keyword>
          <e394:MonthlySearchCounts d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </e394:MonthlySearchCounts>
          <e394:Relevance>ValueHere</e394:Relevance>
          <e394:Source>ValueHere</e394:Source>
          <e394:SuggestedBid>ValueHere</e394:SuggestedBid>
        </e394:KeywordIdea>
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
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

