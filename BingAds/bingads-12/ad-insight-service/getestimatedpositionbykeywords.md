---
title: GetEstimatedPositionByKeywords Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the estimated position in the search results if the specified bid value would be used for the specified keywords.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# GetEstimatedPositionByKeywords Service Operation - Ad Insight
Gets the estimated position in the search results if the specified bid value would be used for the specified keywords. In addition, the operation provides estimates of clicks, average cost per click (CPC), and impressions that the keywords could be generated with the estimated bid.

> [!NOTE]
> The estimates are not a prediction or guarantee of future performance.

## <a name="request"></a>Request Elements
The *GetEstimatedPositionByKeywordsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group whose performance data is used to help determine how well the keyword might perform in the context of the ad group. Specifying an ad group helps improve the accuracy of the suggested position.<br /><br />If you specify an ad group, you must specify the campaign that it belongs to.|**long**|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign that owns the ad group specified in *AdGroupId*. If you do not specify an ad group, the campaign's performance data is used to help determine how well the keyword might perform in the context of the campaign.<br /><br /> Specifying a campaign and ad group helps improve the accuracy of the suggested position. If neither *AdGroupId* or *CampaignId* are specified, the operation uses the specified *CustomerAccountId* header element to help determine how well the keyword might perform in the context of the account.|**long**|
|<a name="currencycode"></a>CurrencyCode|The ISO code for the monetary unit to use to calculate the cost estimates and suggested bid value.<br /><br />If not set, the service determines the currency from the account specified in the *CustomerAccountId* header element. If neither *Currency* or *CustomerAccountId* is set, the service uses USD.|[CurrencyCode](currencycode.md)|
|<a name="keywords"></a>Keywords|An array of keywords for which you want to get the estimated position in the search results, based on the specified bid value. You may specify a maximum of 1,000 keywords and each keyword can contains a maximum of 100 characters.|**string** array|
|<a name="language"></a>Language|The language used to help determine  the country to use as the source of data for estimating the bids, if the *PublisherCountries* element is not specified.<br /><br /> The language must be supported in each of the countries in the *PublisherCountries* element.<br /><br />For possible values and information about the relationship between languages and countries, see [Ad Languages](../guides/ad-languages.md).<br /><br />The default value is determined by the *PublisherCountries* element and the location targets associated with the specified *AdGroupId* and *CampaignId*. For more information, see the [Remarks](#remarks) section below.|**string**|
|<a name="locationids"></a>LocationIds|Reserved.|**long** array|
|<a name="matchtypes"></a>MatchTypes|An array of unique match types for which you want to get estimates.<br /><br />You may not specify the Content match type.|[MatchType](matchtype.md) array|
|<a name="maxbid"></a>MaxBid|The maximum bid value to use to determine the estimated position in the search results.|**double**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetEstimatedPositionByKeywordsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywordestimatedpositions"></a>KeywordEstimatedPositions|An array of [KeywordEstimatedPosition](keywordestimatedposition.md) data objects. The array contains an item for each keyword specified in the request. If the keyword is not valid, the corresponding item in the array will be null.<br /><br />If data is available for the keyword, the [EstimatedPositionAndTraffic](estimatedpositionandtraffic.md)  will provide the estimated position in the search results where your ads could appear, based on the specified bid value. Otherwise, the *EstimatedPositions* element will be set to null.|[KeywordEstimatedPosition](keywordestimatedposition.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
    <Action mustUnderstand="1">GetEstimatedPositionByKeywords</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetEstimatedPositionByKeywordsRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <Keywords i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </Keywords>
      <MaxBid>ValueHere</MaxBid>
      <Language i:nil="false">ValueHere</Language>
      <LocationIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </LocationIds>
      <CurrencyCode i:nil="false">ValueHere</CurrencyCode>
      <MatchTypes i:nil="false">
        <MatchType>ValueHere</MatchType>
      </MatchTypes>
      <CampaignId i:nil="false">ValueHere</CampaignId>
      <AdGroupId i:nil="false">ValueHere</AdGroupId>
    </GetEstimatedPositionByKeywordsRequest>
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
    <GetEstimatedPositionByKeywordsResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <KeywordEstimatedPositions xmlns:e1301="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1301:KeywordEstimatedPosition>
          <e1301:Keyword d4p1:nil="false">ValueHere</e1301:Keyword>
          <e1301:EstimatedPositions d4p1:nil="false">
            <e1301:EstimatedPositionAndTraffic>
              <e1301:MatchType>ValueHere</e1301:MatchType>
              <e1301:MinClicksPerWeek>ValueHere</e1301:MinClicksPerWeek>
              <e1301:MaxClicksPerWeek>ValueHere</e1301:MaxClicksPerWeek>
              <e1301:AverageCPC>ValueHere</e1301:AverageCPC>
              <e1301:MinImpressionsPerWeek>ValueHere</e1301:MinImpressionsPerWeek>
              <e1301:MaxImpressionsPerWeek>ValueHere</e1301:MaxImpressionsPerWeek>
              <e1301:CTR>ValueHere</e1301:CTR>
              <e1301:MinTotalCostPerWeek>ValueHere</e1301:MinTotalCostPerWeek>
              <e1301:MaxTotalCostPerWeek>ValueHere</e1301:MaxTotalCostPerWeek>
              <e1301:CurrencyCode>ValueHere</e1301:CurrencyCode>
              <e1301:EstimatedAdPosition>ValueHere</e1301:EstimatedAdPosition>
            </e1301:EstimatedPositionAndTraffic>
          </e1301:EstimatedPositions>
        </e1301:KeywordEstimatedPosition>
      </KeywordEstimatedPositions>
    </GetEstimatedPositionByKeywordsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetEstimatedPositionByKeywordsResponse> GetEstimatedPositionByKeywordsAsync(
	IList<string> keywords,
	double maxBid,
	string language,
	IList<long> locationIds,
	CurrencyCode? currencyCode,
	IList<MatchType> matchTypes,
	long? campaignId,
	long? adGroupId)
{
	var request = new GetEstimatedPositionByKeywordsRequest
	{
		Keywords = keywords,
		MaxBid = maxBid,
		Language = language,
		LocationIds = locationIds,
		CurrencyCode = currencyCode,
		MatchTypes = matchTypes,
		CampaignId = campaignId,
		AdGroupId = adGroupId
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetEstimatedPositionByKeywordsAsync(r), request));
}
```
```java
static GetEstimatedPositionByKeywordsResponse getEstimatedPositionByKeywords(
	ArrayOfstring keywords,
	double maxBid,
	java.lang.String language,
	ArrayOflong locationIds,
	CurrencyCode currencyCode,
	ArrayOfMatchType matchTypes,
	java.lang.Long campaignId,
	java.lang.Long adGroupId) throws RemoteException, Exception
{
	GetEstimatedPositionByKeywordsRequest request = new GetEstimatedPositionByKeywordsRequest();

	request.setKeywords(keywords);
	request.setMaxBid(maxBid);
	request.setLanguage(language);
	request.setLocationIds(locationIds);
	request.setCurrencyCode(currencyCode);
	request.setMatchTypes(matchTypes);
	request.setCampaignId(campaignId);
	request.setAdGroupId(adGroupId);

	return AdInsightService.getService().getEstimatedPositionByKeywords(request);
}
```
```php
static function GetEstimatedPositionByKeywords(
	$keywords,
	$maxBid,
	$language,
	$locationIds,
	$currencyCode,
	$matchTypes,
	$campaignId,
	$adGroupId)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetEstimatedPositionByKeywordsRequest();

	$request->Keywords = $keywords;
	$request->MaxBid = $maxBid;
	$request->Language = $language;
	$request->LocationIds = $locationIds;
	$request->CurrencyCode = $currencyCode;
	$request->MatchTypes = $matchTypes;
	$request->CampaignId = $campaignId;
	$request->AdGroupId = $adGroupId;

	return $GLOBALS['AdInsightProxy']->GetService()->GetEstimatedPositionByKeywords($request);
}
```
```python
response=adinsight_service.GetEstimatedPositionByKeywords(
	Keywords=Keywords,
	MaxBid=MaxBid,
	Language=Language,
	LocationIds=LocationIds,
	CurrencyCode=CurrencyCode,
	MatchTypes=MatchTypes,
	CampaignId=CampaignId,
	AdGroupId=AdGroupId)
```

## <a name="remarks"></a>Remarks
As a best practice for the most accurate bid estimates per country, you should specify only one country per service call. If no countries are specified or if multiple *PublisherCountries* are specified, then the service will use the first available set of the following properties to determine  the country to use as the source of data for estimating the bids.

-   Multiple countries corresponding to this operation's specified *PublisherCountries* element.

-   The service will use the set of all supported countries for the specified *Language*, and join with common supported countries in the location target associated with the specified *AdGroupId*.

    > [!NOTE]
    > If the target countries conflict with the specified *Language*, then the service will disregard the target countries and only use the set of all supported countries for the specified *Language*.

-   The service will use the set of all supported countries for the specified *Language*, and join with common supported countries in the location target associated with the specified *CampaignId*.

    > [!NOTE]
    > If the target countries conflict with the specified *Language*, then the service will disregard the target countries and only use the set of all supported countries for the specified *Language*.

-   *Language* element of the ad group corresponding to this operation's specified *AdGroupId* element. The service will use the set of all supported countries for this language.

Given multiple countries from one of the property sets above, the service will then determine one country with the highest impression count to use as the source of data for estimating the bids. The response will not include details on the final filtered country.

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

