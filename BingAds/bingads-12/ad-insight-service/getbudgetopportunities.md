---
title: GetBudgetOpportunities Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the campaign budget opportunities of the specified campaign.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetBudgetOpportunities Service Operation - Ad Insight
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
|<a name="opportunities"></a>Opportunities|An array of [BudgetOpportunity](budgetopportunity.md) data objects that identify the campaigns whose clicks and impressions may increase if you were to apply the suggested budget.<br /><br />The list will not include opportunities for campaigns that are currently paused by the user.<br /><br />Up to 500 opportunities will be returned for the account.|[BudgetOpportunity](budgetopportunity.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
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
    <GetBudgetOpportunitiesRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <CampaignId i:nil="false">ValueHere</CampaignId>
    </GetBudgetOpportunitiesRequest>
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
    <GetBudgetOpportunitiesResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <Opportunities xmlns:e942="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e942:BudgetOpportunity>
          <e942:BudgetPoints d4p1:nil="false">
            <e942:BudgetPoint>
              <e942:BudgetAmount>ValueHere</e942:BudgetAmount>
              <e942:BudgetPointType>ValueHere</e942:BudgetPointType>
              <e942:EstimatedWeeklyClicks>ValueHere</e942:EstimatedWeeklyClicks>
              <e942:EstimatedWeeklyCost>ValueHere</e942:EstimatedWeeklyCost>
              <e942:EstimatedWeeklyImpressions>ValueHere</e942:EstimatedWeeklyImpressions>
            </e942:BudgetPoint>
          </e942:BudgetPoints>
          <e942:BudgetType>ValueHere</e942:BudgetType>
          <e942:CampaignId>ValueHere</e942:CampaignId>
          <e942:CurrentBudget>ValueHere</e942:CurrentBudget>
          <e942:IncreaseInClicks>ValueHere</e942:IncreaseInClicks>
          <e942:IncreaseInImpressions>ValueHere</e942:IncreaseInImpressions>
          <e942:PercentageIncreaseInClicks>ValueHere</e942:PercentageIncreaseInClicks>
          <e942:PercentageIncreaseInImpressions>ValueHere</e942:PercentageIncreaseInImpressions>
          <e942:RecommendedBudget>ValueHere</e942:RecommendedBudget>
        </e942:BudgetOpportunity>
      </Opportunities>
    </GetBudgetOpportunitiesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetBudgetOpportunitiesResponse> GetBudgetOpportunitiesAsync(
	long? campaignId)
{
	var request = new GetBudgetOpportunitiesRequest
	{
		CampaignId = campaignId
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetBudgetOpportunitiesAsync(r), request));
}
```
```java
static GetBudgetOpportunitiesResponse getBudgetOpportunities(
	java.lang.Long campaignId) throws RemoteException, Exception
{
	GetBudgetOpportunitiesRequest request = new GetBudgetOpportunitiesRequest();

	request.setCampaignId(campaignId);

	return AdInsightService.getService().getBudgetOpportunities(request);
}
```
```php
static function GetBudgetOpportunities(
	$campaignId)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetBudgetOpportunitiesRequest();

	$request->CampaignId = $campaignId;

	return $GLOBALS['AdInsightProxy']->GetService()->GetBudgetOpportunities($request);
}
```
```python
response=adinsight_service.GetBudgetOpportunities(
	CampaignId=CampaignId)
```

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

