---
title: GetBidLandscapeByKeywordIds Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Given a list of existing keywords, this operation returns for each a list of suggested bids and estimated performance statistics from 1 to  7 days.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetBidLandscapeByKeywordIds Service Operation - Ad Insight
Given a list of existing keywords, this operation returns for each a list of suggested bids and estimated performance statistics from 1 to  7 days. This operation is not based on target position, rather it returns multiple bid options that yield different estimated clicks, impressions, and cost. You can use the landscape view of multiple bid points with estimated traffic for the same keyword to help make decisions about how to adjust your keyword bid to optimize for clicks, impressions, and cost. For example you might use the resulting data to visualize a clicks to cost curve or a bid to impressions curve.

> [!NOTE]
> The estimates are based on the last 7 days of performance data, and not a prediction or guarantee of future performance.

## <a name="request"></a>Request Elements
The *GetBidLandscapeByKeywordIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="includecurrentbid"></a>IncludeCurrentBid|When set to **false**, the suggested bid values might not include the keyword's current bid. The default value is **false**.<br /><br />When set to **true**, one of the suggested bid values will be equal to the keyword's current bid.|**boolean**|
|<a name="keywordids"></a>KeywordIds|An array of identifiers of the keywords for which you want to get the list of suggested bid values with estimated performance statistics.<br /><br />You may specify a maximum of 1,000 keywords.|**long** array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetBidLandscapeByKeywordIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="bidlandscape"></a>BidLandscape|An array of *KeywordBidLandscape* objects. The array contains a *KeywordBidLandscape* corresponding to each keyword specified in the request.  Duplicate keyword identifiers are allowed in the same call and will return the same results.<br /><br />If the specified keyword identifier is invalid or has no associated data results, all elements within the *KeywordBidLandscape* will be nil except the *KeywordId* which reflects the keyword identifier specified in the request.<br /><br />If there is data available for the keyword, the *KeywordBidLandscape* object will provide a list of suggested bids and estimated performance statistics.|[KeywordBidLandscape](keywordbidlandscape.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
    <Action mustUnderstand="1">GetBidLandscapeByKeywordIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetBidLandscapeByKeywordIdsRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <KeywordIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </KeywordIds>
      <IncludeCurrentBid i:nil="false">ValueHere</IncludeCurrentBid>
    </GetBidLandscapeByKeywordIdsRequest>
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
    <GetBidLandscapeByKeywordIdsResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <BidLandscape xmlns:e1644="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1644:KeywordBidLandscape>
          <e1644:KeywordId>ValueHere</e1644:KeywordId>
          <e1644:StartDate d4p1:nil="false">
            <e1644:Day>ValueHere</e1644:Day>
            <e1644:Month>ValueHere</e1644:Month>
            <e1644:Year>ValueHere</e1644:Year>
          </e1644:StartDate>
          <e1644:EndDate d4p1:nil="false">
            <e1644:Day>ValueHere</e1644:Day>
            <e1644:Month>ValueHere</e1644:Month>
            <e1644:Year>ValueHere</e1644:Year>
          </e1644:EndDate>
          <e1644:BidLandscapePoints d4p1:nil="false">
            <e1644:BidLandscapePoint>
              <e1644:Bid>ValueHere</e1644:Bid>
              <e1644:Clicks d4p1:nil="false">ValueHere</e1644:Clicks>
              <e1644:Impressions>ValueHere</e1644:Impressions>
              <e1644:TopImpressions d4p1:nil="false">ValueHere</e1644:TopImpressions>
              <e1644:CurrencyCode>ValueHere</e1644:CurrencyCode>
              <e1644:Cost d4p1:nil="false">ValueHere</e1644:Cost>
              <e1644:MarginalCPC d4p1:nil="false">ValueHere</e1644:MarginalCPC>
            </e1644:BidLandscapePoint>
          </e1644:BidLandscapePoints>
        </e1644:KeywordBidLandscape>
      </BidLandscape>
    </GetBidLandscapeByKeywordIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetBidLandscapeByKeywordIdsResponse> GetBidLandscapeByKeywordIdsAsync(
	IList<long> keywordIds,
	bool? includeCurrentBid)
{
	var request = new GetBidLandscapeByKeywordIdsRequest
	{
		KeywordIds = keywordIds,
		IncludeCurrentBid = includeCurrentBid
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetBidLandscapeByKeywordIdsAsync(r), request));
}
```
```java
static GetBidLandscapeByKeywordIdsResponse getBidLandscapeByKeywordIds(
	ArrayOflong keywordIds,
	boolean includeCurrentBid) throws RemoteException, Exception
{
	GetBidLandscapeByKeywordIdsRequest request = new GetBidLandscapeByKeywordIdsRequest();

	request.setKeywordIds(keywordIds);
	request.setIncludeCurrentBid(includeCurrentBid);

	return AdInsightService.getService().getBidLandscapeByKeywordIds(request);
}
```
```php
static function GetBidLandscapeByKeywordIds(
	$keywordIds,
	$includeCurrentBid)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetBidLandscapeByKeywordIdsRequest();

	$request->KeywordIds = $keywordIds;
	$request->IncludeCurrentBid = $includeCurrentBid;

	return $GLOBALS['AdInsightProxy']->GetService()->GetBidLandscapeByKeywordIds($request);
}
```
```python
response=adinsight_service.GetBidLandscapeByKeywordIds(
	KeywordIds=KeywordIds,
	IncludeCurrentBid=IncludeCurrentBid)
```

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

