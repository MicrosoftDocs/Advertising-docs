---
title: "Campaign object"
description: "Contains the methods used to manage the ad group."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Campaign

Contains the methods used to manage the [campaign](/bingads/guides/entity-hierarchy-limits#campaign).

## Methods
|Method Name|Return Type|Description|
|-|-|-
[addNegativeKeywordList(NegativeKeywordList negativeKeywordList)](#addnegativekeywordlist~negativekeywordlist-negativekeywordlist~)|void|Adds a negative keyword list to this campaign.
[enable](#enable)|void|Enables this campaign.
[getBiddingStrategyType](#getbiddingstrategytype)|string|Returns the campaign's bidding strategy.
[getBudget](#getbudget)|[Budget](Budget.md)|Returns the campaign's budget.
[getEntityType](#getentitytype)|string|Returns this object's entity type.
[getId](#getid)|string|Returns the ID that uniquely identifies this campaign.
[getName](#getname)|string|Returns the campaign's name.
[getStats](#getstats)|[Stats](Stats.md)|Returns the performance data for this campaign.
[isEnabled](#isenabled)|boolean|Returns a Boolean value that determines whether this campaign is enabled.
[isPaused](#ispaused)|Boolean|Returns a Boolean value that indicates whether this campaign is paused.
[isRemoved](#isremoved)|Boolean|Returns a Boolean value that indicates whether this campaign is removed (deleted).
[newAdGroupBuilder](#newadgroupbuilder)|[AdGroupBuilder](./AdGroupBuilder.md)|Returns an ad group builder that you use to add ad groups to this campaign.
[pause](#pause)|void|Pauses this campaign.
[remove](#remove)|void|Removes this campaign.
[setName(String name)](#setname~string-name~)|void|Sets the name of this campaign.
[urls](#urls)|[CampaignUrls](./CampaignUrls.md)|Returns this campaign's URLs.

## <a name="addnegativekeywordlist~negativekeywordlist-negativekeywordlist~"></a>addNegativeKeywordList(NegativeKeywordList negativeKeywordList)
Adds a negative keyword list to this campaign. 

### Arguments
|Name|Type|Description|
|-|-|-
negativeKeywordList|[NegativeKeywordList](NegativeKeywordList.md)|The negative keyword list to add to the campaign.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="enable"></a>enable
Enables this campaign.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getbiddingstrategytype"></a>getBiddingStrategyType
Returns the campaign's bidding strategy. 

### Returns
|Type|Description|
|-|-
string|The campaign's bidding strategy. Possible values are:<br /><ul><li>MANUAL_CPC</li><li>TARGET_SPEND</li><li>MAXIMIZE_CONVERSIONS</li><li>ENHANCED_CPC</li><li>TARGET_CPA</li></ul>
For more information, see [Bid Strategies](../concepts/bid-strategies.md).

## <a name="getbudget"></a>getBudget
Returns the budget for this campaign.

### Returns
|Type|Description|
|-|-
[Budget](Budget.md)|The budget for this campaign.

## <a name="getentitytype"></a>getEntityType
Returns the entity's type.

### Returns
|Type|Description|
|-|-
string|This entity's type, which is Campaign.

## <a name="getid"></a>getId
Returns the ID that uniquely identifies this campaign.

### Returns
|Type|Description|
|-|-
string|The ID that uniquely identifies this campaign.

## <a name="getname"></a>getName
Returns the name of this campaign.

### Returns:
|Type|Description|
|-|-
string|The name of this campaign.

## <a name="getstats"></a>getStats
Returns the performance data for the campaign. 

### Returns
|Type|Description|
|-|-
[Stats](Stats.md)|The campaign's performance data.

## <a name="isenabled"></a>isEnabled
Returns a Boolean value that determines whether this campaign is enabled.

### Returns
|Type|Description|
|-|-
boolean|Returns **true** if this campaign is enabled; otherwise, **false**.

## <a name="ispaused"></a>isPaused
Returns a Boolean value that indicates whether this campaign is paused.

### Returns
|Type|Description|
|-|-
Boolean|Returns **true** if this campaign is paused; otherwise, **false**.

## <a name="isremoved"></a>isRemoved
Returns a Boolean value that indicates whether this campaign is removed (deleted).

### Returns
|Type|Description|
|-|-
Boolean|Returns **true** if this campaign is removed; otherwise, **false**.

## <a name="newadgroupbuilder"></a>newAdGroupBuilder
Returns an ad group builder that you use to add an ad group to this campaign.

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](AdGroupBuilder.md)|The ad group builder that you use to add an ad group to this campaign.

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

## <a name="setname~string-name~"></a>setName(string name)
Sets the name of this campaign.

### Arguments
|Name|Type|Description|
|-|-|-
name|string|The name of the campaign.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="urls"></a>urls
Returns this campaign's URLs.

### Returns
|Type|Description|
|-|-
[CampaignUrls](CampaignUrls.md)|This campaign's URLs.



## See also

- [CampaignIterator.next()](CampaignIterator.md#next)
