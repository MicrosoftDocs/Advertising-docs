---
title: "Campaign object"
description: "Contains the methods used to manage the ad group."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Campaign

Contains the methods used to manage a [campaign](/advertising/guides/entity-hierarchy-limits#campaign).

## Methods
|Method Name|Return Type|Description|
|-|-|-
[addNegativeKeywordList(NegativeKeywordList negativeKeywordList)](#addnegativekeywordlist-negativekeywordlist-negativekeywordlist-)|void|Adds a negative keyword list to this campaign.
[adgroups](#adgroups)|[AdGroupSelector](./AdGroupSelector.md)|Gets a [selector](../concepts/selectors.md) used to filter the list of ad groups in this campaign.
[ads](#ads)|[AdSelector](./AdSelector.md)|Gets a [selector](../concepts/selectors.md) used to filter the list of ads in this campaign.
[enable](#enable)|void|Enables this campaign.
[getBiddingStrategyType](#getbiddingstrategytype)|string|Gets this campaign's bidding strategy.
[getBudget](#getbudget)|[Budget](Budget.md)|Gets this campaign's budget.
[getEntityType](#getentitytype)|string|Gets this entity's type.
[getId](#getid)|string|Gets the ID that uniquely identifies this campaign.
[getName](#getname)|string|Gets this campaign's name.
[getStats](#getstats)|[Stats](Stats.md)|Gets this campaign's performance data.
[isEnabled](#isenabled)|boolean|Gets a Boolean value that indicates whether this campaign is enabled.
[isPaused](#ispaused)|Boolean|Gets a Boolean value that indicates whether this campaign is paused.
[isRemoved](#isremoved)|Boolean|Gets a Boolean value that indicates whether this campaign is removed (deleted).
[keywords](#keywords)|[KeywordSelector](./KeywordSelector.md)|Gets a [selector](../concepts/selectors.md) used to filter the list of keywords in this campaign.
[newAdGroupBuilder](#newadgroupbuilder)|[AdGroupBuilder](./AdGroupBuilder.md)|Gets a builder used to add an ad group to this campaign.
[pause](#pause)|void|Pauses this campaign.
[remove](#remove)|void|Removes this campaign.
[setName(String name)](#setname-string-name-)|void|Sets this campaign's name.
[urls](#urls)|[CampaignUrls](./CampaignUrls.md)|Gets the methods for managing this campaign's tracking template and custom parameters.


## <a name="addnegativekeywordlist-negativekeywordlist-negativekeywordlist-"></a>addNegativeKeywordList(NegativeKeywordList negativeKeywordList)
Adds a negative keyword list to this campaign. 

### Arguments
|Name|Type|Description|
|-|-|-
negativeKeywordList|[NegativeKeywordList](NegativeKeywordList.md)|The negative keyword list to add to this campaign. A campaign may contain a maximum of 20 lists.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="adgroups"></a>adGroups

Gets a [selector](../concepts/selectors.md) used to filter the list of ad groups in this campaign. 

### Returns

|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector.md)|A selector used to filter the list of ad groups in this campaign.


## <a name="ads"></a>ads

Gets a [selector](../concepts/selectors.md) used to filter the list of ads in this campaign. 

### Returns

|Type|Description|
|-|-
[AdSelector](./AdSelector.md)|A selector used to filter the list of ads in this campaign.


## <a name="enable"></a>enable
Enables this campaign.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="getbiddingstrategytype"></a>getBiddingStrategyType
Gets this campaign's bidding strategy. 

### Returns
|Type|Description|
|-|-
string|The campaign's bidding strategy. Possible values are:<br /><ul><li>MANUAL\_CPC</li><li>TARGET\_SPEND</li><li>MAXIMIZE\_CONVERSIONS</li><li>ENHANCED\_CPC</li><li>TARGET\_CPA</li></ul>For more information, see [Bid Strategies](../concepts/bid-strategies.md).


## <a name="getbudget"></a>getBudget
Gets this campaign's budget.

### Returns
|Type|Description|
|-|-
[Budget](Budget.md)|Contains the methods for managing this campaign's budget.


## <a name="getentitytype"></a>getEntityType
Gets this entity's type.

### Returns
|Type|Description|
|-|-
string|This entity's type, which is *Campaign*.


## <a name="getid"></a>getId
Gets the ID that uniquely identifies this campaign.

### Returns
|Type|Description|
|-|-
string|The ID that uniquely identifies this campaign.


## <a name="getname"></a>getName
Gets this campaign's name.

### Returns:
|Type|Description|
|-|-
string|The campaign's name.


## <a name="getstats"></a>getStats
Gets this campaign's performance data. 

### Returns
|Type|Description|
|-|-
[Stats](Stats.md)|The campaign's performance data.


## <a name="isenabled"></a>isEnabled
Gets a Boolean value that indicates whether this campaign is enabled.

### Returns
|Type|Description|
|-|-
boolean|Is **true** if this campaign is enabled; otherwise, **false**.


## <a name="ispaused"></a>isPaused
Gets a Boolean value that indicates whether this campaign is paused.

### Returns
|Type|Description|
|-|-
Boolean|Is **true** if this campaign is paused; otherwise, **false**.


## <a name="isremoved"></a>isRemoved
Gets a Boolean value that indicates whether this campaign is removed (deleted).

### Returns
|Type|Description|
|-|-
Boolean|Is **true** if this campaign is removed; otherwise, **false**.


## <a name="keywords"></a>keywords

Gets a [selector](../concepts/selectors.md) used to filter the list of keywords in this campaign. 

### Returns

|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector.md)|A selector used to filter the list of keywords in this campaign. 


## <a name="newadgroupbuilder"></a>newAdGroupBuilder
Gets a [builder](../concepts/builders.md) used to add an ad group to this campaign.

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](AdGroupBuilder.md)|The builder used to add an ad group to this campaign.


## <a name="pause"></a>pause
Pauses this campaign.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="remove"></a>remove
Removes this campaign.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="setname-string-name-"></a>setName(string name)
Sets the campaign's name.

### Arguments
|Name|Type|Description|
|-|-|-
name|string|The campaign's name. The name may contain a maximum of 128 characters and must be unique within the account.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="urls"></a>urls
Gets the methods for managing this campaign's tracking template and custom parameters.

### Returns
|Type|Description|
|-|-
[CampaignUrls](CampaignUrls.md)|Contains the methods for managing this campaign's tracking template and custom parameters.



## See also

- [CampaignIterator.next()](CampaignIterator.md#next)
