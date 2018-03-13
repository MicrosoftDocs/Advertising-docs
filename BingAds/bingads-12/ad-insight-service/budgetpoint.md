---
title: BudgetPoint Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains a budget amount and an estimate of weekly impressions, clicks, and cost for this budget amount.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# BudgetPoint Data Object - Ad Insight
Defines an object that contains a budget amount and an estimate of weekly impressions, clicks, and cost for this budget amount.

> [!NOTE]
> The budget point is an estimate based on the last 15 days of performance data, and not a prediction or guarantee of future performance.

## Syntax
```xml
<xs:complexType name="BudgetPoint" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="BudgetAmount" type="xs:double" />
    <xs:element minOccurs="0" name="BudgetPointType" type="tns:BudgetPointType" />
    <xs:element minOccurs="0" name="EstimatedWeeklyClicks" type="xs:double" />
    <xs:element minOccurs="0" name="EstimatedWeeklyCost" type="xs:double" />
    <xs:element minOccurs="0" name="EstimatedWeeklyImpressions" type="xs:double" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="budgetamount"></a>BudgetAmount|A potential new budget.<br /><br /> This budget amount is your current campaign budget if the *BudgetPointType* value is *Current*.|**double**|
|<a name="budgetpointtype"></a>BudgetPointType|The type of budget relative to a list of budget points. For example, if the budget point type is *Current* then this object's *BudgetAmount* element would be equal to the corresponding campaign's daily budget.|[BudgetPointType](budgetpointtype.md)|
|<a name="estimatedweeklyclicks"></a>EstimatedWeeklyClicks|The estimated weekly  clicks for the given budget amount.|**double**|
|<a name="estimatedweeklycost"></a>EstimatedWeeklyCost|The estimated weekly cost for the given budget amount.|**double**|
|<a name="estimatedweeklyimpressions"></a>EstimatedWeeklyImpressions|The estimated weekly impressions for the given budget amount.|**double**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[BudgetOpportunity](budgetopportunity.md)  
