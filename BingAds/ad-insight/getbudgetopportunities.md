---
title: GetBudgetOpportunities Service Operation
ms.service: bing-ads-ad-insight
ms.topic: article
author: eric-urban
ms.author: eur
---
# GetBudgetOpportunities Service Operation
Gets the campaign budget opportunities of the specified campaign.

## <a name="request"></a>Request Elements
The *GetBudgetOpportunitiesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign for which you want to discover possible campaign budget opportunities.<br /><br />If this element is nil or empty, then the operation will return all budget opportunities for the account.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetBudgetOpportunitiesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="opportunities"></a>Opportunities|An array of [BudgetOpportunity](../ad-insight/budgetopportunity.md) data objects that identify the campaigns whose clicks and impressions may increase if you were to apply the suggested budget.<br /><br />The list will not include opportunities for campaigns that are currently paused by the user.<br /><br />Up to 500 opportunities will be returned for the account.|[BudgetOpportunity](budgetopportunity.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
    <Action mustUnderstand="1">GetBudgetOpportunities</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetBudgetOpportunitiesRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <CampaignId i:nil="false">ValueHere</CampaignId>
    </GetBudgetOpportunitiesRequest>
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
    <GetBudgetOpportunitiesResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <Opportunities xmlns:e64="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e64:BudgetOpportunity>
          <e64:BudgetPoints d4p1:nil="false">
            <e64:BudgetPoint>
              <e64:BudgetAmount>ValueHere</e64:BudgetAmount>
              <e64:BudgetPointType>ValueHere</e64:BudgetPointType>
              <e64:EstimatedWeeklyClicks>ValueHere</e64:EstimatedWeeklyClicks>
              <e64:EstimatedWeeklyCost>ValueHere</e64:EstimatedWeeklyCost>
              <e64:EstimatedWeeklyImpressions>ValueHere</e64:EstimatedWeeklyImpressions>
            </e64:BudgetPoint>
          </e64:BudgetPoints>
          <e64:BudgetType>ValueHere</e64:BudgetType>
          <e64:CampaignId>ValueHere</e64:CampaignId>
          <e64:CurrentBudget>ValueHere</e64:CurrentBudget>
          <e64:IncreaseInClicks>ValueHere</e64:IncreaseInClicks>
          <e64:IncreaseInImpressions>ValueHere</e64:IncreaseInImpressions>
          <e64:PercentageIncreaseInClicks>ValueHere</e64:PercentageIncreaseInClicks>
          <e64:PercentageIncreaseInImpressions>ValueHere</e64:PercentageIncreaseInImpressions>
          <e64:RecommendedBudget>ValueHere</e64:RecommendedBudget>
        </e64:BudgetOpportunity>
      </Opportunities>
    </GetBudgetOpportunitiesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
protected async Task<GetBudgetOpportunitiesResponse> GetBudgetOpportunitiesAsync(
	long campaignId)
{
	var request = new GetBudgetOpportunitiesRequest
	{
		CampaignId = campaignId
	};

	return (await AdInsight.CallAsync((s, r) => s.GetBudgetOpportunitiesAsync(r), request));
}
```
```java
static GetBudgetOpportunitiesResponse getBudgetOpportunities(
	long campaignId)
{
	GetBudgetOpportunitiesRequest request = new GetBudgetOpportunitiesRequest();

	request.setCampaignId(campaignId);

	return AdInsight.getService().getBudgetOpportunities(request);
}
```
```php
static function GetBudgetOpportunities(
	$campaignId)

	$getBudgetOpportunitiesRequest = new GetBudgetOpportunitiesRequest();

	$request->CampaignId = $campaignId;

	return $AdInsightProxy->GetService()->GetBudgetOpportunities($request);
}
```
```python
response=adinsight.GetBudgetOpportunities(
	CampaignId=CampaignIdHere
)
```

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

