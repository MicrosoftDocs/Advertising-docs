---
title: GetAuctionInsightData Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets auction insight data for an account, campaigns, ad groups, or keywords.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetAuctionInsightData Service Operation - Ad Insight
Gets auction insight data for an account, campaigns, ad groups, or keywords.

By showing you where you are succeeding and where you might be missing opportunities for improved performance, the auction insight data can help you make strategic optimization decisions.

If this is a new campaign or if you have too few impressions, the auction insight data will not be generated.

The data retention period is 180 days.

> [!NOTE]
> You must specify the account identifier in the *CustomerAccountId* header element.

## <a name="request"></a>Request Elements
The *GetAuctionInsightDataRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="entityids"></a>EntityIds|The Bing Ads identifiers for up to 200 campaigns, ad groups, or keywords.<br/><br/>This element is required for the campaign, ad group, and keyword entity types. If the [EntityType](#entitytype) is Account, this element is optional and will override the value set in the CustomerAccountId header.|**long** array|
|<a name="entitytype"></a>EntityType|The entity level that you want to request auction insight data.<br/><br/>The supported values are Account, Campaign, AdGroup, and Keyword.<br/><br/>This element is required.|[EntityType](entitytype.md)|
|<a name="searchparameters"></a>SearchParameters|The search parameters define your criteria and filters for the auction insight data.<br/><br/>You must include exactly one [DateRangeSearchParameter](daterangesearchparameter.md). In addition you can optionally include up to three different [AuctionSegmentSearchParameter](auctionsegmentsearchparameter.md) objects e.g., for Day, DayOfWeek, and Device.|[SearchParameter](searchparameter.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAuctionInsightDataResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="result"></a>Result|Includes the auction insight entries for the requested entity, date range, and segment search parameters.|[AuctionInsightResult](auctioninsightresult.md)|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
    <Action mustUnderstand="1">GetAuctionInsightData</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAuctionInsightDataRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <EntityType>ValueHere</EntityType>
      <EntityIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </EntityIds>
      <SearchParameters xmlns:e928="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.SearchParameters" i:nil="false">
        <e928:SearchParameter i:type="-- derived type specified here with the appropriate prefix --">
          <!--This field is applicable if the derived type attribute is set to QuerySearchParameter-->
          <e928:Queries i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </e928:Queries>
          <!--This field is applicable if the derived type attribute is set to UrlSearchParameter-->
          <e928:Url i:nil="false">ValueHere</e928:Url>
          <!--This field is applicable if the derived type attribute is set to CategorySearchParameter-->
          <e928:CategoryId>ValueHere</e928:CategoryId>
          <!--These fields are applicable if the derived type attribute is set to SearchVolumeSearchParameter-->
          <e928:Maximum i:nil="false">ValueHere</e928:Maximum>
          <e928:Minimum i:nil="false">ValueHere</e928:Minimum>
          <!--These fields are applicable if the derived type attribute is set to SuggestedBidSearchParameter-->
          <e928:Maximum i:nil="false">ValueHere</e928:Maximum>
          <e928:Minimum i:nil="false">ValueHere</e928:Minimum>
          <!--These fields are applicable if the derived type attribute is set to IdeaTextSearchParameter-->
          <Excluded xmlns:e929="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" i:nil="false">
            <e929:Keyword>
              <e929:Id i:nil="false">ValueHere</e929:Id>
              <e929:MatchType>ValueHere</e929:MatchType>
              <e929:Text i:nil="false">ValueHere</e929:Text>
            </e929:Keyword>
          </Excluded>
          <Included xmlns:e930="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" i:nil="false">
            <e930:Keyword>
              <e930:Id i:nil="false">ValueHere</e930:Id>
              <e930:MatchType>ValueHere</e930:MatchType>
              <e930:Text i:nil="false">ValueHere</e930:Text>
            </e930:Keyword>
          </Included>
          <!--This field is applicable if the derived type attribute is set to ExcludeAccountKeywordsSearchParameter-->
          <e928:ExcludeAccountKeywords>ValueHere</e928:ExcludeAccountKeywords>
          <!--These fields are applicable if the derived type attribute is set to ImpressionShareSearchParameter-->
          <e928:Maximum i:nil="false">ValueHere</e928:Maximum>
          <e928:Minimum i:nil="false">ValueHere</e928:Minimum>
          <!--This field is applicable if the derived type attribute is set to LocationSearchParameter-->
          <Locations xmlns:e931="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e931:LocationCriterion>
              <e931:LocationId>ValueHere</e931:LocationId>
            </e931:LocationCriterion>
          </Locations>
          <!--This field is applicable if the derived type attribute is set to NetworkSearchParameter-->
          <Network xmlns:e932="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e932:Network>ValueHere</e932:Network>
          </Network>
          <!--This field is applicable if the derived type attribute is set to DeviceSearchParameter-->
          <Device xmlns:e933="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e933:DeviceName i:nil="false">ValueHere</e933:DeviceName>
          </Device>
          <!--This field is applicable if the derived type attribute is set to LanguageSearchParameter-->
          <Languages xmlns:e934="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e934:LanguageCriterion>
              <e934:Language i:nil="false">ValueHere</e934:Language>
            </e934:LanguageCriterion>
          </Languages>
          <!--This field is applicable if the derived type attribute is set to CompetitionSearchParameter-->
          <e928:CompetitionLevels i:nil="false">
            <CompetitionLevel>ValueHere</CompetitionLevel>
          </e928:CompetitionLevels>
          <!--These fields are applicable if the derived type attribute is set to DateRangeSearchParameter-->
          <EndDate xmlns:e935="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" i:nil="false">
            <e935:Day>ValueHere</e935:Day>
            <e935:Month>ValueHere</e935:Month>
            <e935:Year>ValueHere</e935:Year>
          </EndDate>
          <StartDate xmlns:e936="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" i:nil="false">
            <e936:Day>ValueHere</e936:Day>
            <e936:Month>ValueHere</e936:Month>
            <e936:Year>ValueHere</e936:Year>
          </StartDate>
          <!--This field is applicable if the derived type attribute is set to AuctionSegmentSearchParameter-->
          <e928:Segment>ValueHere</e928:Segment>
        </e928:SearchParameter>
      </SearchParameters>
    </GetAuctionInsightDataRequest>
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
    <GetAuctionInsightDataResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <Result xmlns:e937="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e937:Segments d4p1:nil="false">
          <AuctionSegment>ValueHere</AuctionSegment>
        </e937:Segments>
        <e937:Entries d4p1:nil="false">
          <e937:AuctionInsightEntry>
            <e937:DisplayDomain d4p1:nil="false">ValueHere</e937:DisplayDomain>
            <e937:AggregatedKpi d4p1:nil="false">
              <e937:Segments d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                <a1:string>ValueHere</a1:string>
              </e937:Segments>
              <e937:ImpressionShare>ValueHere</e937:ImpressionShare>
              <e937:OverlapRate>ValueHere</e937:OverlapRate>
              <e937:AveragePosition>ValueHere</e937:AveragePosition>
              <e937:AboveRate>ValueHere</e937:AboveRate>
              <e937:TopOfPageRate>ValueHere</e937:TopOfPageRate>
              <e937:OutrankingShare>ValueHere</e937:OutrankingShare>
            </e937:AggregatedKpi>
            <e937:SegmentedKpis d4p1:nil="false">
              <e937:AuctionInsightKpi>
                <e937:Segments d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                  <a1:string>ValueHere</a1:string>
                </e937:Segments>
                <e937:ImpressionShare>ValueHere</e937:ImpressionShare>
                <e937:OverlapRate>ValueHere</e937:OverlapRate>
                <e937:AveragePosition>ValueHere</e937:AveragePosition>
                <e937:AboveRate>ValueHere</e937:AboveRate>
                <e937:TopOfPageRate>ValueHere</e937:TopOfPageRate>
                <e937:OutrankingShare>ValueHere</e937:OutrankingShare>
              </e937:AuctionInsightKpi>
            </e937:SegmentedKpis>
          </e937:AuctionInsightEntry>
        </e937:Entries>
        <e937:UsedImpressions>ValueHere</e937:UsedImpressions>
        <e937:UsedKeywords>ValueHere</e937:UsedKeywords>
      </Result>
    </GetAuctionInsightDataResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAuctionInsightDataResponse> GetAuctionInsightDataAsync(
	EntityType entityType,
	IList<long> entityIds,
	IList<SearchParameter> searchParameters)
{
	var request = new GetAuctionInsightDataRequest
	{
		EntityType = entityType,
		EntityIds = entityIds,
		SearchParameters = searchParameters
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetAuctionInsightDataAsync(r), request));
}
```
```java
static GetAuctionInsightDataResponse getAuctionInsightData(
	EntityType entityType,
	ArrayOflong entityIds,
	ArrayOfSearchParameter searchParameters) throws RemoteException, Exception
{
	GetAuctionInsightDataRequest request = new GetAuctionInsightDataRequest();

	request.setEntityType(entityType);
	request.setEntityIds(entityIds);
	request.setSearchParameters(searchParameters);

	return AdInsightService.getService().getAuctionInsightData(request);
}
```
```php
static function GetAuctionInsightData(
	$entityType,
	$entityIds,
	$searchParameters)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetAuctionInsightDataRequest();

	$request->EntityType = $entityType;
	$request->EntityIds = $entityIds;
	$request->SearchParameters = $searchParameters;

	return $GLOBALS['AdInsightProxy']->GetService()->GetAuctionInsightData($request);
}
```
```python
response=adinsight_service.GetAuctionInsightData(
	EntityType=EntityType,
	EntityIds=EntityIds,
	SearchParameters=SearchParameters)
```

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

