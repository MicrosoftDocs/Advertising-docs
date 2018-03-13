---
title: GetAuctionInsightData Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets auction insight data.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetAuctionInsightData Service Operation - Ad Insight
Gets auction insight data.

> [!NOTE]
> Reserved for future use.

## <a name="request"></a>Request Elements
The *GetAuctionInsightDataRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="entityids"></a>EntityIds|Reserved.|**long** array|
|<a name="entitytype"></a>EntityType|Reserved.|[EntityType](entitytype.md)|
|<a name="searchparameters"></a>SearchParameters|Reserved.|[SearchParameter](searchparameter.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAuctionInsightDataResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="result"></a>Result|Reserved.|[AuctionInsightResult](auctioninsightresult.md)|

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
      <SearchParameters xmlns:e1280="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.SearchParameters" i:nil="false">
        <e1280:SearchParameter i:type="-- derived type specified here with the appropriate prefix --">
          <!--This field is applicable if the derived type attribute is set to QuerySearchParameter-->
          <e1280:Queries i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </e1280:Queries>
          <!--This field is applicable if the derived type attribute is set to UrlSearchParameter-->
          <e1280:Url i:nil="false">ValueHere</e1280:Url>
          <!--This field is applicable if the derived type attribute is set to CategorySearchParameter-->
          <e1280:CategoryId>ValueHere</e1280:CategoryId>
          <!--These fields are applicable if the derived type attribute is set to SearchVolumeSearchParameter-->
          <e1280:Maximum i:nil="false">ValueHere</e1280:Maximum>
          <e1280:Minimum i:nil="false">ValueHere</e1280:Minimum>
          <!--These fields are applicable if the derived type attribute is set to SuggestedBidSearchParameter-->
          <e1280:Maximum i:nil="false">ValueHere</e1280:Maximum>
          <e1280:Minimum i:nil="false">ValueHere</e1280:Minimum>
          <!--These fields are applicable if the derived type attribute is set to IdeaTextSearchParameter-->
          <Excluded xmlns:e1281="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" i:nil="false">
            <e1281:Keyword>
              <e1281:Id i:nil="false">ValueHere</e1281:Id>
              <e1281:MatchType>ValueHere</e1281:MatchType>
              <e1281:Text i:nil="false">ValueHere</e1281:Text>
            </e1281:Keyword>
          </Excluded>
          <Included xmlns:e1282="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" i:nil="false">
            <e1282:Keyword>
              <e1282:Id i:nil="false">ValueHere</e1282:Id>
              <e1282:MatchType>ValueHere</e1282:MatchType>
              <e1282:Text i:nil="false">ValueHere</e1282:Text>
            </e1282:Keyword>
          </Included>
          <!--This field is applicable if the derived type attribute is set to ExcludeAccountKeywordsSearchParameter-->
          <e1280:ExcludeAccountKeywords>ValueHere</e1280:ExcludeAccountKeywords>
          <!--These fields are applicable if the derived type attribute is set to ImpressionShareSearchParameter-->
          <e1280:Maximum i:nil="false">ValueHere</e1280:Maximum>
          <e1280:Minimum i:nil="false">ValueHere</e1280:Minimum>
          <!--This field is applicable if the derived type attribute is set to LocationSearchParameter-->
          <Locations xmlns:e1283="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e1283:LocationCriterion>
              <e1283:LocationId>ValueHere</e1283:LocationId>
            </e1283:LocationCriterion>
          </Locations>
          <!--This field is applicable if the derived type attribute is set to NetworkSearchParameter-->
          <Network xmlns:e1284="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e1284:Network>ValueHere</e1284:Network>
          </Network>
          <!--This field is applicable if the derived type attribute is set to DeviceSearchParameter-->
          <Device xmlns:e1285="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e1285:DeviceName i:nil="false">ValueHere</e1285:DeviceName>
          </Device>
          <!--This field is applicable if the derived type attribute is set to LanguageSearchParameter-->
          <Languages xmlns:e1286="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e1286:LanguageCriterion>
              <e1286:Language i:nil="false">ValueHere</e1286:Language>
            </e1286:LanguageCriterion>
          </Languages>
          <!--This field is applicable if the derived type attribute is set to CompetitionSearchParameter-->
          <e1280:CompetitionLevels i:nil="false">
            <CompetitionLevel>ValueHere</CompetitionLevel>
          </e1280:CompetitionLevels>
          <!--These fields are applicable if the derived type attribute is set to DateRangeSearchParameter-->
          <EndDate xmlns:e1287="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" i:nil="false">
            <e1287:Day>ValueHere</e1287:Day>
            <e1287:Month>ValueHere</e1287:Month>
            <e1287:Year>ValueHere</e1287:Year>
          </EndDate>
          <StartDate xmlns:e1288="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" i:nil="false">
            <e1288:Day>ValueHere</e1288:Day>
            <e1288:Month>ValueHere</e1288:Month>
            <e1288:Year>ValueHere</e1288:Year>
          </StartDate>
          <!--This field is applicable if the derived type attribute is set to AuctionSegmentSearchParameter-->
          <e1280:Segment>ValueHere</e1280:Segment>
        </e1280:SearchParameter>
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
      <Result xmlns:e1289="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1289:Segment d4p1:nil="false">ValueHere</e1289:Segment>
        <e1289:Entries d4p1:nil="false">
          <e1289:AuctionInsightEntry>
            <e1289:DisplayDomain d4p1:nil="false">ValueHere</e1289:DisplayDomain>
            <e1289:AggregatedKpi d4p1:nil="false">
              <e1289:Segment d4p1:nil="false">ValueHere</e1289:Segment>
              <e1289:ImpressionShare>ValueHere</e1289:ImpressionShare>
              <e1289:OverlapRate>ValueHere</e1289:OverlapRate>
              <e1289:AveragePosition>ValueHere</e1289:AveragePosition>
              <e1289:AboveRate>ValueHere</e1289:AboveRate>
              <e1289:TopOfPageRate>ValueHere</e1289:TopOfPageRate>
              <e1289:OutrankingShare>ValueHere</e1289:OutrankingShare>
            </e1289:AggregatedKpi>
            <e1289:SegmentedKpis d4p1:nil="false">
              <e1289:AuctionInsightKpi>
                <e1289:Segment d4p1:nil="false">ValueHere</e1289:Segment>
                <e1289:ImpressionShare>ValueHere</e1289:ImpressionShare>
                <e1289:OverlapRate>ValueHere</e1289:OverlapRate>
                <e1289:AveragePosition>ValueHere</e1289:AveragePosition>
                <e1289:AboveRate>ValueHere</e1289:AboveRate>
                <e1289:TopOfPageRate>ValueHere</e1289:TopOfPageRate>
                <e1289:OutrankingShare>ValueHere</e1289:OutrankingShare>
              </e1289:AuctionInsightKpi>
            </e1289:SegmentedKpis>
          </e1289:AuctionInsightEntry>
        </e1289:Entries>
        <e1289:UsedImpressions>ValueHere</e1289:UsedImpressions>
        <e1289:UsedKeywords>ValueHere</e1289:UsedKeywords>
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
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

