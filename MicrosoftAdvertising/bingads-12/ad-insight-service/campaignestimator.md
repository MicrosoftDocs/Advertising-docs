---
title: CampaignEstimator Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Contains campaign filter criteria and a nested list of ad group and keyword level filter criteria for traffic estimates.
---
# CampaignEstimator Data Object - Ad Insight
Contains campaign filter criteria and a nested list of ad group and keyword level filter criteria for traffic estimates.

## Syntax
```xml
<xs:complexType name="CampaignEstimator" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AdGroupEstimators" nillable="true" type="tns:ArrayOfAdGroupEstimator" />
    <xs:element minOccurs="0" name="CampaignId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Criteria" nillable="true" type="q5:ArrayOfCriterion" xmlns:q5="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions" />
    <xs:element minOccurs="0" name="DailyBudget" nillable="true" type="xs:double" />
    <xs:element minOccurs="0" name="NegativeKeywords" nillable="true" type="q6:ArrayOfNegativeKeyword" xmlns:q6="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupestimators"></a>AdGroupEstimators|The list of ad group estimators with your ad group and keyword level filter criteria for traffic estimates.|[AdGroupEstimator](adgroupestimator.md) array|
|<a name="campaignid"></a>CampaignId|The campaign identifier.<br/><br/>This element is reserved for future use. The returned estimates are not based on any specific campaign.|**long**|
|<a name="criteria"></a>Criteria|The list of campaign level criteria for traffic estimates.<br/><br/>Do not try to instantiate a [Criterion](criterion.md). You can include one or more the following objects that derive from it: [DeviceCriterion](devicecriterion.md), [LanguageCriterion](languagecriterion.md), [LocationCriterion](locationcriterion.md), and [NetworkCriterion](networkcriterion.md).<br/><br/>The location, language, and network criterions are required for traffic estimates.|[Criterion](criterion.md) array|
|<a name="dailybudget"></a>DailyBudget|The daily budget filter criteria for all keyword traffic estimates in the campaign.|**double**|
|<a name="negativekeywords"></a>NegativeKeywords|The list of negative keyword filter criteria for all keyword traffic estimates in the campaign.|[NegativeKeyword](negativekeyword.md) array|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[GetKeywordTrafficEstimates](getkeywordtrafficestimates.md)  
