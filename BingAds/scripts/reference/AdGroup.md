---
title: "AdGroup object"
description: "Contains the methods used to manage the ad group."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# AdGroup

Contains the methods used to manage the [ad group](/bingads/guides/entity-hierarchy-limits#adgroup).

## Methods
|Method Name|Return Type|Description|
|-|-|-
[bidding](#bidding)|[AdGroupBidding](AdGroupBidding)|Returns an object that contains the methods used to manage the ad group's bid values.
[enable](#enable)|void|Enables this ad group.
[getEndDate](#getenddate)|[BingAdsDate](BingAdsDate.md)|Returns date when ads in the ad group stop serving.
[getEntityType](#getentitytype)|string|Returns the entity's type.
[getId](#getid)|string|Returns the ID that uniquely identifies this ad group.
[getName](#getname)|string|Returns the name of this ad group.
[getStartDate](#getstartdate)|[BingAdsDate](BingAdsDate.md)|Returns date when ads in the ad group start serving.
[getStats](#getstats)|Stats.md|Returns the performance data for this ad group.
[isEnabled](#isenabled)|Boolean|Returns a Boolean value that indicates whether this ad group is enabled.
[isPaused](#ispaused)|Boolean|Returns a Boolean value that indicates whether this ad group is paused.
[isRemoved](#isremoved)|Boolean|Returns a Boolean value that indicates whether this ad group is removed.
[newKeywordBuilder](#newkeywordbuilder)|[KeywordBuilder](./KeywordBuilder.md)|Returns a keyword builder that you use to add keywords to this ad group.
[pause](#pause)|void|Pauses this ad group.
[setEndDate(string endDate)](#setenddate~string-endDate~)]void|Sets the date when ads in the ad group will stop serving.
[setEndDate(Object endDate)](#setenddate~object-enddate~)]|void|Sets the date when ads in the ad group will stop serving.
[setName(String name)](#setname-string-name)|void|Sets the ad group's name.
[setStartDate(string startDate)](#setstartdate~string-startDate~)]|void|Sets the date when ads in the ad group will begin serving.
[setStartDate(Object startDate)](#setstartdate~object-startdate~)]|void|Sets the date when ads in the ad group will begin serving.
[urls](#urls)|[AdGroupUrls](./AdGroupUrls.md)|Returns this ad group's URLs.

<!--
[newAd](#newad)|[AdBuilderSpace](./AdBuilderSpace)|Returns a new ad builder space associated with this ad group, which is used to construct a new ad.
-->


## <a name="bidding"></a>bidding
Returns an object that contains the methods used to manage the ad group's bid values. 

### Returns:
|Type|Description|
|-|-
[AdGroupBidding](AdGroupBidding)|Contains the methods used to manage the ad group's bid values.


## <a name="enable"></a>enable
Enables this ad group.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getenddate"></a>getEndDate
Returns the date when ads in the ad group stop serving.

### Returns
|Type|Description|
|-|-
[BingAdsDate](BingAdsDate.md)|The date when ads in the ad group stop serving.

## <a name="getentitytype"></a>getEntityType
Returns this entity's type.

### Returns
|Type|Description|
|-|-
string|This entity's type, which is AdGroup.

## <a name="getid"></a>getId
Returns the ID that uniquely identifies this ad group.

### Returns
|Type|Description|
|-|-
string|The ID that uniquely identifies this ad group.

## <a name="getname"></a>getName
Returns the name of this ad group.

### Returns
|Type|Description|
|-|-
string|The name of the ad group.


## <a name="getstartdate"></a>getStartDate
Returns the date when ads in the ad group start serving.

### Returns
|Type|Description|
|-|-
[BingAdsDate](BingAdsDate.md)|The date when ads in the ad group start serving.


## <a name="getstats"></a>getStats
Returns the performance data for the ad group. 

### Returns:
|Type|Description|
|-|-
[Stats](Stats.md)|The performance data for the ad group.


## <a name="isenabled"></a>isEnabled
Returns a Boolean value that indicates whether this ad group is enabled.

### Returns:
|Type|Description|
|-|-
Boolean|Returns **true** if this ad group is enabled; otherwise, **false**.

## <a name="ispaused"></a>isPaused
Returns a Boolean value that indicates whether this ad group is paused.

### Returns:
|Type|Description|
|-|-
Boolean|Returns **true** if this ad group is paused; otherwise, **false**.

## <a name="isremoved"></a>isRemoved
Returns a Boolean value that indicates whether this ad group is removed (deleted).

### Returns
|Type|Description|
|-|-
Boolean|Returns **true** if this ad group is removed; otherwise, **false**.

<!--
## <a name="newad"></a>newAd
Returns a new ad builder space associated with this ad group, which is used to construct a new ad.

### Returns:
|Type|Description|
|-|-
[AdBuilderSpace](./AdBuilderSpace)|A new ad builder space associated with this ad group.
-->

## <a name="newkeywordbuilder"></a>newKeywordBuilder
Returns a keyword builder that you use to add keywords to this ad group.

### Returns
|Type|Description|
|-|-
[KeywordBuilder](KeywordBuilder.md)|The keyword builder that you use to add keywords to this ad group.

## <a name="pause"></a>pause
Pauses this ad group.

### Returns
|Type|Description|
|-|-
void|Returns nothing.



## <a name="setenddate~string-enddate~"></a>setEndDate(string endDate)
Sets the date when you want ads in the ad group to stop serving. Set an end date only if you want ads in the group to stop serving on a specific date.

### Arguments
|Name|Type|Description|
|-|-|-
endDate|string|The date when you want ads in the ad group to stop serving. Specify the date in the form, YYYYMMDD.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="setenddate~object-enddate~"></a>setEndDate(Object endDate)
Sets the date when you want ads in the ad group to stop serving. Set an end date only if you want ads in the group to stop serving on a specific date.

### Arguments
|Name|Type|Description|
|-|-|-
endDate|Object|The date when you want ads in the ad group to stop serving. Specify the date using an object with the following fields:<br /><ul><li>year</li><li>month</li><li>day</li><br />For example:<br /><br /><code>var date = `{year: 2018, month: 5, day: 13}`;</code>

### Returns
|Type|Description|
|-|-
void|Returns nothing.




## <a name="setname-string-name"></a>setName(string name)
Sets the name of this ad group.

### Arguments
|Name|Type|Description|
|-|-|-
name|string|The name of the ad group. The name may contain a maximum of 256 characters and must be unique amongst all active ad groups within the campaign.

### Returns
|Type|Description|
|-|-
void|Returns nothing.



## <a name="setstartdate~string-startdate~"></a>setStartDate(string startDate)
Sets the date when you want ads in the ad group to start serving. Set a start date only if you want ads in the group to start serving on a specific date; otherwise, they may begin serving immediately.

### Arguments
|Name|Type|Description|
|-|-|-
endDate|string|The date when you want ads in the ad group to start serving. Specify the date in the form, YYYYMMDD.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="setstartdate~object-startdate~"></a>setStartDate(Object startDate)
Sets the date when you want ads in the ad group will start serving. Set a start date only if you want ads in the group to start serving on a specific date; otherwise, they may begin serving immediately.

### Arguments
|Name|Type|Description|
|-|-|-
endDate|Object|The date when you want ads in the ad group to start serving. Specify the date using an object with the following fields:<br /><ul><li>year</li><li>month</li><li>day</li><br />For example:<br /><br /><code>var date = `{year: 2018, month: 5, day: 13}`;</code>

### Returns
|Type|Description|
|-|-
void|Returns nothing.




## <a name="urls"></a>urls
Returns this ad group's URLs.

### Returns
|Type|Description|
|-|-
[AdGroupUrls](AdGroupUrls.md)|This ad group's urls.


## See also

- [AdGroupIterator.next()](AdGroupIterator.md#next)
- [AdGroupOperator.getResult()](AdGroupOperator.md#getresult)