---
title: GetKeywordIdeas Service Operation
ms.service: bing-ads-ad-insight
ms.topic: article
author: eric-urban
ms.author: eur
---
# GetKeywordIdeas Service Operation
Gets the list of keyword ideas.

Suggests new ad groups and keywords based on your existing keywords, website, and product category. You can also request historical statistics for keywords e.g., monthly searches, competition, average CPC, and ad impression share. You can use the returned suggested keyword bids as input to the [GetKeywordTrafficEstimates](../ad-insight/getkeywordtrafficestimates.md) operation.

## <a name="request"></a>Request Elements
The *GetKeywordIdeasRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="expandideas"></a>ExpandIdeas|Determines whether you want new keyword ideas, or if you only want keyword attributes for the set of keywords that you specified in the *SearchParameters* list. If you set this element false, the [QuerySearchParameter](../ad-insight/querysearchparameter.md) object must be included in the *SearchParameters* list. |**boolean**|
|<a name="ideaattributes"></a>IdeaAttributes|The keyword idea attributes that you want included in the response e.g., *Keyword*, *Competition*, *MonthlySearchCounts*, and *SuggestedBid*.<br/><br/>The *Keyword* attribute will always be returned for each returned [KeywordIdea](../ad-insight/keywordidea.md) whether or not you include the *Keyword* value in the requested list of idea attributes.|[KeywordIdeaAttribute](keywordideaattribute.md) array|
|<a name="searchparameters"></a>SearchParameters|The search parameters define your criteria and filters for the requested keyword ideas.<br/><br/>Do not try to instantiate a [SearchParameter](../ad-insight/searchparameter.md). You can include one or more the following objects that derive from it: [CategorySearchParameter](../ad-insight/categorysearchparameter.md), [CompetitionSearchParameter](../ad-insight/competitionsearchparameter.md), [DateRangeSearchParameter](../ad-insight/daterangesearchparameter.md), [DeviceSearchParameter](../ad-insight/devicesearchparameter.md), [ExcludeAccountKeywordsSearchParameter](../ad-insight/excludeaccountkeywordssearchparameter.md), [IdeaTextSearchParameter](../ad-insight/ideatextsearchparameter.md), [ImpressionShareSearchParameter](../ad-insight/impressionsharesearchparameter.md), [LanguageSearchParameter](../ad-insight/languagesearchparameter.md), [LocationSearchParameter](../ad-insight/locationsearchparameter.md), [NetworkSearchParameter](../ad-insight/networksearchparameter.md), [QuerySearchParameter](../ad-insight/querysearchparameter.md), [SearchVolumeSearchParameter](../ad-insight/searchvolumesearchparameter.md), [SuggestedBidSearchParameter](../ad-insight/suggestedbidsearchparameter.md) and [UrlSearchParameter](../ad-insight/urlsearchparameter.md).<br/><br/>You cannot include duplicates of any search parameter type.<br/><br/>The list must include all of these search parameters: [LanguageSearchParameter](../ad-insight/languagesearchparameter.md), [LocationSearchParameter](../ad-insight/locationsearchparameter.md), and [NetworkSearchParameter](../ad-insight/networksearchparameter.md).<br/><br/>The list must include one or more of these search parameters: [CategorySearchParameter](../ad-insight/categorysearchparameter.md), [QuerySearchParameter](../ad-insight/querysearchparameter.md), or [UrlSearchParameter](../ad-insight/urlsearchparameter.md). If the *ExpandIdeas* element is false, then the [QuerySearchParameter](../ad-insight/querysearchparameter.md) is required whether or not you included additional search parameters.|[SearchParameter](searchparameter.md) array|

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
      <SearchParameters xmlns:e485="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.SearchParameters" i:nil="false">
        <e485:SearchParameter i:type="-- derived type specified here with the appropriate prefix --">
          <!--This field is applicable if the derived type attribute is set to QuerySearchParameter-->
          <e485:Queries i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </e485:Queries>
          <!--This field is applicable if the derived type attribute is set to UrlSearchParameter-->
          <e485:Url i:nil="false">ValueHere</e485:Url>
          <!--This field is applicable if the derived type attribute is set to CategorySearchParameter-->
          <e485:CategoryId>ValueHere</e485:CategoryId>
          <!--These fields are applicable if the derived type attribute is set to SearchVolumeSearchParameter-->
          <e485:Maximum i:nil="false">ValueHere</e485:Maximum>
          <e485:Minimum i:nil="false">ValueHere</e485:Minimum>
          <!--These fields are applicable if the derived type attribute is set to SuggestedBidSearchParameter-->
          <e485:Maximum i:nil="false">ValueHere</e485:Maximum>
          <e485:Minimum i:nil="false">ValueHere</e485:Minimum>
          <!--These fields are applicable if the derived type attribute is set to IdeaTextSearchParameter-->
          <Excluded xmlns:e486="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" i:nil="false">
            <e486:Keyword>
              <e486:Id i:nil="false">ValueHere</e486:Id>
              <e486:MatchType>ValueHere</e486:MatchType>
              <e486:Text i:nil="false">ValueHere</e486:Text>
            </e486:Keyword>
          </Excluded>
          <Included xmlns:e487="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" i:nil="false">
            <e487:Keyword>
              <e487:Id i:nil="false">ValueHere</e487:Id>
              <e487:MatchType>ValueHere</e487:MatchType>
              <e487:Text i:nil="false">ValueHere</e487:Text>
            </e487:Keyword>
          </Included>
          <!--This field is applicable if the derived type attribute is set to ExcludeAccountKeywordsSearchParameter-->
          <e485:ExcludeAccountKeywords>ValueHere</e485:ExcludeAccountKeywords>
          <!--These fields are applicable if the derived type attribute is set to ImpressionShareSearchParameter-->
          <e485:Maximum i:nil="false">ValueHere</e485:Maximum>
          <e485:Minimum i:nil="false">ValueHere</e485:Minimum>
          <!--This field is applicable if the derived type attribute is set to LocationSearchParameter-->
          <Locations xmlns:e488="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions" i:nil="false">
            <e488:LocationCriterion>
              <e488:LocationId>ValueHere</e488:LocationId>
            </e488:LocationCriterion>
          </Locations>
          <!--This field is applicable if the derived type attribute is set to NetworkSearchParameter-->
          <Network xmlns:e489="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions" i:nil="false">
            <e489:Network>ValueHere</e489:Network>
          </Network>
          <!--This field is applicable if the derived type attribute is set to DeviceSearchParameter-->
          <Device xmlns:e490="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions" i:nil="false">
            <e490:DeviceName i:nil="false">ValueHere</e490:DeviceName>
          </Device>
          <!--This field is applicable if the derived type attribute is set to LanguageSearchParameter-->
          <Languages xmlns:e491="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions" i:nil="false">
            <e491:LanguageCriterion>
              <e491:Language i:nil="false">ValueHere</e491:Language>
            </e491:LanguageCriterion>
          </Languages>
          <!--This field is applicable if the derived type attribute is set to CompetitionSearchParameter-->
          <e485:CompetitionLevels i:nil="false">
            <CompetitionLevel>ValueHere</CompetitionLevel>
          </e485:CompetitionLevels>
          <!--These fields are applicable if the derived type attribute is set to DateRangeSearchParameter-->
          <EndDate xmlns:e492="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" i:nil="false">
            <e492:Day>ValueHere</e492:Day>
            <e492:Month>ValueHere</e492:Month>
            <e492:Year>ValueHere</e492:Year>
          </EndDate>
          <StartDate xmlns:e493="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" i:nil="false">
            <e493:Day>ValueHere</e493:Day>
            <e493:Month>ValueHere</e493:Month>
            <e493:Year>ValueHere</e493:Year>
          </StartDate>
        </e485:SearchParameter>
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
      <KeywordIdeas xmlns:e494="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e494:KeywordIdea>
          <e494:AdGroupId d4p1:nil="false">ValueHere</e494:AdGroupId>
          <e494:AdGroupName d4p1:nil="false">ValueHere</e494:AdGroupName>
          <e494:AdImpressionShare>ValueHere</e494:AdImpressionShare>
          <e494:Competition>ValueHere</e494:Competition>
          <e494:Keyword d4p1:nil="false">ValueHere</e494:Keyword>
          <e494:MonthlySearchCounts d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </e494:MonthlySearchCounts>
          <e494:Relevance>ValueHere</e494:Relevance>
          <e494:Source>ValueHere</e494:Source>
          <e494:SuggestedBid>ValueHere</e494:SuggestedBid>
        </e494:KeywordIdea>
      </KeywordIdeas>
    </GetKeywordIdeasResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
