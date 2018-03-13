---
title: BidOpportunity Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains the suggested bid with estimated clicks and impressions opportunities.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# BidOpportunity Data Object - Ad Insight
Defines an object that contains the suggested bid with estimated clicks and impressions opportunities.

> [!NOTE]
> The bid opportunity is an estimate based on the last 7 days of performance data, and not a prediction or guarantee of future performance.

## Syntax
```xml
<xs:complexType name="BidOpportunity" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Opportunity">
      <xs:sequence>
        <xs:element minOccurs="0" name="AdGroupId" type="xs:long" />
        <xs:element minOccurs="0" name="CampaignId" type="xs:long" />
        <xs:element minOccurs="0" name="CurrentBid" type="xs:double" />
        <xs:element minOccurs="0" name="EstimatedIncreaseInClicks" type="xs:double" />
        <xs:element minOccurs="0" name="EstimatedIncreaseInCost" type="xs:double" />
        <xs:element minOccurs="0" name="EstimatedIncreaseInImpressions" type="xs:long" />
        <xs:element minOccurs="0" name="KeywordId" type="xs:long" />
        <xs:element minOccurs="0" name="MatchType" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="SuggestedBid" type="xs:double" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group that owns the keyword.|**long**|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign for the ad group that owns the keyword.|**long**|
|<a name="currentbid"></a>CurrentBid|The current keyword bid amount specified for the match type in the *MatchType* element.|**double**|
|<a name="estimatedincreaseinclicks"></a>EstimatedIncreaseInClicks|The estimated clicks opportunities corresponding to the suggested bid.|**double**|
|<a name="estimatedincreaseincost"></a>EstimatedIncreaseInCost|The estimated increase in spend corresponding to the suggested bid.|**double**|
|<a name="estimatedincreaseinimpressions"></a>EstimatedIncreaseInImpressions|The estimated impressions opportunities corresponding to the suggested bid.|**long**|
|<a name="keywordid"></a>KeywordId|The identifier of the keyword to which the bid opportunity applies.|**long**|
|<a name="matchtype"></a>MatchType|The match type to which the suggested bid value applies. The possible values are BroadMatch, ExactMatch, and PhraseMatch.|**string**|
|<a name="suggestedbid"></a>SuggestedBid|The suggested bid based on the last 7 days of performance history for the corresponding ad group.|**double**|

The [BidOpportunity](bidopportunity.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsopportunity"></a>Inherited Elements from Opportunity
The [BidOpportunity](bidopportunity.md) object derives from the [Opportunity](opportunity.md) object, and inherits the following elements. The descriptions below are specific to [BidOpportunity](bidopportunity.md), and might not apply to other objects that inherit the same elements from the [Opportunity](opportunity.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="opportunitykey"></a>OpportunityKey|An identifier that uniquely identifies the opportunity.|**string**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[GetBidOpportunities](getbidopportunities.md)  
