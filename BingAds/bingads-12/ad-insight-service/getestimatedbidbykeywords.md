---
title: GetEstimatedBidByKeywords Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the estimated bid value of one or more keywords that could result in an ad appearing in the targeted position in the search results.
dev_langs: 
  - csharp
  - java
  - php
  - python
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
|<a name="currencycode"></a>CurrencyCode|The ISO code for the monetary unit to use to calculate the cost estimates and suggested bid value.<br /><br />If not set, the service determines the currency from the account specified in the *CustomerAccountId* header element. If neither *Currency* or *CustomerAccountId* is set, the service uses USD.|[CurrencyCode](currencycode.md)|
|<a name="entitylevelbid"></a>EntityLevelBid|Determines whether to return estimates for keyword level bids, ad group level bids, or both.<br /><br />- Set *EntityLevelBid* to Keyword to get an array of [KeywordEstimatedBid](keywordestimatedbid.md) corresponding to the specified keywords.<br /><br />- Set *EntityLevelBid* to AdGroup to get one [EstimatedBidAndTraffic](estimatedbidandtraffic.md) for the specified ad group.<br /><br />- Set *EntityLevelBid* to AllEntities to get an array of [KeywordEstimatedBid](keywordestimatedbid.md) for keywords and one [EstimatedBidAndTraffic](estimatedbidandtraffic.md) for an ad group.<br /><br />If you do not set *EntityLevelBid*, the default is to return only an array of [KeywordEstimatedBid](keywordestimatedbid.md), or the equivalent of setting *EntityLevelBid* to Keyword.<br /><br />If you set *EntityLevelBid* to any value other thanKeyword, AdGroup, or AllEntities, the service will return *Code 3501* with *ErrorCode CampaignServiceBidLevelInvalid*.|**string**|
|<a name="keywords"></a>Keywords|A list of [KeywordAndMatchType](keywordandmatchtype.md) data objects for which you want to get suggested bid values. You may specify a maximum of 1,000 keywords, and each keyword can contain a maximum of 100 characters.|[KeywordAndMatchType](keywordandmatchtype.md) array|
|<a name="language"></a>Language|The language used in parallel with location identifiers for estimating the bids.<br /><br /> The language must be supported in each of the locations that you specify in [LocationIds](#locationids).<br /><br />For possible language values, see [Ad Languages](../guides/ad-languages.md).<br /><br />If you do not specify the language, the service operation uses the language of the specified [AdGroupId](#adgroupid) or [CampaignId](#campaignid). If none of these properties are set, then *EN* (English) is used by default.|**string**|
|<a name="locationids"></a>LocationIds|The identifier or identifiers of the geographical locations to use for estimating the bids.<br /><br />All of the locations must support the language specified in the [Language](#language) element. Although you can specify multiple location identifiers, as a best practice for the most accurate bid estimates per location, you should specify only one location per service call.<br /><br />For possible location identifiers, see [Geographical Location Codes](../guides/geographical-location-codes.md).<br /><br />If you do not specify any locations, the service operation uses the location criterions of the specified [AdGroupId](#adgroupid) or [CampaignId](#campaignid). If none of these properties are set, then *190* (United States) is used by default.|**long** array|
|<a name="targetpositionforads"></a>TargetPositionForAds|The position where you want your ads to appear in the search results.<br /><br />The default value is *MainLine1*.|[TargetAdPosition](targetadposition.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetEstimatedBidByKeywordsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupestimatedbid"></a>AdGroupEstimatedBid|Contains estimates of clicks, average cost per click (CPC), impressions, click-through rate (CTR), and total cost for the specified ad group if you would use the suggested bid.<br /><br /> The *MatchType* value within the [EstimatedBidAndTraffic](estimatedbidandtraffic.md) will always be Aggregate. In this context, it represents the default search bid for an ad group.|[EstimatedBidAndTraffic](estimatedbidandtraffic.md)|
|<a name="keywordestimatedbids"></a>KeywordEstimatedBids|An array of [KeywordEstimatedBid](keywordestimatedbid.md) data objects. The array contains an item for each keyword specified in the request.  If the keyword is not valid, the corresponding item in the array will be null.<br /><br />Each [KeywordEstimatedBid](keywordestimatedbid.md) contains a keyword and *EstimatedPositions* element. If data is available for the keyword, the [EstimatedPositionAndTraffic](estimatedpositionandtraffic.md) will provide the suggested bid value that could have resulted in an ad appearing in the targeted position of the search results. Otherwise, the *EstimatedPositions* element will be set to null.|[KeywordEstimatedBid](keywordestimatedbid.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
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
    <GetEstimatedBidByKeywordsRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <Keywords xmlns:e945="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Message" i:nil="false">
        <e945:KeywordAndMatchType>
          <e945:KeywordText i:nil="false">ValueHere</e945:KeywordText>
          <e945:MatchTypes i:nil="false">
            <MatchType>ValueHere</MatchType>
          </e945:MatchTypes>
        </e945:KeywordAndMatchType>
      </Keywords>
      <TargetPositionForAds>ValueHere</TargetPositionForAds>
      <Language i:nil="false">ValueHere</Language>
      <LocationIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </LocationIds>
      <CurrencyCode i:nil="false">ValueHere</CurrencyCode>
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
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetEstimatedBidByKeywordsResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <KeywordEstimatedBids xmlns:e946="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e946:KeywordEstimatedBid>
          <e946:Keyword d4p1:nil="false">ValueHere</e946:Keyword>
          <e946:EstimatedBids d4p1:nil="false">
            <e946:EstimatedBidAndTraffic>
              <e946:MinClicksPerWeek d4p1:nil="false">ValueHere</e946:MinClicksPerWeek>
              <e946:MaxClicksPerWeek d4p1:nil="false">ValueHere</e946:MaxClicksPerWeek>
              <e946:AverageCPC d4p1:nil="false">ValueHere</e946:AverageCPC>
              <e946:MinImpressionsPerWeek d4p1:nil="false">ValueHere</e946:MinImpressionsPerWeek>
              <e946:MaxImpressionsPerWeek d4p1:nil="false">ValueHere</e946:MaxImpressionsPerWeek>
              <e946:CTR d4p1:nil="false">ValueHere</e946:CTR>
              <e946:MinTotalCostPerWeek d4p1:nil="false">ValueHere</e946:MinTotalCostPerWeek>
              <e946:MaxTotalCostPerWeek d4p1:nil="false">ValueHere</e946:MaxTotalCostPerWeek>
              <e946:CurrencyCode>ValueHere</e946:CurrencyCode>
              <e946:MatchType>ValueHere</e946:MatchType>
              <e946:EstimatedMinBid>ValueHere</e946:EstimatedMinBid>
            </e946:EstimatedBidAndTraffic>
          </e946:EstimatedBids>
        </e946:KeywordEstimatedBid>
      </KeywordEstimatedBids>
      <AdGroupEstimatedBid xmlns:e947="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e947:MinClicksPerWeek d4p1:nil="false">ValueHere</e947:MinClicksPerWeek>
        <e947:MaxClicksPerWeek d4p1:nil="false">ValueHere</e947:MaxClicksPerWeek>
        <e947:AverageCPC d4p1:nil="false">ValueHere</e947:AverageCPC>
        <e947:MinImpressionsPerWeek d4p1:nil="false">ValueHere</e947:MinImpressionsPerWeek>
        <e947:MaxImpressionsPerWeek d4p1:nil="false">ValueHere</e947:MaxImpressionsPerWeek>
        <e947:CTR d4p1:nil="false">ValueHere</e947:CTR>
        <e947:MinTotalCostPerWeek d4p1:nil="false">ValueHere</e947:MinTotalCostPerWeek>
        <e947:MaxTotalCostPerWeek d4p1:nil="false">ValueHere</e947:MaxTotalCostPerWeek>
        <e947:CurrencyCode>ValueHere</e947:CurrencyCode>
        <e947:MatchType>ValueHere</e947:MatchType>
        <e947:EstimatedMinBid>ValueHere</e947:EstimatedMinBid>
      </AdGroupEstimatedBid>
    </GetEstimatedBidByKeywordsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetEstimatedBidByKeywordsResponse> GetEstimatedBidByKeywordsAsync(
	IList<KeywordAndMatchType> keywords,
	TargetAdPosition targetPositionForAds,
	string language,
	IList<long> locationIds,
	CurrencyCode? currencyCode,
	long? campaignId,
	long? adGroupId,
	string entityLevelBid)
{
	var request = new GetEstimatedBidByKeywordsRequest
	{
		Keywords = keywords,
		TargetPositionForAds = targetPositionForAds,
		Language = language,
		LocationIds = locationIds,
		CurrencyCode = currencyCode,
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
	ArrayOflong locationIds,
	CurrencyCode currencyCode,
	java.lang.Long campaignId,
	java.lang.Long adGroupId,
	java.lang.String entityLevelBid) throws RemoteException, Exception
{
	GetEstimatedBidByKeywordsRequest request = new GetEstimatedBidByKeywordsRequest();

	request.setKeywords(keywords);
	request.setTargetPositionForAds(targetPositionForAds);
	request.setLanguage(language);
	request.setLocationIds(locationIds);
	request.setCurrencyCode(currencyCode);
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
	$locationIds,
	$currencyCode,
	$campaignId,
	$adGroupId,
	$entityLevelBid)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetEstimatedBidByKeywordsRequest();

	$request->Keywords = $keywords;
	$request->TargetPositionForAds = $targetPositionForAds;
	$request->Language = $language;
	$request->LocationIds = $locationIds;
	$request->CurrencyCode = $currencyCode;
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
	LocationIds=LocationIds,
	CurrencyCode=CurrencyCode,
	CampaignId=CampaignId,
	AdGroupId=AdGroupId,
	EntityLevelBid=EntityLevelBid)
```

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

