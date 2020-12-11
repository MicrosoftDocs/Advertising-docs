---
title: Budget Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Represents a budget that can be shared by any campaigns in an account.
---
# Budget Data Object - Campaign Management
Represents a budget that can be shared by any campaigns in an account. 

> [!IMPORTANT]
> The accelerated budget type is deprecated. Please see [Deprecating Accelerated Budget Delivery](../guides/budget-bid-strategies.md#deprecating-accelerated-budget) for more information.  

You can set a single daily budget that can be used by any campaign within the same account. This will enable you to efficiently distribute a single daily budget across all campaigns or across a defined group of campaigns within your Microsoft Advertising account. 

Say you have a budget of $20 to be used uniformly between two campaigns every day. On a given day Campaign A spends only $8 (of its $10 budget) because it got a smaller amount of impressions and clicks than usual. Using a Shared Budget, if Campaign B is performing well then Microsoft Advertising will automatically take the remaining $2 and allocate it to Campaign B. This will increase the chances that the remaining budget will be used to send you more traffic. 

## Syntax
```xml
<xs:complexType name="Budget" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Amount" nillable="true" type="xs:decimal" />
    <xs:element minOccurs="0" name="AssociationCount" nillable="true" type="xs:int" />
    <xs:element minOccurs="0" name="BudgetType" nillable="true" type="tns:BudgetLimitType" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Name" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [Budget](budget.md) object has the following elements: [Amount](#amount), [AssociationCount](#associationcount), [BudgetType](#budgettype), [Id](#id), [Name](#name).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="amount"></a>Amount|The amount to spend daily across all campaigns that share the budget.<br/><br/>**Add:** Required<br/>**Update:** Optional|**decimal**|
|<a name="associationcount"></a>AssociationCount|The number of [Campaign](campaign.md) objects that currently share this budget.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**int**|
|<a name="budgettype"></a>BudgetType|The budget type determines the pace at which the budget is spent throughout the day.<br/><br/>The only valid budget type that you can set is DailyBudgetStandard.<br/><br/>**IMPORTANT:** The accelerated budget type has been sunset for shared budgets. As of January 2020 the only valid budget type that you can set is DailyBudgetStandard, and any other budget type value that you attempt to set will be ignored without returning an error. If you had set the budget type to accelerated prior to January 2020, the data has been migrated and the API will only return "DailyBudgetStandard". Please see [Deprecating Accelerated Budget Delivery](../guides/budget-bid-strategies.md#deprecating-accelerated-budget) for more information.<br/><br/>**Add:** Required<br/>**Update:** Optional|[BudgetLimitType](budgetlimittype.md)|
|<a name="id"></a>Id|The unique Microsoft Advertising identifier of the budget.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**long**|
|<a name="name"></a>Name|The name of the budget. The name must be unique among all budgets within the account. The name can contain a maximum of 255 characters.<br/><br/>The service performs a case-insensitive comparison when it compares the name to existing budget names.<br/><br/>**Add:** Required<br/>**Update:** Optional|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[AddBudgets](addbudgets.md)  
[GetBudgetsByIds](getbudgetsbyids.md)  
[UpdateBudgets](updatebudgets.md)  
