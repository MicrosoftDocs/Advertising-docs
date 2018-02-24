---
title: BudgetLimitType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible budget types that you can specify for a campaign.
---
# BudgetLimitType Value Set - Campaign Management

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Defines the possible budget types that you can specify for a campaign.

## Syntax
```xml
<xs:simpleType name="BudgetLimitType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="DailyBudgetAccelerated" />
    <xs:enumeration value="DailyBudgetStandard" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="dailybudgetaccelerated"></a>DailyBudgetAccelerated|A daily budget that is spent until it is depleted. Depending on the activity, the complete budget could be spent within a couple of minutes, hours, or not at all.<br /><br />The daily spend will not exceed the daily budget limit and the accumulated daily spend will not exceed the calculated monthly budget limit.<br /><br />To specify an accelerated daily budget, set the *BudgetType* element of the [Campaign](/bingads/campaign-management-service/campaign.md) object to DailyBudgetAccelerated and set the *DailyBudget* element to the amount that you want to spend daily on the campaign.|
|<a name="dailybudgetstandard"></a>DailyBudgetStandard|A daily budget that is spread throughout the day.<br /><br />The daily spend can exceed the daily budget limit by up to 20%; however, the accumulated daily spend will not exceed the calculated monthly budget limit.<br /><br />To specify a standard daily budget, set the *BudgetType* element of the [Campaign](/bingads/campaign-management-service/campaign.md) object to DailyBudgetStandard and set the *DailyBudget* element to the amount that you want to spend daily on the campaign.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[Budget](budget.md)  
[Campaign](campaign.md)  
