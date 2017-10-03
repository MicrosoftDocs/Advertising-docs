---
title: KeywordOpportunityType Value Set
ms.service: bing-ads-ad-insight
ms.topic: article
author: eric-urban
ms.author: eur
---
# KeywordOpportunityType Value Set
Defines the possible keyword opportunity types you can request when calling [GetKeywordOpportunities](../ad-insight/getkeywordopportunities.md).

## Syntax
```xml
<xs:simpleType name="KeywordOpportunityType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="BroadMatch" />
        <xs:enumeration value="CampaignContext" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="broadmatch"></a>BroadMatch|The keyword opportunity will be suggested based on the marketplace impact of adding keywords with the broad match type.|
|<a name="campaigncontext"></a>CampaignContext|The keyword opportunity will be suggested based on the full context of the campaign, including existing keywords, landing page, and ad copy.|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

## Used By
[GetKeywordOpportunities](getkeywordopportunities.md)  
