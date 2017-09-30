---
title: GetKeywordTrafficEstimates Service Operation
ms.service: bing-ads-ad-insight
ms.topic: article
author: eric-urban
ms.author: eur
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
      <CampaignEstimators xmlns:e497="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" i:nil="false">
        <e497:CampaignEstimator>
          <e497:AdGroupEstimators i:nil="false">
            <e497:AdGroupEstimator>
              <e497:AdGroupId i:nil="false">ValueHere</e497:AdGroupId>
              <e497:KeywordEstimators i:nil="false">
                <e497:KeywordEstimator>
                  <Keyword xmlns:e498="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" i:nil="false">
                    <e498:Id i:nil="false">ValueHere</e498:Id>
                    <e498:MatchType>ValueHere</e498:MatchType>
                    <e498:Text i:nil="false">ValueHere</e498:Text>
                  </Keyword>
                  <e497:MaxCpc i:nil="false">ValueHere</e497:MaxCpc>
                </e497:KeywordEstimator>
              </e497:KeywordEstimators>
              <e497:MaxCpc>ValueHere</e497:MaxCpc>
            </e497:AdGroupEstimator>
          </e497:AdGroupEstimators>
          <e497:CampaignId i:nil="false">ValueHere</e497:CampaignId>
          <Criteria xmlns:e499="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions" i:nil="false">
            <e499:Criterion i:type="-- derived type specified here with the appropriate prefix --">
              <!--This field is applicable if the derived type attribute is set to LocationCriterion-->
              <e499:LocationId>ValueHere</e499:LocationId>
              <!--This field is applicable if the derived type attribute is set to LanguageCriterion-->
              <e499:Language i:nil="false">ValueHere</e499:Language>
              <!--This field is applicable if the derived type attribute is set to NetworkCriterion-->
              <e499:Network>ValueHere</e499:Network>
              <!--This field is applicable if the derived type attribute is set to DeviceCriterion-->
              <e499:DeviceName i:nil="false">ValueHere</e499:DeviceName>
            </e499:Criterion>
          </Criteria>
          <e497:DailyBudget i:nil="false">ValueHere</e497:DailyBudget>
          <NegativeKeywords xmlns:e500="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" i:nil="false">
            <e500:NegativeKeyword>
              <e500:Id i:nil="false">ValueHere</e500:Id>
              <e500:MatchType>ValueHere</e500:MatchType>
              <e500:Text i:nil="false">ValueHere</e500:Text>
            </e500:NegativeKeyword>
          </NegativeKeywords>
        </e497:CampaignEstimator>
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
      <CampaignEstimates xmlns:e501="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e501:CampaignEstimate>
          <e501:AdGroupEstimates d4p1:nil="false">
            <e501:AdGroupEstimate>
              <e501:AdGroupId d4p1:nil="false">ValueHere</e501:AdGroupId>
              <e501:KeywordEstimates d4p1:nil="false">
                <e501:KeywordEstimate>
                  <Keyword xmlns:e502="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" d4p1:nil="false">
                    <e502:Id d4p1:nil="false">ValueHere</e502:Id>
                    <e502:MatchType>ValueHere</e502:MatchType>
                    <e502:Text d4p1:nil="false">ValueHere</e502:Text>
                  </Keyword>
                  <e501:Maximum d4p1:nil="false">
                    <e501:AverageCpc>ValueHere</e501:AverageCpc>
                    <e501:AveragePosition>ValueHere</e501:AveragePosition>
                    <e501:Clicks>ValueHere</e501:Clicks>
                    <e501:Ctr>ValueHere</e501:Ctr>
                    <e501:Impressions>ValueHere</e501:Impressions>
                    <e501:TotalCost>ValueHere</e501:TotalCost>
                  </e501:Maximum>
                  <e501:Minimum d4p1:nil="false">
                    <e501:AverageCpc>ValueHere</e501:AverageCpc>
                    <e501:AveragePosition>ValueHere</e501:AveragePosition>
                    <e501:Clicks>ValueHere</e501:Clicks>
                    <e501:Ctr>ValueHere</e501:Ctr>
                    <e501:Impressions>ValueHere</e501:Impressions>
                    <e501:TotalCost>ValueHere</e501:TotalCost>
                  </e501:Minimum>
                </e501:KeywordEstimate>
              </e501:KeywordEstimates>
            </e501:AdGroupEstimate>
          </e501:AdGroupEstimates>
          <e501:CampaignId d4p1:nil="false">ValueHere</e501:CampaignId>
        </e501:CampaignEstimate>
      </CampaignEstimates>
    </GetKeywordTrafficEstimatesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
```csharp
protected async Task<GetKeywordTrafficEstimatesResponse> GetKeywordTrafficEstimatesAsync(
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
	ArrayOfCampaignEstimator campaignEstimators)
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

