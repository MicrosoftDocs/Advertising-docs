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
      <Opportunities xmlns:e470="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e470:BudgetOpportunity>
          <e470:BudgetPoints d4p1:nil="false">
            <e470:BudgetPoint>
              <e470:BudgetAmount>ValueHere</e470:BudgetAmount>
              <e470:BudgetPointType>ValueHere</e470:BudgetPointType>
              <e470:EstimatedWeeklyClicks>ValueHere</e470:EstimatedWeeklyClicks>
              <e470:EstimatedWeeklyCost>ValueHere</e470:EstimatedWeeklyCost>
              <e470:EstimatedWeeklyImpressions>ValueHere</e470:EstimatedWeeklyImpressions>
            </e470:BudgetPoint>
          </e470:BudgetPoints>
          <e470:BudgetType>ValueHere</e470:BudgetType>
          <e470:CampaignId>ValueHere</e470:CampaignId>
          <e470:CurrentBudget>ValueHere</e470:CurrentBudget>
          <e470:IncreaseInClicks>ValueHere</e470:IncreaseInClicks>
          <e470:IncreaseInImpressions>ValueHere</e470:IncreaseInImpressions>
          <e470:PercentageIncreaseInClicks>ValueHere</e470:PercentageIncreaseInClicks>
          <e470:PercentageIncreaseInImpressions>ValueHere</e470:PercentageIncreaseInImpressions>
          <e470:RecommendedBudget>ValueHere</e470:RecommendedBudget>
        </e470:BudgetOpportunity>
      </Opportunities>
    </GetBudgetOpportunitiesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
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

