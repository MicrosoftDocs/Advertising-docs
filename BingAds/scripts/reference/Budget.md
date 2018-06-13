---
title: "Budget object"
description: "Contains the methods for managing the campaign's budget."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Budget
Contains the methods for managing the campaign's budget. For more information, see [Budget](/bingads/guides/entity-hierarchy-limits#budget).

## Methods
|Method Name|Return Type|Description|
|-|-|-
[getAmount](#getamount)|double|Returns the campaign's budget amount.
[getDeliveryMethod](#getdeliverymethod)|string|Returns the delivery method (budget type) for this budget.
[setAmount(double amount)](#setamount~double-amount~)|void|Sets the campaign's budget to the specified value.
[setDeliveryMethod(String method)](#setdeliverymethod~string-method~)|void|Sets the delivery method for this budget.

## <a name="getamount"></a>getAmount
Returns the campaign's budget amount.

### Returns
|Type|Description|
|-|-
double|The campaign's budget amount in the account's currency.

## <a name="getdeliverymethod"></a>getDeliveryMethod
Returns the delivery method (budget type) for this budget. 

### Returns
|Type|Description|
|-|-
string|The budget's delivery method. Possible values are:<br /><ul><li>STANDARD</li><li>ACCELERATED</li></ul>For more information, see [What are my budget options?](https://help.bingads.microsoft.com/#apex/3/en/51006/1)

## <a name="setamount~double-amount~"></a>setAmount(double amount)
Sets the campaign's budget to the specified value.

### Arguments
|Name|Type|Description|
|-|-|-
amount|double|The campaign's budget. The amount is in the currency of parent account.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="setdeliverymethod~string-method~"></a>setDeliveryMethod(string method)
Sets the delivery method for this budget. 

### Arguments
|Name|Type|Description|
|-|-|-
method|string|The delivery method of the budget. Possible case-sensitive values are:<ul><li>STANDARD</li><li>ACCELERATED</li></ul>For more information, see [What are my budget options?](https://help.bingads.microsoft.com/#apex/3/en/51006/1)

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## See also

[Campaign.getBudget()](Campaign.md#getbudget)