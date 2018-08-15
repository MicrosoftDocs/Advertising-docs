---
title: "Budget object"
description: "Contains the methods for managing the budget."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Budget
Contains the methods for managing a budget. For more information, see [Budget](/bingads/guides/entity-hierarchy-limits#budget).

## Methods
|Method Name|Return Type|Description|
|-|-|-
[campaigns](#campaigns)|[CampaignSelector](./CampaignSelector.md)|Gets a selector that returns all campaigns that share this budget.
[getAmount](#getamount)|double|Gets the budget's amount.
[getDeliveryMethod](#getdeliverymethod)|string|Gets the delivery method (budget type) for this budget.
[getEntityType](#getentitytype)|string|Gets this entity's type.
[getId](#getid)|string|Gets the ID that uniquely identifies this shared budget.
[getName](#getname)|string|Gets this shared budget's name.
[getStats](#getstats)|[Stats](Stats.md)|Gets the performance data for the campaigns that share this budget.
[isExplicitlyShared](#isexplicitlyshared)|Boolean|Gets a Boolean value that indicates whether this budget is a shared budget.
[setAmount(double amount)](#setamount-double-amount-)|void|Sets the budget to the specified amount.
[setDeliveryMethod(String method)](#setdeliverymethod-string-method-)|void|Sets the delivery method for this budget.


## <a name="campaigns"></a>campaigns

Gets a [selector](../concepts/selectors.md) that returns all campaigns that share this budget. 

### Returns

|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector.md)|A selector that returns all campaigns that share this budget. Use the selector's methods to filter the list of campaigns.


## <a name="getamount"></a>getAmount
Gets the budget's amount.

### Returns
|Type|Description|
|-|-
double|The budget, in the account's currency.

## <a name="getdeliverymethod"></a>getDeliveryMethod
Gets the budget's delivery method (budget type). 

### Returns
|Type|Description|
|-|-
string|The budget's delivery method. Possible values are:<br /><ul><li>STANDARD</li><li>ACCELERATED</li></ul>For more information, see [What are my budget options?](https://help.bingads.microsoft.com/#apex/3/en/51006/1)

## <a name="getentitytype"></a>getEntityType
Gets this entity's type.

### Returns
|Type|Description|
|-|-
string|This entity's type, which is *Budget*.

## <a name="getid"></a>getId
Gets the ID that uniquely identifies this shared budget.

### Returns
|Type|Description|
|-|-
string|The ID that uniquely identifies this shared budget. Returns null if the budget is not a shared budget.

## <a name="getname"></a>getName
Gets this shared budget's name.

### Returns:
|Type|Description|
|-|-
string|The shared budget's name. Returns null if the budget is not a shared budget.


## <a name="getstats"></a>getStats
Gets the performance data for for campaigns that share this budget. 

Performance data is available for shared budgets only. To call this method, you must have called the selector's [forDateRange(String dateRange)](BudgetSelector.md#fordaterange-string-daterange-) or [forDateRange(Object dateFrom, Object dateTo)](BudgetSelector.md#fordaterange-object-datefrom-object-dateto-) method. 

### Returns:
|Type|Description|
|-|-
[Stats](Stats.md)|The performance data for campaigns that share this budget. Returns null if the budget is not a shared budget.


## <a name="isexplicitlyshared"></a>isExplicitlyShared
Gets a Boolean value that indicates whether this budget is a shared budget.

### Returns:
|Type|Description|
|-|-
Boolean|Is **true** if the budget is meant to be shared by multiple campaigns; otherwise, **false**.


## <a name="setamount-double-amount-"></a>setAmount(double amount)
Sets the budget's amount.

### Arguments
|Name|Type|Description|
|-|-|-
amount|double|The budget, in the account's currency.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="setdeliverymethod-string-method-"></a>setDeliveryMethod(string method)
Sets the budget's delivery method. 

### Arguments
|Name|Type|Description|
|-|-|-
method|string|The budget's delivery method. Possible case-sensitive values are:<ul><li>STANDARD</li><li>ACCELERATED</li></ul>For more information, see [What are my budget options?](https://help.bingads.microsoft.com/#apex/3/en/51006/1)

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## See also

[Campaign.getBudget()](Campaign.md#getbudget)