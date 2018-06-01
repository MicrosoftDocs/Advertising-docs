---
title: "BingAdsApp object"
description: "The top-level object that you use to navigate all entities in a single user account."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# BingAdsApp

This is the root object of Bing Ads Scripts API for single-user account. You must use this object to access all entities in the account.

## Methods

|Method Name|Return Type|Description|
|-|-|-
[adGroups](#adgroups)|[AdGroupSelector](./AdGroupSelector.md)|Returns a [selector](../concepts/selectors.md) of all ad groups in this account.
[campaigns](#campaigns)|[CampaignSelector](./CampaignSelector.md)|Returns a selector of all campaigns in this account.
[keywords](#keywords)|[KeywordSelector](./KeywordSelector.md)|Returns a selector of all keywords in this account.
[negativeKeywordLists](#negativekeywordlists)|[NegativeKeywordListSelector](./NegativeKeywordListSelector.md)|Returns a selector of all negative keyword lists in this account.
[newNegativeKeywordListBuilder](#newnegativekeywordlistbuilder)|[NegativeKeywordListBuilder](./NegativeKeywordListBuilder.md)|Returns a new negative keyword list builder for this account.

<!--
[ads](#ads)|[AdSelector](./AdSelector)|Returns a selector of all ads in this account.<br />
[getExecutionInfo](#getexecutioninfo)|[ExecutionInfo](./ExecutionInfo)|Returns information about the environment in which the script is currently executing.
-->


## <a name="adgroups"></a>adGroups

Returns a [selector](../concepts/selectors.md) of all ad groups in this account. 

### Returns

|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector.md)|Selector of all ad groups in the current account. By default, the selector returns all ad groups in this account. You can also use the selector's methods to return a filtered list of ad groups.

<!--
## <a name="ads"></a>ads
Returns a selector of all ads in this account.


### Returns:
|Type|Description|
|-|-
[AdSelector](./AdSelector)|Selector of all ads in this account.
-->

## <a name="campaigns"></a>campaigns

Returns a [selector](../concepts/selectors.md) of all campaigns in this account. 

### Returns

|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector.md)|Selector of all campaigns in this account. By default, the selector returns all campaigns in this account. You can also use the selector's methods to return a filtered list of campaigns.

<!--
## <a name="getexecutioninfo"></a>getExecutionInfo
Returns information about the environment in which the script is currently executing.

### Returns:
|Type|Description|
|-|-
[ExecutionInfo](./ExecutionInfo)|Information about the environment in which the script is currently executing.
-->

## <a name="keywords"></a>keywords

Returns a [selector](../concepts/selectors.md) of all keywords in this account.

### Returns

|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector.md)|Selector of all keywords in this account. By default, the selector returns all keywords in this account. You can also use the selector's methods to return a filtered list of keywords.

## <a name="negativekeywordlists"></a>negativeKeywordLists

Returns a [selector](../concepts/selectors.md) of all negative keyword lists in this account. 

### Returns

|Type|Description|
|-|-
[NegativeKeywordListSelector](./NegativeKeywordListSelector.md)|Selector of all negative keyword lists in this account. By default, the selector returns all negative keyword lists in this account. You can also use the selector's methods to return a filtered list of negative keyword lists.

## <a name="newnegativekeywordlistbuilder"></a>newNegativeKeywordListBuilder

Returns a negative keyword list [builder](../concepts/builders.md) for this account. 

### Returns

|Type|Description|
|-|-
[NegativeKeywordListBuilder](./NegativeKeywordListBuilder.md)|Negative keyword list builder for this account. Use the builder to add a negative keyword list to this account.

