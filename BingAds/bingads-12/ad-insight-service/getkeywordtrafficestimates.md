---
title: GetKeywordTrafficEstimates Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Provides traffic estimates for keywords e.g., average CPC, average position, clicks, CTR, impressions, and total cost.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

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
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
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
    <GetKeywordTrafficEstimatesRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <CampaignEstimators xmlns:e1673="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" i:nil="false">
        <e1673:CampaignEstimator>
          <e1673:AdGroupEstimators i:nil="false">
            <e1673:AdGroupEstimator>
              <e1673:AdGroupId i:nil="false">ValueHere</e1673:AdGroupId>
              <e1673:KeywordEstimators i:nil="false">
                <e1673:KeywordEstimator>
                  <Keyword xmlns:e1674="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" i:nil="false">
                    <e1674:Id i:nil="false">ValueHere</e1674:Id>
                    <e1674:MatchType>ValueHere</e1674:MatchType>
                    <e1674:Text i:nil="false">ValueHere</e1674:Text>
                  </Keyword>
                  <e1673:MaxCpc i:nil="false">ValueHere</e1673:MaxCpc>
                </e1673:KeywordEstimator>
              </e1673:KeywordEstimators>
              <e1673:MaxCpc>ValueHere</e1673:MaxCpc>
            </e1673:AdGroupEstimator>
          </e1673:AdGroupEstimators>
          <e1673:CampaignId i:nil="false">ValueHere</e1673:CampaignId>
          <Criteria xmlns:e1675="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e1675:Criterion i:type="-- derived type specified here with the appropriate prefix --">
              <!--This field is applicable if the derived type attribute is set to LocationCriterion-->
              <e1675:LocationId>ValueHere</e1675:LocationId>
              <!--This field is applicable if the derived type attribute is set to LanguageCriterion-->
              <e1675:Language i:nil="false">ValueHere</e1675:Language>
              <!--This field is applicable if the derived type attribute is set to NetworkCriterion-->
              <e1675:Network>ValueHere</e1675:Network>
              <!--This field is applicable if the derived type attribute is set to DeviceCriterion-->
              <e1675:DeviceName i:nil="false">ValueHere</e1675:DeviceName>
            </e1675:Criterion>
          </Criteria>
          <e1673:DailyBudget i:nil="false">ValueHere</e1673:DailyBudget>
          <NegativeKeywords xmlns:e1676="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" i:nil="false">
            <e1676:NegativeKeyword>
              <e1676:Id i:nil="false">ValueHere</e1676:Id>
              <e1676:MatchType>ValueHere</e1676:MatchType>
              <e1676:Text i:nil="false">ValueHere</e1676:Text>
            </e1676:NegativeKeyword>
          </NegativeKeywords>
        </e1673:CampaignEstimator>
      </CampaignEstimators>
    </GetKeywordTrafficEstimatesRequest>
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
    <GetKeywordTrafficEstimatesResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <CampaignEstimates xmlns:e1677="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1677:CampaignEstimate>
          <e1677:AdGroupEstimates d4p1:nil="false">
            <e1677:AdGroupEstimate>
              <e1677:AdGroupId d4p1:nil="false">ValueHere</e1677:AdGroupId>
              <e1677:KeywordEstimates d4p1:nil="false">
                <e1677:KeywordEstimate>
                  <Keyword xmlns:e1678="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" d4p1:nil="false">
                    <e1678:Id d4p1:nil="false">ValueHere</e1678:Id>
                    <e1678:MatchType>ValueHere</e1678:MatchType>
                    <e1678:Text d4p1:nil="false">ValueHere</e1678:Text>
                  </Keyword>
                  <e1677:Maximum d4p1:nil="false">
                    <e1677:AverageCpc>ValueHere</e1677:AverageCpc>
                    <e1677:AveragePosition>ValueHere</e1677:AveragePosition>
                    <e1677:Clicks>ValueHere</e1677:Clicks>
                    <e1677:Ctr>ValueHere</e1677:Ctr>
                    <e1677:Impressions>ValueHere</e1677:Impressions>
                    <e1677:TotalCost>ValueHere</e1677:TotalCost>
                  </e1677:Maximum>
                  <e1677:Minimum d4p1:nil="false">
                    <e1677:AverageCpc>ValueHere</e1677:AverageCpc>
                    <e1677:AveragePosition>ValueHere</e1677:AveragePosition>
                    <e1677:Clicks>ValueHere</e1677:Clicks>
                    <e1677:Ctr>ValueHere</e1677:Ctr>
                    <e1677:Impressions>ValueHere</e1677:Impressions>
                    <e1677:TotalCost>ValueHere</e1677:TotalCost>
                  </e1677:Minimum>
                </e1677:KeywordEstimate>
              </e1677:KeywordEstimates>
            </e1677:AdGroupEstimate>
          </e1677:AdGroupEstimates>
          <e1677:CampaignId d4p1:nil="false">ValueHere</e1677:CampaignId>
        </e1677:CampaignEstimate>
      </CampaignEstimates>
    </GetKeywordTrafficEstimatesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
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
response=adinsight_service.GetKeywordTrafficEstimates(
	CampaignEstimators=CampaignEstimators)
```

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

