---
title: Criterion Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: This is the base class from which keyword planner criterion objects derive.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

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
Service: [AdInsightService.svc v13](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v13/AdInsightService.svc)  
Namespace: https\://bingads.microsoft.com/AdInsight/v13  

## Used By
[CampaignEstimator](campaignestimator.md)  
