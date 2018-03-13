---
title: BudgetLimitType Value Set - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible types of campaign budgets.
---
# BudgetLimitType Value Set - Ad Insight
Defines the possible types of campaign budgets.

## Syntax
```xml
<xs:simpleType name="BudgetLimitType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="DailyBudgetStandard">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">5</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="DailyBudgetAccelerated">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">6</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="dailybudgetaccelerated"></a>DailyBudgetAccelerated|A daily budget that is spent until it is depleted. Depending on the activity, the complete budget could be spent within a couple of minutes, hours, or not at all.<br /><br />The daily spend will not exceed the daily budget limit and the accumulated daily spend will not exceed the calculated monthly budget limit.|
|<a name="dailybudgetstandard"></a>DailyBudgetStandard|A daily budget that is spread throughout the day.<br /><br />The daily spend can exceed the daily budget limit by up to 20%; however, the accumulated daily spend will not exceed the calculated monthly budget limit.|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

## Used By
[BudgetOpportunity](budgetopportunity.md)  
