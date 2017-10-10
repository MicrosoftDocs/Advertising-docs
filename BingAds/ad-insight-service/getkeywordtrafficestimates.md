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
|<a name="campaignestimates"></a>CampaignEstimates|The list of campaign estimates. Within each campaign estimate is a nested list of keyword traffic estimates for each ad group.<br/><br/>You can inspect the [BatchError](batcherror.md) Details element to find out which of the requested list items failed. For example if Details contains "*CampaignEstimators[0], AdGroupEstimators[1], KeywordEstimators is null or contains no value*", the error occurred for the 2nd [AdGroupEstimator](adgroupestimator.md) in the submitted list. The Index element of the [BatchError](batcherror.md) is only a sequential count of returned batch errors, and cannot be used to determine where in the request the error occurred.|[CampaignEstimate](campaignestimate.md) array|

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
      <CampaignEstimators xmlns:e703="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" i:nil="false">
        <e703:CampaignEstimator>
          <e703:AdGroupEstimators i:nil="false">
            <e703:AdGroupEstimator>
              <e703:AdGroupId i:nil="false">ValueHere</e703:AdGroupId>
              <e703:KeywordEstimators i:nil="false">
                <e703:KeywordEstimator>
                  <Keyword xmlns:e704="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" i:nil="false">
                    <e704:Id i:nil="false">ValueHere</e704:Id>
                    <e704:MatchType>ValueHere</e704:MatchType>
                    <e704:Text i:nil="false">ValueHere</e704:Text>
                  </Keyword>
                  <e703:MaxCpc i:nil="false">ValueHere</e703:MaxCpc>
                </e703:KeywordEstimator>
              </e703:KeywordEstimators>
              <e703:MaxCpc>ValueHere</e703:MaxCpc>
            </e703:AdGroupEstimator>
          </e703:AdGroupEstimators>
          <e703:CampaignId i:nil="false">ValueHere</e703:CampaignId>
          <Criteria xmlns:e705="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions" i:nil="false">
            <e705:Criterion i:type="-- derived type specified here with the appropriate prefix --">
              <!--This field is applicable if the derived type attribute is set to LocationCriterion-->
              <e705:LocationId>ValueHere</e705:LocationId>
              <!--This field is applicable if the derived type attribute is set to LanguageCriterion-->
              <e705:Language i:nil="false">ValueHere</e705:Language>
              <!--This field is applicable if the derived type attribute is set to NetworkCriterion-->
              <e705:Network>ValueHere</e705:Network>
              <!--This field is applicable if the derived type attribute is set to DeviceCriterion-->
              <e705:DeviceName i:nil="false">ValueHere</e705:DeviceName>
            </e705:Criterion>
          </Criteria>
          <e703:DailyBudget i:nil="false">ValueHere</e703:DailyBudget>
          <NegativeKeywords xmlns:e706="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" i:nil="false">
            <e706:NegativeKeyword>
              <e706:Id i:nil="false">ValueHere</e706:Id>
              <e706:MatchType>ValueHere</e706:MatchType>
              <e706:Text i:nil="false">ValueHere</e706:Text>
            </e706:NegativeKeyword>
          </NegativeKeywords>
        </e703:CampaignEstimator>
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
      <CampaignEstimates xmlns:e707="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e707:CampaignEstimate>
          <e707:AdGroupEstimates d4p1:nil="false">
            <e707:AdGroupEstimate>
              <e707:AdGroupId d4p1:nil="false">ValueHere</e707:AdGroupId>
              <e707:KeywordEstimates d4p1:nil="false">
                <e707:KeywordEstimate>
                  <Keyword xmlns:e708="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" d4p1:nil="false">
                    <e708:Id d4p1:nil="false">ValueHere</e708:Id>
                    <e708:MatchType>ValueHere</e708:MatchType>
                    <e708:Text d4p1:nil="false">ValueHere</e708:Text>
                  </Keyword>
                  <e707:Maximum d4p1:nil="false">
                    <e707:AverageCpc>ValueHere</e707:AverageCpc>
                    <e707:AveragePosition>ValueHere</e707:AveragePosition>
                    <e707:Clicks>ValueHere</e707:Clicks>
                    <e707:Ctr>ValueHere</e707:Ctr>
                    <e707:Impressions>ValueHere</e707:Impressions>
                    <e707:TotalCost>ValueHere</e707:TotalCost>
                  </e707:Maximum>
                  <e707:Minimum d4p1:nil="false">
                    <e707:AverageCpc>ValueHere</e707:AverageCpc>
                    <e707:AveragePosition>ValueHere</e707:AveragePosition>
                    <e707:Clicks>ValueHere</e707:Clicks>
                    <e707:Ctr>ValueHere</e707:Ctr>
                    <e707:Impressions>ValueHere</e707:Impressions>
                    <e707:TotalCost>ValueHere</e707:TotalCost>
                  </e707:Minimum>
                </e707:KeywordEstimate>
              </e707:KeywordEstimates>
            </e707:AdGroupEstimate>
          </e707:AdGroupEstimates>
          <e707:CampaignId d4p1:nil="false">ValueHere</e707:CampaignId>
        </e707:CampaignEstimate>
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

	return (await AdInsightService.CallAsync((s, r) => s.GetKeywordTrafficEstimatesAsync(r), request));
}
```
```java
static GetKeywordTrafficEstimatesResponse getKeywordTrafficEstimates(
	ArrayOfCampaignEstimator campaignEstimators) throws RemoteException, Exception
{
	GetKeywordTrafficEstimatesRequest request = new GetKeywordTrafficEstimatesRequest();

	request.setCampaignEstimators(campaignEstimators);

	return AdInsightService.getService().getKeywordTrafficEstimates(request);
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

