---
title: Opportunity Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: This is the base class from which opportunity objects derive.
---
# Opportunity Data Object - Ad Insight
This is the base class from which opportunity objects derive. The class contains the unique key used to identify the opportunity.

Do not try to instantiate an *Opportunity*. You can create one or more following objects that derive from it.
- [BidOpportunity](bidopportunity.md)  
- [BudgetOpportunity](budgetopportunity.md)  
- [KeywordOpportunity](keywordopportunity.md)  
- [BroadMatchKeywordOpportunity](broadmatchkeywordopportunity.md) (derived from [KeywordOpportunity](keywordopportunity.md))

## Syntax
```xml
<xs:complexType name="Opportunity" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="OpportunityKey" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="opportunitykey"></a>OpportunityKey|An identifier that uniquely identifies the opportunity.|**string**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

