---
title: Criterion Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: "article"
ms.date: 11/01/2017
author: eric-urban
ms.author: eur
description: This is the base class from which keyword planner criterion objects derive.
---
# Criterion Data Object - Ad Insight
This is the base class from which keyword planner criterion objects derive. 

Do not try to instantiate a [Criterion](../ad-insight-service/criterion.md). You can create one or more following objects that derive from it.
- [DeviceCriterion](../ad-insight-service/devicecriterion.md)  
- [LanguageCriterion](../ad-insight-service/languagecriterion.md)  
- [LocationCriterion](../ad-insight-service/locationcriterion.md)  
- [NetworkCriterion](../ad-insight-service/networkcriterion.md)  

## Syntax
```xml
<xs:complexType name="Criterion" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence />
</xs:complexType>
```

## <a name="elements"></a>Elements

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Criterions  

## Used By
[CampaignEstimator](campaignestimator.md)  
