---
title: "BingAdsApp object"
description: "The top-level object that you use to navigate all entities in a single account."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# BingAdsApp

This is the top-level object used to access and manage a single account.

## Methods

|Method Name|Return Type|Description|
|-|-|-
[adGroups](#adgroups)|[AdGroupSelector](./AdGroupSelector.md)|Gets a [selector](../concepts/selectors.md) used to filter the list of ad groups in this account.
[ads](#ads)|[AdSelector](./AdSelector.md)|Gets a [selector](../concepts/selectors.md) used to filter the list of ads in this account.
[budgets](#budgets)|[BudgetSelector](./BudgetSelector.md)|Gets a [selector](../concepts/selectors.md) used to filter the list of shared budgets in this account.
[campaigns](#campaigns)|[CampaignSelector](./CampaignSelector.md)|Gets a selector used to filter the list of campaigns in this account.
[currentAccount](#currentaccount)|[Account](./Account.md)|Gets the account that the script is currently processing.
[keywords](#keywords)|[KeywordSelector](./KeywordSelector.md)|Gets a selector used to filter the list of keywords in this account.
[negativeKeywordLists](#negativekeywordlists)|[NegativeKeywordListSelector](./NegativeKeywordListSelector.md)|Gets a selector used to filter the list of negative keyword lists in this account.
[newNegativeKeywordListBuilder](#newnegativekeywordlistbuilder)|[NegativeKeywordListBuilder](./NegativeKeywordListBuilder.md)|Gets a builder that you use to add a negative keyword list to this account.

<!--
[getExecutionInfo](#getexecutioninfo)|[ExecutionInfo](./ExecutionInfo)|Returns information about the environment in which the script is currently executing.
-->


## <a name="adgroups"></a>adGroups

Gets a [selector](../concepts/selectors.md) used to filter the list of ad groups in this account. 

### Returns

|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector.md)|A selector used to filter the list of ad groups in the current account.


## <a name="ads"></a>ads

Gets a [selector](../concepts/selectors.md) used to filter the list of ads in this account. 

### Returns

|Type|Description|
|-|-
[AdSelector](./AdSelector.md)|A selector used to filter the list of ads in the current account.


## <a name="budgets"></a>budgets

Gets a [selector](../concepts/selectors.md) used to filter the list of shared budgets in this account. 

This method returns only shared budgets. To get unshared (individual campaign) budgets, call the specific campaign's [getBudget](Campaign.md#getbudget) method. The campaign's budget is not shared if the `isExplicitlyShared` method returns **false**.

### Returns

|Type|Description|
|-|-
[BudgetSelector](./BudgetSelector.md)|A selector used to filter the list of shared budgets in the current account.


## <a name="campaigns"></a>campaigns

Gets a [selector](../concepts/selectors.md) used to filter the list of campaigns in this account. 

### Returns

|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector.md)|A selector used to filter the list of campaigns in the current account.


## <a name="currentaccount"></a>currentAccount

Gets the account that the script is currently processing.

### Returns

|Type|Description|
|-|-
[Account](./Account.md)|The account that the script is currently processing. To see how you might use this in a multi-account scenario, see the [select](AccountsApp.md#select-bingadsaccount-account-) method of [AccountsApp](AccountsApp.md).


<!--
## <a name="getexecutioninfo"></a>getExecutionInfo
Returns information about the environment in which the script is currently executing.

### Returns:
|Type|Description|
|-|-
[ExecutionInfo](./ExecutionInfo)|Information about the environment in which the script is currently executing.
-->


## <a name="keywords"></a>keywords

Gets a [selector](../concepts/selectors.md) used to filter the list of keywords in this account.

### Returns

|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector.md)|A selector used to filter the list of keywords in the current account.


## <a name="negativekeywordlists"></a>negativeKeywordLists

Gets a [selector](../concepts/selectors.md) used to filter the list of negative keyword lists in this account. 

### Returns

|Type|Description|
|-|-
[NegativeKeywordListSelector](./NegativeKeywordListSelector.md)|A selector used to filter the list of negative keyword lists in the current account.


## <a name="newnegativekeywordlistbuilder"></a>newNegativeKeywordListBuilder

Gets a [builder](../concepts/builders.md) that you use to add a negative keyword list to this account. 

### Returns

|Type|Description|
|-|-
[NegativeKeywordListBuilder](./NegativeKeywordListBuilder.md)|A builder that you use to add a negative keyword list to the current account.

