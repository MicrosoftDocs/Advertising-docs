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
      <SearchParameters xmlns:e1632="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.SearchParameters" i:nil="false">
        <e1632:SearchParameter i:type="-- derived type specified here with the appropriate prefix --">
          <!--This field is applicable if the derived type attribute is set to QuerySearchParameter-->
          <e1632:Queries i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </e1632:Queries>
          <!--This field is applicable if the derived type attribute is set to UrlSearchParameter-->
          <e1632:Url i:nil="false">ValueHere</e1632:Url>
          <!--This field is applicable if the derived type attribute is set to CategorySearchParameter-->
          <e1632:CategoryId>ValueHere</e1632:CategoryId>
          <!--These fields are applicable if the derived type attribute is set to SearchVolumeSearchParameter-->
          <e1632:Maximum i:nil="false">ValueHere</e1632:Maximum>
          <e1632:Minimum i:nil="false">ValueHere</e1632:Minimum>
          <!--These fields are applicable if the derived type attribute is set to SuggestedBidSearchParameter-->
          <e1632:Maximum i:nil="false">ValueHere</e1632:Maximum>
          <e1632:Minimum i:nil="false">ValueHere</e1632:Minimum>
          <!--These fields are applicable if the derived type attribute is set to IdeaTextSearchParameter-->
          <Excluded xmlns:e1633="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" i:nil="false">
            <e1633:Keyword>
              <e1633:Id i:nil="false">ValueHere</e1633:Id>
              <e1633:MatchType>ValueHere</e1633:MatchType>
              <e1633:Text i:nil="false">ValueHere</e1633:Text>
            </e1633:Keyword>
          </Excluded>
          <Included xmlns:e1634="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" i:nil="false">
            <e1634:Keyword>
              <e1634:Id i:nil="false">ValueHere</e1634:Id>
              <e1634:MatchType>ValueHere</e1634:MatchType>
              <e1634:Text i:nil="false">ValueHere</e1634:Text>
            </e1634:Keyword>
          </Included>
          <!--This field is applicable if the derived type attribute is set to ExcludeAccountKeywordsSearchParameter-->
          <e1632:ExcludeAccountKeywords>ValueHere</e1632:ExcludeAccountKeywords>
          <!--These fields are applicable if the derived type attribute is set to ImpressionShareSearchParameter-->
          <e1632:Maximum i:nil="false">ValueHere</e1632:Maximum>
          <e1632:Minimum i:nil="false">ValueHere</e1632:Minimum>
          <!--This field is applicable if the derived type attribute is set to LocationSearchParameter-->
          <Locations xmlns:e1635="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e1635:LocationCriterion>
              <e1635:LocationId>ValueHere</e1635:LocationId>
            </e1635:LocationCriterion>
          </Locations>
          <!--This field is applicable if the derived type attribute is set to NetworkSearchParameter-->
          <Network xmlns:e1636="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e1636:Network>ValueHere</e1636:Network>
          </Network>
          <!--This field is applicable if the derived type attribute is set to DeviceSearchParameter-->
          <Device xmlns:e1637="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e1637:DeviceName i:nil="false">ValueHere</e1637:DeviceName>
          </Device>
          <!--This field is applicable if the derived type attribute is set to LanguageSearchParameter-->
          <Languages xmlns:e1638="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e1638:LanguageCriterion>
              <e1638:Language i:nil="false">ValueHere</e1638:Language>
            </e1638:LanguageCriterion>
          </Languages>
          <!--This field is applicable if the derived type attribute is set to CompetitionSearchParameter-->
          <e1632:CompetitionLevels i:nil="false">
            <CompetitionLevel>ValueHere</CompetitionLevel>
          </e1632:CompetitionLevels>
          <!--These fields are applicable if the derived type attribute is set to DateRangeSearchParameter-->
          <EndDate xmlns:e1639="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" i:nil="false">
            <e1639:Day>ValueHere</e1639:Day>
            <e1639:Month>ValueHere</e1639:Month>
            <e1639:Year>ValueHere</e1639:Year>
          </EndDate>
          <StartDate xmlns:e1640="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" i:nil="false">
            <e1640:Day>ValueHere</e1640:Day>
            <e1640:Month>ValueHere</e1640:Month>
            <e1640:Year>ValueHere</e1640:Year>
          </StartDate>
          <!--This field is applicable if the derived type attribute is set to AuctionSegmentSearchParameter-->
          <e1632:Segment>ValueHere</e1632:Segment>
        </e1632:SearchParameter>
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
      <Result xmlns:e1641="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1641:Segment d4p1:nil="false">ValueHere</e1641:Segment>
        <e1641:Entries d4p1:nil="false">
          <e1641:AuctionInsightEntry>
            <e1641:DisplayDomain d4p1:nil="false">ValueHere</e1641:DisplayDomain>
            <e1641:AggregatedKpi d4p1:nil="false">
              <e1641:Segment d4p1:nil="false">ValueHere</e1641:Segment>
              <e1641:ImpressionShare>ValueHere</e1641:ImpressionShare>
              <e1641:OverlapRate>ValueHere</e1641:OverlapRate>
              <e1641:AveragePosition>ValueHere</e1641:AveragePosition>
              <e1641:AboveRate>ValueHere</e1641:AboveRate>
              <e1641:TopOfPageRate>ValueHere</e1641:TopOfPageRate>
              <e1641:OutrankingShare>ValueHere</e1641:OutrankingShare>
            </e1641:AggregatedKpi>
            <e1641:SegmentedKpis d4p1:nil="false">
              <e1641:AuctionInsightKpi>
                <e1641:Segment d4p1:nil="false">ValueHere</e1641:Segment>
                <e1641:ImpressionShare>ValueHere</e1641:ImpressionShare>
                <e1641:OverlapRate>ValueHere</e1641:OverlapRate>
                <e1641:AveragePosition>ValueHere</e1641:AveragePosition>
                <e1641:AboveRate>ValueHere</e1641:AboveRate>
                <e1641:TopOfPageRate>ValueHere</e1641:TopOfPageRate>
                <e1641:OutrankingShare>ValueHere</e1641:OutrankingShare>
              </e1641:AuctionInsightKpi>
            </e1641:SegmentedKpis>
          </e1641:AuctionInsightEntry>
        </e1641:Entries>
        <e1641:UsedImpressions>ValueHere</e1641:UsedImpressions>
        <e1641:UsedKeywords>ValueHere</e1641:UsedKeywords>
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

