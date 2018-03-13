---
title: GetBidLandscapeByAdGroupIds Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Given a list of existing ad groups, this operation returns for each a list of suggested bids and estimated performance statistics.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetBidLandscapeByAdGroupIds Service Operation - Ad Insight
Given a list of existing ad groups, this operation returns for each a list of suggested bids and estimated performance statistics. You can use the landscape view of multiple bid points with estimated traffic for the same ad group to help make decisions about how to adjust your ad group level default bid to optimize for clicks, impressions, and cost. For example you might use the resulting data to visualize a clicks to cost curve or a bid to impressions curve.

> [!NOTE]
> The estimates are based on the last 7 days of performance data, and not a prediction or guarantee of future performance.

## <a name="request"></a>Request Elements
The *GetBidLandscapeByAdGroupIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupbidlandscapeinputs"></a>AdGroupBidLandscapeInputs|An array of ad group identifiers with corresponding bid landscape type input. A list of suggested bid values with estimated performance statistics will be returned for each input.<br /><br />You may specify a maximum of 1,000 input elements.|[AdGroupBidLandscapeInput](adgroupbidlandscapeinput.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetBidLandscapeByAdGroupIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="bidlandscape"></a>BidLandscape|An array of *AdGroupBidLandscape* objects. The array contains a *AdGroupBidLandscape* corresponding to each ad group and bid landscape type input specified in the request.  Duplicate input are allowed in the same call and will return the same results.<br /><br />If the specified input is invalid or has no associated data results, all elements within the *AdGroupBidLandscape* will be nil except the *AdGroupId* which reflects the ad group identifier specified in the request.<br /><br />If there is data available for the ad group, the *AdGroupBidLandscape* object will provide a list of suggested bids and estimated performance statistics.|[AdGroupBidLandscape](adgroupbidlandscape.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
    <Action mustUnderstand="1">GetBidLandscapeByAdGroupIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetBidLandscapeByAdGroupIdsRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <AdGroupBidLandscapeInputs xmlns:e1290="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" i:nil="false">
        <e1290:AdGroupBidLandscapeInput>
          <e1290:AdGroupBidLandscapeType>ValueHere</e1290:AdGroupBidLandscapeType>
          <e1290:AdGroupId>ValueHere</e1290:AdGroupId>
        </e1290:AdGroupBidLandscapeInput>
      </AdGroupBidLandscapeInputs>
    </GetBidLandscapeByAdGroupIdsRequest>
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
    <GetBidLandscapeByAdGroupIdsResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <BidLandscape xmlns:e1291="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1291:AdGroupBidLandscape>
          <e1291:AdGroupId>ValueHere</e1291:AdGroupId>
          <e1291:AdGroupBidLandscapeType>ValueHere</e1291:AdGroupBidLandscapeType>
          <e1291:StartDate d4p1:nil="false">
            <e1291:Day>ValueHere</e1291:Day>
            <e1291:Month>ValueHere</e1291:Month>
            <e1291:Year>ValueHere</e1291:Year>
          </e1291:StartDate>
          <e1291:EndDate d4p1:nil="false">
            <e1291:Day>ValueHere</e1291:Day>
            <e1291:Month>ValueHere</e1291:Month>
            <e1291:Year>ValueHere</e1291:Year>
          </e1291:EndDate>
          <e1291:BidLandscapePoints d4p1:nil="false">
            <e1291:BidLandscapePoint>
              <e1291:Bid>ValueHere</e1291:Bid>
              <e1291:Clicks d4p1:nil="false">ValueHere</e1291:Clicks>
              <e1291:Impressions>ValueHere</e1291:Impressions>
              <e1291:TopImpressions d4p1:nil="false">ValueHere</e1291:TopImpressions>
              <e1291:CurrencyCode>ValueHere</e1291:CurrencyCode>
              <e1291:Cost d4p1:nil="false">ValueHere</e1291:Cost>
              <e1291:MarginalCPC d4p1:nil="false">ValueHere</e1291:MarginalCPC>
            </e1291:BidLandscapePoint>
          </e1291:BidLandscapePoints>
        </e1291:AdGroupBidLandscape>
      </BidLandscape>
    </GetBidLandscapeByAdGroupIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetBidLandscapeByAdGroupIdsResponse> GetBidLandscapeByAdGroupIdsAsync(
	IList<AdGroupBidLandscapeInput> adGroupBidLandscapeInputs)
{
	var request = new GetBidLandscapeByAdGroupIdsRequest
	{
		AdGroupBidLandscapeInputs = adGroupBidLandscapeInputs
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetBidLandscapeByAdGroupIdsAsync(r), request));
}
```
```java
static GetBidLandscapeByAdGroupIdsResponse getBidLandscapeByAdGroupIds(
	ArrayOfAdGroupBidLandscapeInput adGroupBidLandscapeInputs) throws RemoteException, Exception
{
	GetBidLandscapeByAdGroupIdsRequest request = new GetBidLandscapeByAdGroupIdsRequest();

	request.setAdGroupBidLandscapeInputs(adGroupBidLandscapeInputs);

	return AdInsightService.getService().getBidLandscapeByAdGroupIds(request);
}
```
```php
static function GetBidLandscapeByAdGroupIds(
	$adGroupBidLandscapeInputs)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetBidLandscapeByAdGroupIdsRequest();

	$request->AdGroupBidLandscapeInputs = $adGroupBidLandscapeInputs;

	return $GLOBALS['AdInsightProxy']->GetService()->GetBidLandscapeByAdGroupIds($request);
}
```
```python
response=adinsight_service.GetBidLandscapeByAdGroupIds(
	AdGroupBidLandscapeInputs=AdGroupBidLandscapeInputs)
```

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

