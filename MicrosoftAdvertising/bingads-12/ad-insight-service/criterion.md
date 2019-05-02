---
title: Criterion Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: This is the base class from which keyword planner criterion objects derive.
---
# Criterion Data Object - Ad Insight
This is the base class from which keyword planner criterion objects derive. 

Do not try to instantiate a [Criterion](criterion.md). You can create one or more following objects that derive from it.
- [DeviceCriterion](devicecriterion.md)  
- [LanguageCriterion](languagecriterion.md)  
- [LocationCriterion](locationcriterion.md)  
- [NetworkCriterion](networkcriterion.md)  

## Syntax
```xml
<xs:complexType name="Criterion" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence />
</xs:complexType>
```

## <a name="elements"></a>Elements

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Criterions  

## Used By
[CampaignEstimator](campaignestimator.md)  
