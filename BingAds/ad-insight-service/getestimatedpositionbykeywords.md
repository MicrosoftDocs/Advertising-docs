---
title: GetEstimatedPositionByKeywords Service Operation
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the estimated position in the search results if the specified bid value would be used for the specified keywords.
---
# GetEstimatedPositionByKeywords Service Operation
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
|<a name="currency"></a>Currency|The monetary unit to use to calculate the cost estimates and suggested bid value.<br /><br />If not set, the service determines the currency from the account specified in the CustomerAccountId header element. If neither is set, the service uses USDollar.|[Currency](currency.md)|
|<a name="keywords"></a>Keywords|An array of keywords for which you want to get the estimated position in the search results, based on the specified bid value. You may specify a maximum of 1,000 keywords and each keyword can contains a maximum of 100 characters.|**string**|
|<a name="language"></a>Language|The language used to help determine  the country to use as the source of data for estimating the bids, if the *PublisherCountries* element is not specified.<br /><br /> The language must be supported in each of the countries in the *PublisherCountries* element.<br /><br />For possible values and information about the relationship between languages and countries, see [Ad Languages](~/guides/ad-languages.md).<br /><br />The default value is determined by the *PublisherCountries* element and the location targets associated with the specified *AdGroupId* and *CampaignId*. For more information, see the [Remarks](#remarks) section below.|**string**|
|<a name="matchtypes"></a>MatchTypes|An array of unique match types for which you want to get estimates.<br /><br />You may not specify the Content match type.|[MatchType](matchtype.md) array|
|<a name="maxbid"></a>MaxBid|The maximum bid value to use to determine the estimated position in the search results.|**double**|
|<a name="publishercountries"></a>PublisherCountries|The country codes of the countries to use as the source of data for estimating the bids.<br /><br /> All of the countries must support the language specified in the *Language* element.<br /><br />You may specify one or more country codes. For possible values, see [Geographical Location Codes](~/guides/geographical-location-codes.md).<br /><br />The default value is determined by the *Language* element and the location targets associated with the specified *AdGroupId* and *CampaignId*. For more information, see the [Remarks](#remarks) section below.|**string**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetEstimatedPositionByKeywordsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywordestimatedpositions"></a>KeywordEstimatedPositions|An array of [KeywordEstimatedPosition](../ad-insight-service/keywordestimatedposition.md) data objects. The array contains an item for each keyword specified in the request. If the keyword is not valid, the corresponding item in the array will be null.<br /><br />If data is available for the keyword, the [EstimatedPositionAndTraffic](../ad-insight-service/estimatedpositionandtraffic.md)  will provide the estimated position in the search results where your ads could appear, based on the specified bid value. Otherwise, the *EstimatedPositions* element will be set to null.|[KeywordEstimatedPosition](keywordestimatedposition.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
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
    <GetEstimatedPositionByKeywordsRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <Keywords i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </Keywords>
      <MaxBid>ValueHere</MaxBid>
      <Language i:nil="false">ValueHere</Language>
      <PublisherCountries i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </PublisherCountries>
      <Currency i:nil="false">ValueHere</Currency>
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
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetEstimatedPositionByKeywordsResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <KeywordEstimatedPositions xmlns:e71="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e71:KeywordEstimatedPosition>
          <e71:Keyword d4p1:nil="false">ValueHere</e71:Keyword>
          <e71:EstimatedPositions d4p1:nil="false">
            <e71:EstimatedPositionAndTraffic>
              <e71:MatchType>ValueHere</e71:MatchType>
              <e71:MinClicksPerWeek>ValueHere</e71:MinClicksPerWeek>
              <e71:MaxClicksPerWeek>ValueHere</e71:MaxClicksPerWeek>
              <e71:AverageCPC>ValueHere</e71:AverageCPC>
              <e71:MinImpressionsPerWeek>ValueHere</e71:MinImpressionsPerWeek>
              <e71:MaxImpressionsPerWeek>ValueHere</e71:MaxImpressionsPerWeek>
              <e71:CTR>ValueHere</e71:CTR>
              <e71:MinTotalCostPerWeek>ValueHere</e71:MinTotalCostPerWeek>
              <e71:MaxTotalCostPerWeek>ValueHere</e71:MaxTotalCostPerWeek>
              <e71:Currency>ValueHere</e71:Currency>
              <e71:EstimatedAdPosition>ValueHere</e71:EstimatedAdPosition>
            </e71:EstimatedPositionAndTraffic>
          </e71:EstimatedPositions>
        </e71:KeywordEstimatedPosition>
      </KeywordEstimatedPositions>
    </GetEstimatedPositionByKeywordsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetEstimatedPositionByKeywordsResponse> GetEstimatedPositionByKeywordsAsync(
	IList<string> keywords,
	double maxBid,
	string language,
	IList<string> publisherCountries,
	Currency? currency,
	IList<MatchType> matchTypes,
	long campaignId,
	long adGroupId)
{
	var request = new GetEstimatedPositionByKeywordsRequest
	{
		Keywords = keywords,
		MaxBid = maxBid,
		Language = language,
		PublisherCountries = publisherCountries,
		Currency = currency,
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
	ArrayOfstring publisherCountries,
	Currency currency,
	ArrayOfMatchType matchTypes,
	java.lang.Long campaignId,
	java.lang.Long adGroupId) throws RemoteException, Exception
{
	GetEstimatedPositionByKeywordsRequest request = new GetEstimatedPositionByKeywordsRequest();

	request.setKeywords(keywords);
	request.setMaxBid(maxBid);
	request.setLanguage(language);
	request.setPublisherCountries(publisherCountries);
	request.setCurrency(currency);
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
	$publisherCountries,
	$currency,
	$matchTypes,
	$campaignId,
	$adGroupId)

	$getEstimatedPositionByKeywordsRequest = new GetEstimatedPositionByKeywordsRequest();

	$request->Keywords = $keywords;
	$request->MaxBid = $maxBid;
	$request->Language = $language;
	$request->PublisherCountries = $publisherCountries;
	$request->Currency = $currency;
	$request->MatchTypes = $matchTypes;
	$request->CampaignId = $campaignId;
	$request->AdGroupId = $adGroupId;

	return $AdInsightProxy->GetService()->GetEstimatedPositionByKeywords($request);
}
```
```python
response=adinsight.GetEstimatedPositionByKeywords(
	Keywords=KeywordsHere,
	MaxBid=MaxBidHere,
	Language=LanguageHere,
	PublisherCountries=PublisherCountriesHere,
	Currency=CurrencyHere,
	MatchTypes=MatchTypesHere,
	CampaignId=CampaignIdHere,
	AdGroupId=AdGroupIdHere
)
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
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

