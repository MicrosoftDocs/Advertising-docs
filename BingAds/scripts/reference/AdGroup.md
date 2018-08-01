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

Contains the methods used to manage an [ad group](/bingads/guides/entity-hierarchy-limits#adgroup).

## Methods
|Method Name|Return Type|Description|
|-|-|-
[bidding](#bidding)|[AdGroupBidding](AdGroupBidding.md)|Gets the methods used to manage this ad group's bid amount.
[enable](#enable)|void|Enables this ad group.
[getEndDate](#getenddate)|[BingAdsDate](BingAdsDate.md)|Gets the date when ads in this ad group stop serving.
[getEntityType](#getentitytype)|string|Gets this entity's type.
[getId](#getid)|string|Gets the ID that uniquely identifies this ad group.
[getName](#getname)|string|Gets this ad group's name.
[getStartDate](#getstartdate)|[BingAdsDate](BingAdsDate.md)|Get the date when ads in this ad group start serving.
[getStats](#getstats)|[Stats](Stats.md)|Gets the performance data for this ad group.
[isEnabled](#isenabled)|Boolean|Gets a Boolean value that indicates whether this ad group is enabled.
[isPaused](#ispaused)|Boolean|Gets a Boolean value that indicates whether this ad group is paused.
[isRemoved](#isremoved)|Boolean|Gets a Boolean value that indicates whether this ad group is removed.
[newAd](#newad)|[AdBuilderSpace](./AdBuilderSpace.md)|Gets an object that contains methods for getting ad builders.
[newKeywordBuilder](#newkeywordbuilder)|[KeywordBuilder](./KeywordBuilder.md)|Gets a builder that you use to add a keyword to this ad group.
[pause](#pause)|void|Pauses this ad group.
[setEndDate(string endDate)](#setenddate-string-enddate-)|void|Sets the date when ads in this ad group stop serving.
[setEndDate(Object endDate)](#setenddate-object-enddate-)|void|Sets the date when ads in this ad group stop serving.
[setName(String name)](#setname-string-name)|void|Sets the ad group's name.
[setStartDate(string startDate)](#setstartdate-string-startdate-)|void|Sets the date when ads in this ad group begin serving.
[setStartDate(Object startDate)](#setstartdate-object-startdate-)|void|Sets the date when ads in this ad group begin serving.
[urls](#urls)|[AdGroupUrls](./AdGroupUrls.md)|Contains the methods used to manage this ad group's final URLs, tracking template, and custom parameters.


## <a name="bidding"></a>bidding
Gets the methods used to manage this ad group's bid amount.

### Returns:
|Type|Description|
|-|-
[AdGroupBidding](AdGroupBidding.md)|Contains the methods for managing this ad group's bid amount.


## <a name="enable"></a>enable
Enables this ad group.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getenddate"></a>getEndDate
Gets the date when ads in this ad group stop serving.

### Returns
|Type|Description|
|-|-
[BingAdsDate](BingAdsDate.md)|The date when ads in this ad group stop serving.

## <a name="getentitytype"></a>getEntityType
Gets this entity's type.

### Returns
|Type|Description|
|-|-
string|This entity's type, which is *AdGroup*.

## <a name="getid"></a>getId
Gets the ID that uniquely identifies this ad group.

### Returns
|Type|Description|
|-|-
string|The ID that uniquely identifies this ad group.

## <a name="getname"></a>getName
Gets this ad group's name.

### Returns
|Type|Description|
|-|-
string|The name of this ad group.


## <a name="getstartdate"></a>getStartDate
Gets the date when ads in this ad group start serving.

### Returns
|Type|Description|
|-|-
[BingAdsDate](BingAdsDate.md)|The date when ads in this ad group start serving.


## <a name="getstats"></a>getStats
Gets the performance data for this ad group. 

### Returns:
|Type|Description|
|-|-
[Stats](Stats.md)|The performance data for this ad group.


## <a name="isenabled"></a>isEnabled
Gets a Boolean value that indicates whether this ad group is enabled.

### Returns:
|Type|Description|
|-|-
Boolean|Is **true** if this ad group is enabled; otherwise, **false**.

## <a name="ispaused"></a>isPaused
Gets a Boolean value that indicates whether this ad group is paused.

### Returns:
|Type|Description|
|-|-
Boolean|Is **true** if this ad group is paused; otherwise, **false**.

## <a name="isremoved"></a>isRemoved
Gets a Boolean value that indicates whether this ad group is removed (deleted).

### Returns
|Type|Description|
|-|-
Boolean|Is **true** if this ad group is removed; otherwise, **false**.

## <a name="newad"></a>newAd
Gets an object that contains methods for getting ad builders.

### Returns

|Type|Description|
|-|-
[AdBuilderSpace](./AdBuilderSpace)|An object that contains methods for getting ad builders. For example, if you want to build an expanded text ad, you'd call the object's `expandedTextAdBuilder` method to get the [ExpandedTextAdBuilder](ExpandedTextAdBuilder.md) object.

## <a name="newkeywordbuilder"></a>newKeywordBuilder
Gets a [builder](../concepts/builders.md) that you use to add a keyword to this ad group.

### Returns
|Type|Description|
|-|-
[KeywordBuilder](KeywordBuilder.md)|The builder that you use to add a keyword to this ad group.

## <a name="pause"></a>pause
Pauses this ad group.

### Returns
|Type|Description|
|-|-
void|Returns nothing.



## <a name="setenddate-string-enddate-"></a>setEndDate(string endDate)
Sets the date when you want ads in this ad group to stop serving. Set an end date only if you want ads in the group to stop serving on a specific date.

### Arguments
|Name|Type|Description|
|-|-|-
endDate|string|The date when you want ads in the ad group to stop serving. Specify the date in the form, YYYYMMDD.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="setenddate-object-enddate-"></a>setEndDate(Object endDate)
Sets the date when you want ads in this ad group to stop serving. Set an end date only if you want ads in the group to stop serving on a specific date.

### Arguments
|Name|Type|Description|
|-|-|-
endDate|Object|The date when you want ads in this ad group to stop serving. Specify the date using an object with the following fields:<br /><ul><li>year</li><li>month</li><li>day</li></ul>For example: `var date = {year: 2018, month: 5, day: 13};`<br /><br />The month is one-based where 1 is January and 12 is December.

### Returns
|Type|Description|
|-|-
void|Returns nothing.




## <a name="setname-string-name"></a>setName(string name)
Sets this ad group's name.

### Arguments
|Name|Type|Description|
|-|-|-
name|string|The name of this ad group. The name may contain a maximum of 256 characters and must be unique amongst all ad groups in the campaign.

### Returns
|Type|Description|
|-|-
void|Returns nothing.



## <a name="setstartdate-string-startdate-"></a>setStartDate(string startDate)
Sets the date when you want ads in this ad group to start serving. Set a start date only if you want ads in the group to start serving on a specific date; otherwise, they start serving immediately.

### Arguments
|Name|Type|Description|
|-|-|-
endDate|string|The date when you want ads in this ad group to start serving. Specify the date in the form, YYYYMMDD.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="setstartdate-object-startdate-"></a>setStartDate(Object startDate)
Sets the date when you want ads in this ad group to start serving. Set a start date only if you want ads in the group to start serving on a specific date; otherwise, they start serving immediately.

### Arguments
|Name|Type|Description|
|-|-|-
endDate|Object|The date when you want ads in this ad group to start serving. Specify the date using an object with the following fields:<br /><ul><li>year</li><li>month</li><li>day</li></ul>For example: `var date = {year: 2018, month: 5, day: 13};`<br /><br />The month is one-based where 1 is January and 12 is December.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="urls"></a>urls
Contains the methods used to manage this ad group's final URLs, tracking template, and custom parameters.

### Returns
|Type|Description|
|-|-
[AdGroupUrls](AdGroupUrls.md)|The object used to manage this ad group's final URLs, tracking template, and custom parameters.


## See also

- [AdGroupIterator.next()](AdGroupIterator.md#next)
- [AdGroupOperation.getResult()](AdGroupOperation.md#getresult)