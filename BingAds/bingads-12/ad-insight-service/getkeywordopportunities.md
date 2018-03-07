---
title: GetKeywordOpportunities Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets a list of keyword suggestions that are relevant to the specified ad group.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# GetKeywordOpportunities Service Operation - Ad Insight
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
|<a name="opportunities"></a>Opportunities|A list of [KeywordOpportunity](keywordopportunity.md) data objects that identifies a suggested keyword and bid value. The list will be empty if there are no suggestions, which may occur if the ad group does not contain existing ads and keywords.<br /><br />Up to 1,000 CampaignContext and up to 500 BroadMatch keyword opportunities will be returned by the service.|[KeywordOpportunity](keywordopportunity.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
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
    <GetKeywordOpportunitiesRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
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
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetKeywordOpportunitiesResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <Opportunities xmlns:e1320="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1320:KeywordOpportunity d4p1:type="-- derived type specified here with the appropriate prefix --">
          <e1320:AdGroupId>ValueHere</e1320:AdGroupId>
          <e1320:AdGroupName d4p1:nil="false">ValueHere</e1320:AdGroupName>
          <e1320:CampaignId>ValueHere</e1320:CampaignId>
          <e1320:CampaignName d4p1:nil="false">ValueHere</e1320:CampaignName>
          <e1320:Competition>ValueHere</e1320:Competition>
          <e1320:EstimatedIncreaseInClicks>ValueHere</e1320:EstimatedIncreaseInClicks>
          <e1320:EstimatedIncreaseInCost>ValueHere</e1320:EstimatedIncreaseInCost>
          <e1320:EstimatedIncreaseInImpressions>ValueHere</e1320:EstimatedIncreaseInImpressions>
          <e1320:MatchType>ValueHere</e1320:MatchType>
          <e1320:MonthlySearches>ValueHere</e1320:MonthlySearches>
          <e1320:SuggestedBid>ValueHere</e1320:SuggestedBid>
          <e1320:SuggestedKeyword d4p1:nil="false">ValueHere</e1320:SuggestedKeyword>
          <!--These fields are applicable if the derived type attribute is set to BroadMatchKeywordOpportunity-->
          <e1320:AverageCPC>ValueHere</e1320:AverageCPC>
          <e1320:AverageCTR>ValueHere</e1320:AverageCTR>
          <e1320:ClickShare>ValueHere</e1320:ClickShare>
          <e1320:ImpressionShare>ValueHere</e1320:ImpressionShare>
          <e1320:ReferenceKeywordBid>ValueHere</e1320:ReferenceKeywordBid>
          <e1320:ReferenceKeywordId>ValueHere</e1320:ReferenceKeywordId>
          <e1320:ReferenceKeywordMatchType>ValueHere</e1320:ReferenceKeywordMatchType>
          <e1320:SearchQueryKPIs d4p1:nil="false">
            <e1320:BroadMatchSearchQueryKPI>
              <e1320:AverageCTR>ValueHere</e1320:AverageCTR>
              <e1320:Clicks>ValueHere</e1320:Clicks>
              <e1320:Impressions>ValueHere</e1320:Impressions>
              <e1320:SRPV>ValueHere</e1320:SRPV>
              <e1320:SearchQuery d4p1:nil="false">ValueHere</e1320:SearchQuery>
            </e1320:BroadMatchSearchQueryKPI>
          </e1320:SearchQueryKPIs>
        </e1320:KeywordOpportunity>
      </Opportunities>
    </GetKeywordOpportunitiesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetKeywordOpportunitiesResponse> GetKeywordOpportunitiesAsync(
	long? adGroupId,
	long? campaignId,
	KeywordOpportunityType opportunityType)
{
	var request = new GetKeywordOpportunitiesRequest
	{
		AdGroupId = adGroupId,
		CampaignId = campaignId,
		OpportunityType = opportunityType
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetKeywordOpportunitiesAsync(r), request));
}
```
```java
static GetKeywordOpportunitiesResponse getKeywordOpportunities(
	java.lang.Long adGroupId,
	java.lang.Long campaignId,
	ArrayList<KeywordOpportunityType> opportunityType) throws RemoteException, Exception
{
	GetKeywordOpportunitiesRequest request = new GetKeywordOpportunitiesRequest();

	request.setAdGroupId(adGroupId);
	request.setCampaignId(campaignId);
	request.setOpportunityType(opportunityType);

	return AdInsightService.getService().getKeywordOpportunities(request);
}
```
```php
static function GetKeywordOpportunities(
	$adGroupId,
	$campaignId,
	$opportunityType)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetKeywordOpportunitiesRequest();

	$request->AdGroupId = $adGroupId;
	$request->CampaignId = $campaignId;
	$request->OpportunityType = $opportunityType;

	return $GLOBALS['AdInsightProxy']->GetService()->GetKeywordOpportunities($request);
}
```
```python
response=adinsight_service.GetKeywordOpportunities(
	AdGroupId=AdGroupId,
	CampaignId=CampaignId,
	OpportunityType=OpportunityType)
```

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

