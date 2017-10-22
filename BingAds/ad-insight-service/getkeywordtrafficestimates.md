---
title: GetKeywordTrafficEstimates Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Provides traffic estimates for keywords e.g., average CPC, average position, clicks, CTR, impressions, and total cost.
---
# GetKeywordTrafficEstimates Service Operation - Ad Insight
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
      <CampaignEstimators xmlns:e91="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" i:nil="false">
        <e91:CampaignEstimator>
          <e91:AdGroupEstimators i:nil="false">
            <e91:AdGroupEstimator>
              <e91:AdGroupId i:nil="false">ValueHere</e91:AdGroupId>
              <e91:KeywordEstimators i:nil="false">
                <e91:KeywordEstimator>
                  <Keyword xmlns:e92="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" i:nil="false">
                    <e92:Id i:nil="false">ValueHere</e92:Id>
                    <e92:MatchType>ValueHere</e92:MatchType>
                    <e92:Text i:nil="false">ValueHere</e92:Text>
                  </Keyword>
                  <e91:MaxCpc i:nil="false">ValueHere</e91:MaxCpc>
                </e91:KeywordEstimator>
              </e91:KeywordEstimators>
              <e91:MaxCpc>ValueHere</e91:MaxCpc>
            </e91:AdGroupEstimator>
          </e91:AdGroupEstimators>
          <e91:CampaignId i:nil="false">ValueHere</e91:CampaignId>
          <Criteria xmlns:e93="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions" i:nil="false">
            <e93:Criterion i:type="-- derived type specified here with the appropriate prefix --">
              <!--This field is applicable if the derived type attribute is set to LocationCriterion-->
              <e93:LocationId>ValueHere</e93:LocationId>
              <!--This field is applicable if the derived type attribute is set to LanguageCriterion-->
              <e93:Language i:nil="false">ValueHere</e93:Language>
              <!--This field is applicable if the derived type attribute is set to NetworkCriterion-->
              <e93:Network>ValueHere</e93:Network>
              <!--This field is applicable if the derived type attribute is set to DeviceCriterion-->
              <e93:DeviceName i:nil="false">ValueHere</e93:DeviceName>
            </e93:Criterion>
          </Criteria>
          <e91:DailyBudget i:nil="false">ValueHere</e91:DailyBudget>
          <NegativeKeywords xmlns:e94="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" i:nil="false">
            <e94:NegativeKeyword>
              <e94:Id i:nil="false">ValueHere</e94:Id>
              <e94:MatchType>ValueHere</e94:MatchType>
              <e94:Text i:nil="false">ValueHere</e94:Text>
            </e94:NegativeKeyword>
          </NegativeKeywords>
        </e91:CampaignEstimator>
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
      <CampaignEstimates xmlns:e95="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e95:CampaignEstimate>
          <e95:AdGroupEstimates d4p1:nil="false">
            <e95:AdGroupEstimate>
              <e95:AdGroupId d4p1:nil="false">ValueHere</e95:AdGroupId>
              <e95:KeywordEstimates d4p1:nil="false">
                <e95:KeywordEstimate>
                  <Keyword xmlns:e96="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common" d4p1:nil="false">
                    <e96:Id d4p1:nil="false">ValueHere</e96:Id>
                    <e96:MatchType>ValueHere</e96:MatchType>
                    <e96:Text d4p1:nil="false">ValueHere</e96:Text>
                  </Keyword>
                  <e95:Maximum d4p1:nil="false">
                    <e95:AverageCpc>ValueHere</e95:AverageCpc>
                    <e95:AveragePosition>ValueHere</e95:AveragePosition>
                    <e95:Clicks>ValueHere</e95:Clicks>
                    <e95:Ctr>ValueHere</e95:Ctr>
                    <e95:Impressions>ValueHere</e95:Impressions>
                    <e95:TotalCost>ValueHere</e95:TotalCost>
                  </e95:Maximum>
                  <e95:Minimum d4p1:nil="false">
                    <e95:AverageCpc>ValueHere</e95:AverageCpc>
                    <e95:AveragePosition>ValueHere</e95:AveragePosition>
                    <e95:Clicks>ValueHere</e95:Clicks>
                    <e95:Ctr>ValueHere</e95:Ctr>
                    <e95:Impressions>ValueHere</e95:Impressions>
                    <e95:TotalCost>ValueHere</e95:TotalCost>
                  </e95:Minimum>
                </e95:KeywordEstimate>
              </e95:KeywordEstimates>
            </e95:AdGroupEstimate>
          </e95:AdGroupEstimates>
          <e95:CampaignId d4p1:nil="false">ValueHere</e95:CampaignId>
        </e95:CampaignEstimate>
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
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetKeywordTrafficEstimatesRequest();

	$request->CampaignEstimators = $campaignEstimators;

	return $GLOBALS['AdInsightProxy']->GetService()->GetKeywordTrafficEstimates($request);
}
```
```python
response=adinsight.GetKeywordTrafficEstimates(
	CampaignEstimators=CampaignEstimators)
```

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

