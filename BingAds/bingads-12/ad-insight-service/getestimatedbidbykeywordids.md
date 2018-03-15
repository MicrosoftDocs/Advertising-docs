---
title: GetEstimatedBidByKeywordIds Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the estimated bid value of one or more keywords - specified by keyword identifier - that could have resulted in an ad appearing in the targeted position in the search results in the last  7 days.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetEstimatedBidByKeywordIds Service Operation - Ad Insight
Gets the estimated bid value of one or more keywords - specified by keyword identifier - that could have resulted in an ad appearing in the targeted position in the search results in the last  7 days. In addition, the operation provides estimates of clicks, average cost per click (CPC), and impressions that the keywords could have generated with the estimated bid.

> [!NOTE]
> The estimates are based on the last 7 days of performance data, and not a prediction or guarantee of future performance.

## <a name="request"></a>Request Elements
The *GetEstimatedBidByKeywordIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywordids"></a>KeywordIds|An array of identifiers of the keywords for which you want to get the suggested bid values that could have resulted in your ad appearing in the targeted position in the search results. You may specify a maximum of 1,000 keywords.|**long** array|
|<a name="targetpositionforads"></a>TargetPositionForAds|The position in which you want your ads to appear in the search results.<br /><br />The default value is MainLine1.|[TargetAdPosition](targetadposition.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetEstimatedBidByKeywordIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywordestimatedbids"></a>KeywordEstimatedBids|An array of [KeywordIdEstimatedBid](keywordidestimatedbid.md) data objects. The array contains a corresponding item for each keyword specified in the request. If the keyword ID is not valid, the corresponding item in the array will be null.<br /><br />Each [KeywordIdEstimatedBid](keywordidestimatedbid.md) contains a keyword identifier and a  [KeywordEstimatedBid](keywordestimatedbid.md). If there is data available for the keyword, the [KeywordEstimatedBid](keywordestimatedbid.md) will provide a suggested bid value that could have resulted in an ad appearing in the targeted position of the search results. Otherwise, the [KeywordEstimatedBid](keywordestimatedbid.md) element will be set to null.|[KeywordIdEstimatedBid](keywordidestimatedbid.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
    <Action mustUnderstand="1">GetEstimatedBidByKeywordIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetEstimatedBidByKeywordIdsRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <KeywordIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </KeywordIds>
      <TargetPositionForAds>ValueHere</TargetPositionForAds>
    </GetEstimatedBidByKeywordIdsRequest>
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
    <GetEstimatedBidByKeywordIdsResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <KeywordEstimatedBids xmlns:e1648="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1648:KeywordIdEstimatedBid>
          <e1648:KeywordId>ValueHere</e1648:KeywordId>
          <e1648:KeywordEstimatedBid d4p1:nil="false">
            <e1648:Keyword d4p1:nil="false">ValueHere</e1648:Keyword>
            <e1648:EstimatedBids d4p1:nil="false">
              <e1648:EstimatedBidAndTraffic>
                <e1648:MinClicksPerWeek d4p1:nil="false">ValueHere</e1648:MinClicksPerWeek>
                <e1648:MaxClicksPerWeek d4p1:nil="false">ValueHere</e1648:MaxClicksPerWeek>
                <e1648:AverageCPC d4p1:nil="false">ValueHere</e1648:AverageCPC>
                <e1648:MinImpressionsPerWeek d4p1:nil="false">ValueHere</e1648:MinImpressionsPerWeek>
                <e1648:MaxImpressionsPerWeek d4p1:nil="false">ValueHere</e1648:MaxImpressionsPerWeek>
                <e1648:CTR d4p1:nil="false">ValueHere</e1648:CTR>
                <e1648:MinTotalCostPerWeek d4p1:nil="false">ValueHere</e1648:MinTotalCostPerWeek>
                <e1648:MaxTotalCostPerWeek d4p1:nil="false">ValueHere</e1648:MaxTotalCostPerWeek>
                <e1648:CurrencyCode>ValueHere</e1648:CurrencyCode>
                <e1648:MatchType>ValueHere</e1648:MatchType>
                <e1648:EstimatedMinBid>ValueHere</e1648:EstimatedMinBid>
              </e1648:EstimatedBidAndTraffic>
            </e1648:EstimatedBids>
          </e1648:KeywordEstimatedBid>
        </e1648:KeywordIdEstimatedBid>
      </KeywordEstimatedBids>
    </GetEstimatedBidByKeywordIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetEstimatedBidByKeywordIdsResponse> GetEstimatedBidByKeywordIdsAsync(
	IList<long> keywordIds,
	TargetAdPosition targetPositionForAds)
{
	var request = new GetEstimatedBidByKeywordIdsRequest
	{
		KeywordIds = keywordIds,
		TargetPositionForAds = targetPositionForAds
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetEstimatedBidByKeywordIdsAsync(r), request));
}
```
```java
static GetEstimatedBidByKeywordIdsResponse getEstimatedBidByKeywordIds(
	ArrayOflong keywordIds,
	TargetAdPosition targetPositionForAds) throws RemoteException, Exception
{
	GetEstimatedBidByKeywordIdsRequest request = new GetEstimatedBidByKeywordIdsRequest();

	request.setKeywordIds(keywordIds);
	request.setTargetPositionForAds(targetPositionForAds);

	return AdInsightService.getService().getEstimatedBidByKeywordIds(request);
}
```
```php
static function GetEstimatedBidByKeywordIds(
	$keywordIds,
	$targetPositionForAds)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetEstimatedBidByKeywordIdsRequest();

	$request->KeywordIds = $keywordIds;
	$request->TargetPositionForAds = $targetPositionForAds;

	return $GLOBALS['AdInsightProxy']->GetService()->GetEstimatedBidByKeywordIds($request);
}
```
```python
response=adinsight_service.GetEstimatedBidByKeywordIds(
	KeywordIds=KeywordIds,
	TargetPositionForAds=TargetPositionForAds)
```

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

