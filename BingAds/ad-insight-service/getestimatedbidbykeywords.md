---
title: GetEstimatedBidByKeywords Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: "article"
ms.date: 11/01/2017
author: eric-urban
ms.author: eur
description: Gets the estimated bid value of one or more keywords that could result in an ad appearing in the targeted position in the search results.
---
# GetEstimatedBidByKeywords Service Operation - Ad Insight
Gets the estimated bid value of one or more keywords that could result in an ad appearing in the targeted position in the search results.

> [!NOTE]
> The estimates are not a prediction or guarantee of future performance.

## <a name="request"></a>Request Elements
The *GetEstimatedBidByKeywordsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group whose performance data is used to help determine how well the keyword might perform in the context of the ad group. Specifying an ad group helps improve the accuracy of the suggested bid.<br /><br />If you specify an ad group, you must specify the campaign that it belongs to.|**long**|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign that owns the ad group specified in *AdGroupId*. If you do not specify an ad group, the campaign's performance data is used to help determine how well the keyword might perform in the context of the campaign.<br /><br /> Specifying a campaign and ad group helps improve the accuracy of the suggested bid. If neither *AdGroupId* or *CampaignId* are specified, the operation uses the specified *CustomerAccountId* header element to help determine how well the keyword might perform in the context of the account.|**long**|
|<a name="currency"></a>Currency|The monetary unit to use to calculate the cost estimates and suggested bid value.<br /><br />If not set, the service determines the currency from the account specified in the *CustomerAccountId* header element. If neither *Currency* or  *CustomerAccountId* is set, the service uses USDollar.|[Currency](currency.md)|
|<a name="entitylevelbid"></a>EntityLevelBid|Determines whether to return estimates for keyword level bids, ad group level bids, or both.<br /><br />- Set *EntityLevelBid* to Keyword to get an array of [KeywordEstimatedBid](../ad-insight-service/keywordestimatedbid.md) corresponding to the specified keywords.<br /><br />- Set *EntityLevelBid* to AdGroup to get one [EstimatedBidAndTraffic](../ad-insight-service/estimatedbidandtraffic.md) for the specified ad group.<br /><br />- Set *EntityLevelBid* to AllEntities to get an array of [KeywordEstimatedBid](../ad-insight-service/keywordestimatedbid.md) for keywords and one [EstimatedBidAndTraffic](../ad-insight-service/estimatedbidandtraffic.md) for an ad group.<br /><br />If you do not set *EntityLevelBid*, the default is to return only an array of [KeywordEstimatedBid](../ad-insight-service/keywordestimatedbid.md), or the equivalent of setting *EntityLevelBid* to Keyword.<br /><br />If you set *EntityLevelBid* to any value other thanKeyword, AdGroup, or AllEntities, the service will return *Code 3501* with *ErrorCode CampaignServiceBidLevelInvalid*.|**string**|
|<a name="keywords"></a>Keywords|A list of [KeywordAndMatchType](../ad-insight-service/keywordandmatchtype.md) data objects for which you want to get suggested bid values. You may specify a maximum of 1,000 keywords, and each keyword can contain a maximum of 100 characters.|[KeywordAndMatchType](keywordandmatchtype.md) array|
|<a name="language"></a>Language|The language used to help determine  the country to use as the source of data for estimating the bids, if the *PublisherCountries* element is not specified.<br /><br /> The language must be supported in each of the countries in the *PublisherCountries* element.<br /><br />For possible values and information about the relationship between languages and countries, see [Ad Languages](~/guides/ad-languages.md).<br /><br />The default value is determined by the *PublisherCountries* element and the location targets associated with the specified *AdGroupId* and *CampaignId*. For more information, see the [Remarks](#remarks) section below.|**string**|
|<a name="publishercountries"></a>PublisherCountries|The country codes of the countries to use as the source of data for estimating the bids.<br /><br /> All of the countries must support the language specified in the *Language* element.<br /><br />You may specify one or more country codes. For possible values, see [Geographical Location Codes](~/guides/geographical-location-codes.md).<br /><br />The default value is determined by the *Language* element and the location targets associated with the specified *AdGroupId* and *CampaignId*. For more information, see the [Remarks](#remarks) section below.|**string**|
|<a name="targetpositionforads"></a>TargetPositionForAds|The position where you want your ads to appear in the search results.<br /><br />The default value is *MainLine1*.|[TargetAdPosition](targetadposition.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetEstimatedBidByKeywordsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupestimatedbid"></a>AdGroupEstimatedBid|Contains estimates of clicks, average cost per click (CPC), impressions, click-through rate (CTR), and total cost for the specified ad group if you would use the suggested bid.<br /><br /> The *MatchType* value within the [EstimatedBidAndTraffic](../ad-insight-service/estimatedbidandtraffic.md) will always be Aggregate. In this context, it represents the default search bid for an ad group.|[EstimatedBidAndTraffic](estimatedbidandtraffic.md)|
|<a name="keywordestimatedbids"></a>KeywordEstimatedBids|An array of [KeywordEstimatedBid](../ad-insight-service/keywordestimatedbid.md) data objects. The array contains an item for each keyword specified in the request.  If the keyword is not valid, the corresponding item in the array will be null.<br /><br />Each [KeywordEstimatedBid](../ad-insight-service/keywordestimatedbid.md) contains a keyword and *EstimatedPositions* element. If data is available for the keyword, the [EstimatedPositionAndTraffic](../ad-insight-service/estimatedpositionandtraffic.md) will provide the suggested bid value that could have resulted in an ad appearing in the targeted position of the search results. Otherwise, the *EstimatedPositions* element will be set to null.|[KeywordEstimatedBid](keywordestimatedbid.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
    <Action mustUnderstand="1">GetEstimatedBidByKeywords</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetEstimatedBidByKeywordsRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <Keywords xmlns:e67="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Message" i:nil="false">
        <e67:KeywordAndMatchType>
          <e67:KeywordText i:nil="false">ValueHere</e67:KeywordText>
          <e67:MatchTypes i:nil="false">
            <MatchType>ValueHere</MatchType>
          </e67:MatchTypes>
        </e67:KeywordAndMatchType>
      </Keywords>
      <TargetPositionForAds>ValueHere</TargetPositionForAds>
      <Language i:nil="false">ValueHere</Language>
      <PublisherCountries i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </PublisherCountries>
      <Currency i:nil="false">ValueHere</Currency>
      <CampaignId i:nil="false">ValueHere</CampaignId>
      <AdGroupId i:nil="false">ValueHere</AdGroupId>
      <EntityLevelBid i:nil="false">ValueHere</EntityLevelBid>
    </GetEstimatedBidByKeywordsRequest>
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
    <GetEstimatedBidByKeywordsResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <KeywordEstimatedBids xmlns:e68="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e68:KeywordEstimatedBid>
          <e68:Keyword d4p1:nil="false">ValueHere</e68:Keyword>
          <e68:EstimatedBids d4p1:nil="false">
            <e68:EstimatedBidAndTraffic>
              <e68:MinClicksPerWeek d4p1:nil="false">ValueHere</e68:MinClicksPerWeek>
              <e68:MaxClicksPerWeek d4p1:nil="false">ValueHere</e68:MaxClicksPerWeek>
              <e68:AverageCPC d4p1:nil="false">ValueHere</e68:AverageCPC>
              <e68:MinImpressionsPerWeek d4p1:nil="false">ValueHere</e68:MinImpressionsPerWeek>
              <e68:MaxImpressionsPerWeek d4p1:nil="false">ValueHere</e68:MaxImpressionsPerWeek>
              <e68:CTR d4p1:nil="false">ValueHere</e68:CTR>
              <e68:MinTotalCostPerWeek d4p1:nil="false">ValueHere</e68:MinTotalCostPerWeek>
              <e68:MaxTotalCostPerWeek d4p1:nil="false">ValueHere</e68:MaxTotalCostPerWeek>
              <e68:Currency>ValueHere</e68:Currency>
              <e68:MatchType>ValueHere</e68:MatchType>
              <e68:EstimatedMinBid>ValueHere</e68:EstimatedMinBid>
            </e68:EstimatedBidAndTraffic>
          </e68:EstimatedBids>
        </e68:KeywordEstimatedBid>
      </KeywordEstimatedBids>
      <AdGroupEstimatedBid xmlns:e69="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e69:MinClicksPerWeek d4p1:nil="false">ValueHere</e69:MinClicksPerWeek>
        <e69:MaxClicksPerWeek d4p1:nil="false">ValueHere</e69:MaxClicksPerWeek>
        <e69:AverageCPC d4p1:nil="false">ValueHere</e69:AverageCPC>
        <e69:MinImpressionsPerWeek d4p1:nil="false">ValueHere</e69:MinImpressionsPerWeek>
        <e69:MaxImpressionsPerWeek d4p1:nil="false">ValueHere</e69:MaxImpressionsPerWeek>
        <e69:CTR d4p1:nil="false">ValueHere</e69:CTR>
        <e69:MinTotalCostPerWeek d4p1:nil="false">ValueHere</e69:MinTotalCostPerWeek>
        <e69:MaxTotalCostPerWeek d4p1:nil="false">ValueHere</e69:MaxTotalCostPerWeek>
        <e69:Currency>ValueHere</e69:Currency>
        <e69:MatchType>ValueHere</e69:MatchType>
        <e69:EstimatedMinBid>ValueHere</e69:EstimatedMinBid>
      </AdGroupEstimatedBid>
    </GetEstimatedBidByKeywordsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetEstimatedBidByKeywordsResponse> GetEstimatedBidByKeywordsAsync(
	IList<KeywordAndMatchType> keywords,
	TargetAdPosition targetPositionForAds,
	string language,
	IList<string> publisherCountries,
	Currency? currency,
	long campaignId,
	long adGroupId,
	string entityLevelBid)
{
	var request = new GetEstimatedBidByKeywordsRequest
	{
		Keywords = keywords,
		TargetPositionForAds = targetPositionForAds,
		Language = language,
		PublisherCountries = publisherCountries,
		Currency = currency,
		CampaignId = campaignId,
		AdGroupId = adGroupId,
		EntityLevelBid = entityLevelBid
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetEstimatedBidByKeywordsAsync(r), request));
}
```
```java
static GetEstimatedBidByKeywordsResponse getEstimatedBidByKeywords(
	ArrayOfKeywordAndMatchType keywords,
	TargetAdPosition targetPositionForAds,
	java.lang.String language,
	ArrayOfstring publisherCountries,
	Currency currency,
	java.lang.Long campaignId,
	java.lang.Long adGroupId,
	java.lang.String entityLevelBid) throws RemoteException, Exception
{
	GetEstimatedBidByKeywordsRequest request = new GetEstimatedBidByKeywordsRequest();

	request.setKeywords(keywords);
	request.setTargetPositionForAds(targetPositionForAds);
	request.setLanguage(language);
	request.setPublisherCountries(publisherCountries);
	request.setCurrency(currency);
	request.setCampaignId(campaignId);
	request.setAdGroupId(adGroupId);
	request.setEntityLevelBid(entityLevelBid);

	return AdInsightService.getService().getEstimatedBidByKeywords(request);
}
```
```php
static function GetEstimatedBidByKeywords(
	$keywords,
	$targetPositionForAds,
	$language,
	$publisherCountries,
	$currency,
	$campaignId,
	$adGroupId,
	$entityLevelBid)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetEstimatedBidByKeywordsRequest();

	$request->Keywords = $keywords;
	$request->TargetPositionForAds = $targetPositionForAds;
	$request->Language = $language;
	$request->PublisherCountries = $publisherCountries;
	$request->Currency = $currency;
	$request->CampaignId = $campaignId;
	$request->AdGroupId = $adGroupId;
	$request->EntityLevelBid = $entityLevelBid;

	return $GLOBALS['AdInsightProxy']->GetService()->GetEstimatedBidByKeywords($request);
}
```
```python
response=adinsight_service.GetEstimatedBidByKeywords(
	Keywords=Keywords,
	TargetPositionForAds=TargetPositionForAds,
	Language=Language,
	PublisherCountries=PublisherCountries,
	Currency=Currency,
	CampaignId=CampaignId,
	AdGroupId=AdGroupId,
	EntityLevelBid=EntityLevelBid)
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

