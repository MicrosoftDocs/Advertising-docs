---
title: CampaignEstimate Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: "article"
ms.date: 11/01/2017
author: eric-urban
ms.author: eur
description: Contains a nested list of suggested keywords for the campaign's ad groups with minimum and maximum traffic estimates.
---
# CampaignEstimate Data Object - Ad Insight
Contains a nested list of suggested keywords for the campaign's ad groups with minimum and maximum traffic estimates. Traffic estimates include average CPC, average position, clicks, CTR, impressions, and total cost.

> [!NOTE]
> The estimates are not a prediction or guarantee of future performance.

## Syntax
```xml
<xs:complexType name="CampaignEstimate" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AdGroupEstimates" nillable="true" type="tns:ArrayOfAdGroupEstimate" />
    <xs:element minOccurs="0" name="CampaignId" nillable="true" type="xs:long" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupestimates"></a>AdGroupEstimates|The nested list of suggested keywords for the campaign's ad groups with minimum and maximum traffic estimates.<br/><br/>Traffic estimates include average CPC, average position, clicks, CTR, impressions, and total cost.|[AdGroupEstimate](adgroupestimate.md) array|
|<a name="campaignid"></a>CampaignId|The ad group identifier.|**long**|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity  

## Used By
[GetKeywordTrafficEstimates](getkeywordtrafficestimates.md)  