```csharp
protected async Task<GetKeywordIdeasResponse> GetKeywordIdeasAsync(
	boolean expandIdeas,
	IList<KeywordIdeaAttribute> ideaAttributes,
	IList<SearchParameter> searchParameters)
{
	var request = new GetKeywordIdeasRequest
	{
		ExpandIdeas = expandIdeas,
		IdeaAttributes = ideaAttributes,
		SearchParameters = searchParameters
	};

	return (await AdInsight.CallAsync((s, r) => s.GetKeywordIdeasAsync(r), request));
}
```
```java
static GetKeywordIdeasResponse getKeywordIdeas(
	boolean expandIdeas,
	ArrayOfKeywordIdeaAttribute ideaAttributes,
	ArrayOfSearchParameter searchParameters)
{
	GetKeywordIdeasRequest request = new GetKeywordIdeasRequest();

	request.setExpandIdeas(expandIdeas);
	request.setIdeaAttributes(ideaAttributes);
	request.setSearchParameters(searchParameters);

	return AdInsight.getService().getKeywordIdeas(request);
}
```
```php
static function GetKeywordIdeas(
	$expandIdeas,
	$ideaAttributes,
	$searchParameters)

	$getKeywordIdeasRequest = new GetKeywordIdeasRequest();

	$request->ExpandIdeas = $expandIdeas;
	$request->IdeaAttributes = $ideaAttributes;
	$request->SearchParameters = $searchParameters;

	return $AdInsightProxy->GetService()->GetKeywordIdeas($request);
}
```
```python
response=adinsight.GetKeywordIdeas(
	ExpandIdeas=ExpandIdeasHere,
	IdeaAttributes=IdeaAttributesHere,
	SearchParameters=SearchParametersHere
)
```

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

