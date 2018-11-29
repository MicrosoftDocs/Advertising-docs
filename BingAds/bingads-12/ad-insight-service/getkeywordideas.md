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
|<a name="searchparameters"></a>SearchParameters|The search parameters define your criteria and filters for the requested keyword ideas.<br/><br/>Do not try to instantiate a [SearchParameter](searchparameter.md). You can include one or more the following objects that derive from it: [CategorySearchParameter](categorysearchparameter.md), [CompetitionSearchParameter](competitionsearchparameter.md), [DateRangeSearchParameter](daterangesearchparameter.md), [DeviceSearchParameter](devicesearchparameter.md), [ExcludeAccountKeywordsSearchParameter](excludeaccountkeywordssearchparameter.md), [IdeaTextSearchParameter](ideatextsearchparameter.md), [ImpressionShareSearchParameter](impressionsharesearchparameter.md), [LanguageSearchParameter](languagesearchparameter.md), [LocationSearchParameter](locationsearchparameter.md), [NetworkSearchParameter](networksearchparameter.md), [QuerySearchParameter](querysearchparameter.md), [SearchVolumeSearchParameter](searchvolumesearchparameter.md), [SuggestedBidSearchParameter](suggestedbidsearchparameter.md) and [UrlSearchParameter](urlsearchparameter.md).<br/><br/>You cannot include duplicates of any search parameter type.<br/><br/>The list must include all of these search parameters: [LanguageSearchParameter](languagesearchparameter.md), [LocationSearchParameter](locationsearchparameter.md), and [NetworkSearchParameter](networksearchparameter.md).<br/><br/>The list must include one or more of these search parameters: [CategorySearchParameter](categorysearchparameter.md), [QuerySearchParameter](querysearchparameter.md), or [UrlSearchParameter](urlsearchparameter.md). If the *ExpandIdeas* element is false, then the [QuerySearchParameter](querysearchparameter.md) is required whether or not you included additional search parameters.<br/><br/>It can take up to 72 hours for the previous calendar month's data to be available. For example, if you request keyword ideas on August 1st, 2nd or 3rd, and July's data is not ready, the response will be based on June's data. If you do not include the [DateRangeSearchParameter](daterangesearchparameter.md) in the [GetKeywordIdeas](getkeywordideas.md) request, then you will not be able to confirm whether the first list item is data for the previous month, or the month prior. If the date range is specified and the most recent month's data is not yet available, then [GetKeywordIdeas](getkeywordideas.md) will return an error.|[SearchParameter](searchparameter.md) array|

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
      <SearchParameters xmlns:e99="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.SearchParameters" i:nil="false">
        <e99:SearchParameter i:type="-- derived type specified here with the appropriate prefix --">
          <!--This field is applicable if the derived type attribute is set to QuerySearchParameter-->
          <e99:Queries i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </e99:Queries>
          <!--This field is applicable if the derived type attribute is set to UrlSearchParameter-->
          <e99:Url i:nil="false">ValueHere</e99:Url>
          <!--This field is applicable if the derived type attribute is set to CategorySearchParameter-->
          <e99:CategoryId>ValueHere</e99:CategoryId>
          <!--These fields are applicable if the derived type attribute is set to SearchVolumeSearchParameter-->
          <e99:Maximum i:nil="false">ValueHere</e99:Maximum>
          <e99:Minimum i:nil="false">ValueHere</e99:Minimum>
          <!--These fields are applicable if the derived type attribute is set to SuggestedBidSearchParameter-->
          <e99:Maximum i:nil="false">ValueHere</e99:Maximum>
          <e99:Minimum i:nil="false">ValueHere</e99:Minimum>
          <!--These fields are applicable if the derived type attribute is set to IdeaTextSearchParameter-->
          <e99:Excluded xmlns:e100="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" i:nil="false">
            <e100:Keyword>
              <e100:Id i:nil="false">ValueHere</e100:Id>
              <e100:MatchType>ValueHere</e100:MatchType>
              <e100:Text i:nil="false">ValueHere</e100:Text>
            </e100:Keyword>
          </e99:Excluded>
          <e99:Included xmlns:e101="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" i:nil="false">
            <e101:Keyword>
              <e101:Id i:nil="false">ValueHere</e101:Id>
              <e101:MatchType>ValueHere</e101:MatchType>
              <e101:Text i:nil="false">ValueHere</e101:Text>
            </e101:Keyword>
          </e99:Included>
          <!--This field is applicable if the derived type attribute is set to ExcludeAccountKeywordsSearchParameter-->
          <e99:ExcludeAccountKeywords>ValueHere</e99:ExcludeAccountKeywords>
          <!--These fields are applicable if the derived type attribute is set to ImpressionShareSearchParameter-->
          <e99:Maximum i:nil="false">ValueHere</e99:Maximum>
          <e99:Minimum i:nil="false">ValueHere</e99:Minimum>
          <!--This field is applicable if the derived type attribute is set to LocationSearchParameter-->
          <e99:Locations xmlns:e102="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e102:LocationCriterion>
              <e102:LocationId>ValueHere</e102:LocationId>
            </e102:LocationCriterion>
          </e99:Locations>
          <!--This field is applicable if the derived type attribute is set to NetworkSearchParameter-->
          <e99:Network xmlns:e103="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e103:Network>ValueHere</e103:Network>
          </e99:Network>
          <!--This field is applicable if the derived type attribute is set to DeviceSearchParameter-->
          <e99:Device xmlns:e104="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e104:DeviceName i:nil="false">ValueHere</e104:DeviceName>
          </e99:Device>
          <!--This field is applicable if the derived type attribute is set to LanguageSearchParameter-->
          <e99:Languages xmlns:e105="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e105:LanguageCriterion>
              <e105:Language i:nil="false">ValueHere</e105:Language>
            </e105:LanguageCriterion>
          </e99:Languages>
          <!--This field is applicable if the derived type attribute is set to CompetitionSearchParameter-->
          <e99:CompetitionLevels i:nil="false">
            <CompetitionLevel>ValueHere</CompetitionLevel>
          </e99:CompetitionLevels>
          <!--These fields are applicable if the derived type attribute is set to DateRangeSearchParameter-->
          <e99:EndDate xmlns:e106="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" i:nil="false">
            <e106:Day>ValueHere</e106:Day>
            <e106:Month>ValueHere</e106:Month>
            <e106:Year>ValueHere</e106:Year>
          </e99:EndDate>
          <e99:StartDate xmlns:e107="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" i:nil="false">
            <e107:Day>ValueHere</e107:Day>
            <e107:Month>ValueHere</e107:Month>
            <e107:Year>ValueHere</e107:Year>
          </e99:StartDate>
          <!--This field is applicable if the derived type attribute is set to AuctionSegmentSearchParameter-->
          <e99:Segment>ValueHere</e99:Segment>
        </e99:SearchParameter>
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
      <KeywordIdeas xmlns:e108="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e108:KeywordIdea>
          <e108:AdGroupId d4p1:nil="false">ValueHere</e108:AdGroupId>
          <e108:AdGroupName d4p1:nil="false">ValueHere</e108:AdGroupName>
          <e108:AdImpressionShare d4p1:nil="false">ValueHere</e108:AdImpressionShare>
          <e108:Competition d4p1:nil="false">ValueHere</e108:Competition>
          <e108:Keyword d4p1:nil="false">ValueHere</e108:Keyword>
          <e108:MonthlySearchCounts d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </e108:MonthlySearchCounts>
          <e108:Relevance d4p1:nil="false">ValueHere</e108:Relevance>
          <e108:Source d4p1:nil="false">ValueHere</e108:Source>
          <e108:SuggestedBid d4p1:nil="false">ValueHere</e108:SuggestedBid>
        </e108:KeywordIdea>
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

