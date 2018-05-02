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
      <CampaignEstimators xmlns:e969="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" i:nil="false">
        <e969:CampaignEstimator>
          <e969:AdGroupEstimators i:nil="false">
            <e969:AdGroupEstimator>
              <e969:AdGroupId i:nil="false">ValueHere</e969:AdGroupId>
              <e969:KeywordEstimators i:nil="false">
                <e969:KeywordEstimator>
                  <Keyword xmlns:e970="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" i:nil="false">
                    <e970:Id i:nil="false">ValueHere</e970:Id>
                    <e970:MatchType>ValueHere</e970:MatchType>
                    <e970:Text i:nil="false">ValueHere</e970:Text>
                  </Keyword>
                  <e969:MaxCpc i:nil="false">ValueHere</e969:MaxCpc>
                </e969:KeywordEstimator>
              </e969:KeywordEstimators>
              <e969:MaxCpc>ValueHere</e969:MaxCpc>
            </e969:AdGroupEstimator>
          </e969:AdGroupEstimators>
          <e969:CampaignId i:nil="false">ValueHere</e969:CampaignId>
          <Criteria xmlns:e971="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" i:nil="false">
            <e971:Criterion i:type="-- derived type specified here with the appropriate prefix --">
              <!--This field is applicable if the derived type attribute is set to LocationCriterion-->
              <e971:LocationId>ValueHere</e971:LocationId>
              <!--This field is applicable if the derived type attribute is set to LanguageCriterion-->
              <e971:Language i:nil="false">ValueHere</e971:Language>
              <!--This field is applicable if the derived type attribute is set to NetworkCriterion-->
              <e971:Network>ValueHere</e971:Network>
              <!--This field is applicable if the derived type attribute is set to DeviceCriterion-->
              <e971:DeviceName i:nil="false">ValueHere</e971:DeviceName>
            </e971:Criterion>
          </Criteria>
          <e969:DailyBudget i:nil="false">ValueHere</e969:DailyBudget>
          <NegativeKeywords xmlns:e972="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" i:nil="false">
            <e972:NegativeKeyword>
              <e972:Id i:nil="false">ValueHere</e972:Id>
              <e972:MatchType>ValueHere</e972:MatchType>
              <e972:Text i:nil="false">ValueHere</e972:Text>
            </e972:NegativeKeyword>
          </NegativeKeywords>
        </e969:CampaignEstimator>
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
      <CampaignEstimates xmlns:e973="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e973:CampaignEstimate>
          <e973:AdGroupEstimates d4p1:nil="false">
            <e973:AdGroupEstimate>
              <e973:AdGroupId d4p1:nil="false">ValueHere</e973:AdGroupId>
              <e973:KeywordEstimates d4p1:nil="false">
                <e973:KeywordEstimate>
                  <Keyword xmlns:e974="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" d4p1:nil="false">
                    <e974:Id d4p1:nil="false">ValueHere</e974:Id>
                    <e974:MatchType>ValueHere</e974:MatchType>
                    <e974:Text d4p1:nil="false">ValueHere</e974:Text>
                  </Keyword>
                  <e973:Maximum d4p1:nil="false">
                    <e973:AverageCpc>ValueHere</e973:AverageCpc>
                    <e973:AveragePosition>ValueHere</e973:AveragePosition>
                    <e973:Clicks>ValueHere</e973:Clicks>
                    <e973:Ctr>ValueHere</e973:Ctr>
                    <e973:Impressions>ValueHere</e973:Impressions>
                    <e973:TotalCost>ValueHere</e973:TotalCost>
                  </e973:Maximum>
                  <e973:Minimum d4p1:nil="false">
                    <e973:AverageCpc>ValueHere</e973:AverageCpc>
                    <e973:AveragePosition>ValueHere</e973:AveragePosition>
                    <e973:Clicks>ValueHere</e973:Clicks>
                    <e973:Ctr>ValueHere</e973:Ctr>
                    <e973:Impressions>ValueHere</e973:Impressions>
                    <e973:TotalCost>ValueHere</e973:TotalCost>
                  </e973:Minimum>
                </e973:KeywordEstimate>
              </e973:KeywordEstimates>
            </e973:AdGroupEstimate>
          </e973:AdGroupEstimates>
          <e973:CampaignId d4p1:nil="false">ValueHere</e973:CampaignId>
        </e973:CampaignEstimate>
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

