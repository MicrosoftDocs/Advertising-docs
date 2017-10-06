---
title: GetEstimatedPositionByKeywordIds Service Operation
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the estimated position in the search results if the specified bid value had been used for the keywords in the last 7 days.
---
# GetEstimatedPositionByKeywordIds Service Operation
Gets the estimated position in the search results if the specified bid value had been used for the keywords in the last 7 days. In addition, the operation provides estimates of clicks, average cost per click (CPC), and impressions that the keywords could have generated with the estimated bid.

> [!NOTE]
> The estimates are based on the last 7 days of performance data, and not a prediction or guarantee of future performance.

## <a name="request"></a>Request Elements
The *GetEstimatedPositionByKeywordIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywordids"></a>KeywordIds|An array of identifiers of the keywords for which you want to get the estimated position in the search results, based on the specified bid value. You may specify a maximum of 1,000 keyword identifiers.|**long**|
|<a name="maxbid"></a>MaxBid|The maximum bid value to use to determine the estimated position in the search results.<br /><br />You must specify the bid value in the currency of the account.|**double**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetEstimatedPositionByKeywordIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywordestimatedpositions"></a>KeywordEstimatedPositions|A list of [KeywordIdEstimatedPosition](../ad-insight-service/keywordidestimatedposition.md) data objects. The array contains an item for each keyword specified in the request. If the keyword ID is not valid, the corresponding item in the array will be null.<br /><br />Each [KeywordIdEstimatedPosition](../ad-insight-service/keywordidestimatedposition.md) contains a keyword identifier and a  [KeywordEstimatedPosition](../ad-insight-service/keywordestimatedposition.md). If data is available for the keyword, the [EstimatedPositionAndTraffic](../ad-insight-service/estimatedpositionandtraffic.md) will provide the estimated position in the search results, based on the specified bid value. Otherwise, the *EstimatedPositions* element will be set to null.|[KeywordIdEstimatedPosition](keywordidestimatedposition.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
    <Action mustUnderstand="1">GetEstimatedPositionByKeywordIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetEstimatedPositionByKeywordIdsRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <KeywordIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </KeywordIds>
      <MaxBid>ValueHere</MaxBid>
    </GetEstimatedPositionByKeywordIdsRequest>
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
    <GetEstimatedPositionByKeywordIdsResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <KeywordEstimatedPositions xmlns:e13="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e13:KeywordIdEstimatedPosition>
          <e13:KeywordId>ValueHere</e13:KeywordId>
          <e13:KeywordEstimatedPosition d4p1:nil="false">
            <e13:Keyword d4p1:nil="false">ValueHere</e13:Keyword>
            <e13:EstimatedPositions d4p1:nil="false">
              <e13:EstimatedPositionAndTraffic>
                <e13:MatchType>ValueHere</e13:MatchType>
                <e13:MinClicksPerWeek>ValueHere</e13:MinClicksPerWeek>
                <e13:MaxClicksPerWeek>ValueHere</e13:MaxClicksPerWeek>
                <e13:AverageCPC>ValueHere</e13:AverageCPC>
                <e13:MinImpressionsPerWeek>ValueHere</e13:MinImpressionsPerWeek>
                <e13:MaxImpressionsPerWeek>ValueHere</e13:MaxImpressionsPerWeek>
                <e13:CTR>ValueHere</e13:CTR>
                <e13:MinTotalCostPerWeek>ValueHere</e13:MinTotalCostPerWeek>
                <e13:MaxTotalCostPerWeek>ValueHere</e13:MaxTotalCostPerWeek>
                <e13:Currency>ValueHere</e13:Currency>
                <e13:EstimatedAdPosition>ValueHere</e13:EstimatedAdPosition>
              </e13:EstimatedPositionAndTraffic>
            </e13:EstimatedPositions>
          </e13:KeywordEstimatedPosition>
        </e13:KeywordIdEstimatedPosition>
      </KeywordEstimatedPositions>
    </GetEstimatedPositionByKeywordIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetEstimatedPositionByKeywordIdsResponse> GetEstimatedPositionByKeywordIdsAsync(
	IList<long> keywordIds,
	double maxBid)
{
	var request = new GetEstimatedPositionByKeywordIdsRequest
	{
		KeywordIds = keywordIds,
		MaxBid = maxBid
	};

	return (await AdInsight.CallAsync((s, r) => s.GetEstimatedPositionByKeywordIdsAsync(r), request));
}
```
```java
static GetEstimatedPositionByKeywordIdsResponse getEstimatedPositionByKeywordIds(
	ArrayOflong keywordIds,
	double maxBid) throws RemoteException, Exception
{
	GetEstimatedPositionByKeywordIdsRequest request = new GetEstimatedPositionByKeywordIdsRequest();

	request.setKeywordIds(keywordIds);
	request.setMaxBid(maxBid);

	return AdInsight.getService().getEstimatedPositionByKeywordIds(request);
}
```
```php
static function GetEstimatedPositionByKeywordIds(
	$keywordIds,
	$maxBid)

	$getEstimatedPositionByKeywordIdsRequest = new GetEstimatedPositionByKeywordIdsRequest();

	$request->KeywordIds = $keywordIds;
	$request->MaxBid = $maxBid;

	return $AdInsightProxy->GetService()->GetEstimatedPositionByKeywordIds($request);
}
```
```python
response=adinsight.GetEstimatedPositionByKeywordIds(
	KeywordIds=KeywordIdsHere,
	MaxBid=MaxBidHere
)
```

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

