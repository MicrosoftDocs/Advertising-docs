---
title: GetKeywordTrafficEstimates Service Operation
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Provides traffic estimates for keywords e.g., average CPC, average position, clicks, CTR, impressions, and total cost.
---
# GetKeywordTrafficEstimates Service Operation
Provides traffic estimates for keywords e.g., average CPC, average position, clicks, CTR, impressions, and total cost. As input you provide the bid, language, location, and network, with optional campaign budget and negative keyword filters.

## <a name="request"></a>Request Elements
The *GetKeywordTrafficEstimatesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaignestimators"></a>CampaignEstimators|Defines your campaign, ad group, and keyword level criteria and filters for the requested keyword traffic estimates.|[CampaignEstimator](campaignestimator.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetKeywordTrafficEstimatesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaignestimates"></a>CampaignEstimates|The list of campaign estimates. Within each campaign estimate is a nested list of keyword traffic estimates for each ad group.|[CampaignEstimate](campaignestimate.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
    <Action mustUnderstand="1">GetKeywordTrafficEstimates</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetKeywordTrafficEstimatesRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <CampaignEstimators xmlns:e34="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" i:nil="false">
        <e34:CampaignEstimator>
          <e34:AdGroupEstimators i:nil="false">
            <e34:AdGroupEstimator>
              <e34:AdGroupId i:nil="false">ValueHere</e34:AdGroupId>
              <e34:KeywordEstimators i:nil="false">
                <e34:KeywordEstimator>
                  <Keyword xmlns:e35="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" i:nil="false">
                    <e35:Id i:nil="false">ValueHere</e35:Id>
                    <e35:MatchType>ValueHere</e35:MatchType>
                    <e35:Text i:nil="false">ValueHere</e35:Text>
                  </Keyword>
                  <e34:MaxCpc i:nil="false">ValueHere</e34:MaxCpc>
                </e34:KeywordEstimator>
              </e34:KeywordEstimators>
              <e34:MaxCpc>ValueHere</e34:MaxCpc>
            </e34:AdGroupEstimator>
          </e34:AdGroupEstimators>
          <e34:CampaignId i:nil="false">ValueHere</e34:CampaignId>
          <Criteria xmlns:e36="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions" i:nil="false">
            <e36:Criterion i:type="-- derived type specified here with the appropriate prefix --">
              <!--This field is applicable if the derived type attribute is set to LocationCriterion-->
              <e36:LocationId>ValueHere</e36:LocationId>
              <!--This field is applicable if the derived type attribute is set to LanguageCriterion-->
              <e36:Language i:nil="false">ValueHere</e36:Language>
              <!--This field is applicable if the derived type attribute is set to NetworkCriterion-->
              <e36:Network>ValueHere</e36:Network>
              <!--This field is applicable if the derived type attribute is set to DeviceCriterion-->
              <e36:DeviceName i:nil="false">ValueHere</e36:DeviceName>
            </e36:Criterion>
          </Criteria>
          <e34:DailyBudget i:nil="false">ValueHere</e34:DailyBudget>
          <NegativeKeywords xmlns:e37="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" i:nil="false">
            <e37:NegativeKeyword>
              <e37:Id i:nil="false">ValueHere</e37:Id>
              <e37:MatchType>ValueHere</e37:MatchType>
              <e37:Text i:nil="false">ValueHere</e37:Text>
            </e37:NegativeKeyword>
          </NegativeKeywords>
        </e34:CampaignEstimator>
      </CampaignEstimators>
    </GetKeywordTrafficEstimatesRequest>
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
    <GetKeywordTrafficEstimatesResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <CampaignEstimates xmlns:e38="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e38:CampaignEstimate>
          <e38:AdGroupEstimates d4p1:nil="false">
            <e38:AdGroupEstimate>
              <e38:AdGroupId d4p1:nil="false">ValueHere</e38:AdGroupId>
              <e38:KeywordEstimates d4p1:nil="false">
                <e38:KeywordEstimate>
                  <Keyword xmlns:e39="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" d4p1:nil="false">
                    <e39:Id d4p1:nil="false">ValueHere</e39:Id>
                    <e39:MatchType>ValueHere</e39:MatchType>
                    <e39:Text d4p1:nil="false">ValueHere</e39:Text>
                  </Keyword>
                  <e38:Maximum d4p1:nil="false">
                    <e38:AverageCpc>ValueHere</e38:AverageCpc>
                    <e38:AveragePosition>ValueHere</e38:AveragePosition>
                    <e38:Clicks>ValueHere</e38:Clicks>
                    <e38:Ctr>ValueHere</e38:Ctr>
                    <e38:Impressions>ValueHere</e38:Impressions>
                    <e38:TotalCost>ValueHere</e38:TotalCost>
                  </e38:Maximum>
                  <e38:Minimum d4p1:nil="false">
                    <e38:AverageCpc>ValueHere</e38:AverageCpc>
                    <e38:AveragePosition>ValueHere</e38:AveragePosition>
                    <e38:Clicks>ValueHere</e38:Clicks>
                    <e38:Ctr>ValueHere</e38:Ctr>
                    <e38:Impressions>ValueHere</e38:Impressions>
                    <e38:TotalCost>ValueHere</e38:TotalCost>
                  </e38:Minimum>
                </e38:KeywordEstimate>
              </e38:KeywordEstimates>
            </e38:AdGroupEstimate>
          </e38:AdGroupEstimates>
          <e38:CampaignId d4p1:nil="false">ValueHere</e38:CampaignId>
        </e38:CampaignEstimate>
      </CampaignEstimates>
    </GetKeywordTrafficEstimatesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetKeywordTrafficEstimatesResponse> GetKeywordTrafficEstimatesAsync(
	IList<CampaignEstimator> campaignEstimators)
{
	var request = new GetKeywordTrafficEstimatesRequest
	{
		CampaignEstimators = campaignEstimators
	};

	return (await AdInsight.CallAsync((s, r) => s.GetKeywordTrafficEstimatesAsync(r), request));
}
```
```java
static GetKeywordTrafficEstimatesResponse getKeywordTrafficEstimates(
	ArrayOfCampaignEstimator campaignEstimators) throws RemoteException, Exception
{
	GetKeywordTrafficEstimatesRequest request = new GetKeywordTrafficEstimatesRequest();

	request.setCampaignEstimators(campaignEstimators);

	return AdInsight.getService().getKeywordTrafficEstimates(request);
}
```
```php
static function GetKeywordTrafficEstimates(
	$campaignEstimators)

	$getKeywordTrafficEstimatesRequest = new GetKeywordTrafficEstimatesRequest();

	$request->CampaignEstimators = $campaignEstimators;

	return $AdInsightProxy->GetService()->GetKeywordTrafficEstimates($request);
}
```
```python
response=adinsight.GetKeywordTrafficEstimates(
	CampaignEstimators=CampaignEstimatorsHere
)
```

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

