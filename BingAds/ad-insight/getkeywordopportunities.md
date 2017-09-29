---
title: GetKeywordOpportunities Service Operation
ms.service: bing-ads-ad-insight
ms.topic: article
author: eric-urban
ms.author: eur
---
# GetKeywordOpportunities Service Operation
Gets a list of keyword suggestions that are relevant to the specified ad group. The keyword suggestion also includes a suggested bid value.

## <a name="request"></a>Request Elements
The *GetKeywordOpportunitiesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group to get keyword suggestions for.<br /><br />The following restrictions apply to the specified ad group:<br /><br />- Its language must be set to English.<br /><br />- Its distribution medium must include Search.<br /><br />- It should contain keywords and ads. The operation will suggest keywords only if the ad group contains one or more ads and keywords; the more keywords and ads that the ad group contains, the richer the set of suggested keywords will be.<br /><br />If *AdGroupId* is nil or empty, the operation will return all keyword opportunities for the specified campaign.|**long**|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign that owns the specified ad group.<br /><br />If the *CampaignId* element is nil or empty, then the *AdGroupId* must also be nil or empty, and the operation will return all keyword opportunities for the account.|**long**|
|<a name="opportunitytype"></a>OpportunityType|Determines the type or types of keyword opportunities that you want.|[KeywordOpportunityType](keywordopportunitytype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetKeywordOpportunitiesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="opportunities"></a>Opportunities|A list of [KeywordOpportunity](../ad-insight/keywordopportunity.md) data objects that identifies a suggested keyword and bid value. The list will be empty if there are no suggestions, which may occur if the ad group does not contain existing ads and keywords.<br /><br />Up to 500 opportunities of each *OpportunityType* will be returned for the account.|[KeywordOpportunity](keywordopportunity.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
    <Action mustUnderstand="1">GetKeywordOpportunities</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetKeywordOpportunitiesRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <AdGroupId i:nil="false">ValueHere</AdGroupId>
      <CampaignId i:nil="false">ValueHere</CampaignId>
      <OpportunityType>ValueHere</OpportunityType>
    </GetKeywordOpportunitiesRequest>
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
    <GetKeywordOpportunitiesResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <Opportunities xmlns:e496="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e496:KeywordOpportunity d4p1:type="-- derived type specified here with the appropriate prefix --">
          <e496:AdGroupId>ValueHere</e496:AdGroupId>
          <e496:AdGroupName d4p1:nil="false">ValueHere</e496:AdGroupName>
          <e496:CampaignId>ValueHere</e496:CampaignId>
          <e496:CampaignName d4p1:nil="false">ValueHere</e496:CampaignName>
          <e496:Competition>ValueHere</e496:Competition>
          <e496:EstimatedIncreaseInClicks>ValueHere</e496:EstimatedIncreaseInClicks>
          <e496:EstimatedIncreaseInCost>ValueHere</e496:EstimatedIncreaseInCost>
          <e496:EstimatedIncreaseInImpressions>ValueHere</e496:EstimatedIncreaseInImpressions>
          <e496:MatchType>ValueHere</e496:MatchType>
          <e496:MonthlySearches>ValueHere</e496:MonthlySearches>
          <e496:SuggestedBid>ValueHere</e496:SuggestedBid>
          <e496:SuggestedKeyword d4p1:nil="false">ValueHere</e496:SuggestedKeyword>
          <!--These fields are applicable if the derived type attribute is set to BroadMatchKeywordOpportunity-->
          <e496:AverageCPC>ValueHere</e496:AverageCPC>
          <e496:AverageCTR>ValueHere</e496:AverageCTR>
          <e496:ClickShare>ValueHere</e496:ClickShare>
          <e496:ImpressionShare>ValueHere</e496:ImpressionShare>
          <e496:ReferenceKeywordBid>ValueHere</e496:ReferenceKeywordBid>
          <e496:ReferenceKeywordId>ValueHere</e496:ReferenceKeywordId>
          <e496:ReferenceKeywordMatchType>ValueHere</e496:ReferenceKeywordMatchType>
          <e496:SearchQueryKPIs d4p1:nil="false">
            <e496:BroadMatchSearchQueryKPI>
              <e496:AverageCTR>ValueHere</e496:AverageCTR>
              <e496:Clicks>ValueHere</e496:Clicks>
              <e496:Impressions>ValueHere</e496:Impressions>
              <e496:SRPV>ValueHere</e496:SRPV>
              <e496:SearchQuery d4p1:nil="false">ValueHere</e496:SearchQuery>
            </e496:BroadMatchSearchQueryKPI>
          </e496:SearchQueryKPIs>
        </e496:KeywordOpportunity>
      </Opportunities>
    </GetKeywordOpportunitiesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
```csharp
protected async Task<GetKeywordOpportunitiesResponse> GetKeywordOpportunitiesAsync(
	long adGroupId,
	long campaignId,
	KeywordOpportunityType opportunityType)
{
	var request = new GetKeywordOpportunitiesRequest
	{
		AdGroupId = adGroupId,
		CampaignId = campaignId,
		OpportunityType = opportunityType
	};

	return (await AdInsight.CallAsync((s, r) => s.GetKeywordOpportunitiesAsync(r), request));
}
```
```java
static GetKeywordOpportunitiesResponse getKeywordOpportunities(
	long adGroupId,
	long campaignId,
	KeywordOpportunityType opportunityType)
{
	GetKeywordOpportunitiesRequest request = new GetKeywordOpportunitiesRequest();

	request.setAdGroupId(adGroupId);
	request.setCampaignId(campaignId);
	request.setOpportunityType(opportunityType);

	return AdInsight.getService().getKeywordOpportunities(request);
}
```
```php
static function GetKeywordOpportunities(
	$adGroupId,
	$campaignId,
	$opportunityType)

	$getKeywordOpportunitiesRequest = new GetKeywordOpportunitiesRequest();

	$request->AdGroupId = $adGroupId;
	$request->CampaignId = $campaignId;
	$request->OpportunityType = $opportunityType;

	return $AdInsightProxy->GetService()->GetKeywordOpportunities($request);
}
```
```python
response=adinsight.GetKeywordOpportunities(
	AdGroupId=AdGroupIdHere,
	CampaignId=CampaignIdHere,
	OpportunityType=OpportunityTypeHere
)
```

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

