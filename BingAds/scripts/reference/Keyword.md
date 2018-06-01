---
title: "Keyword object"
description: "Contains the methods for managing a keyword."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Keyword
Contains the methods for managing a keyword. For information about keywords, see [Keyword](/bingads/guides/entity-hierarchy-limits#keyword).


# Methods
|Method Name|Return Type|Description|
|-|-|-
[adParams](#adparams)|[AdParamSelector](AdParamSelector.md)|Returns a selector of all substitution parameters used in the ad for this keyword.
[bidding](#bidding)|[KeywordBidding](./KeywordBidding.md)|Returns an object that contains the methods used to manage the keyword's bid values.
[clearDestinationUrl](#cleardestinationurl)|void|Clears the keyword's destination URL.
[enable](#enable)|void|Enables this keyword.
[getAdGroup](#getadgroup)|[AdGroup](AdGroup/md)|Returns the ad group this keyword belongs to.
[getApprovalStatus](#getapprovalstatus)|string|Returns the keyword's editorial approval status.
[getCampaign](#getcampaign)|[Campaign](./Campaign.md)|Returns the campaign this keyword belongs to.
[getEntityType](#getentitytype)|string|Returns the entity's type.
[getId](#getid)|string|Returns the ID that uniquely identifies this keyword.
[getMatchType](#getmatchtype)|String|Returns the keyword's match type.
[getStats](#getstats)|[Stats](./Stats.md)|Returns the performance data for this keyword.
[getText](#gettext)|string|Returns the keyword's text.
[isEnabled](#isenabled)|Boolean|Returns a Boolean value that indicates whether this keyword is enabled.
[isPaused](#ispaused)|Boolean|Returns a Boolean value that indicates whether this keyword is paused.
[pause](#pause)|void|Pauses this keyword.
[remove](#remove)|void|Removes this keyword.
[setAdParam(int index, string insertionText)](#setadparam~int-index~string-insertiontext~)|void|Sets the ad substitution value for the specified substitution parameter.
[urls](#urls)|[KeywordUrls](./KeywordUrls.md)|Returns the keyword's URL fields.



## <a name="adparams"></a>adParams
Returns a selector of all substitution parameters used in the ad for this keyword.

### Returns
|Type|Description|
|-|-
[AdParamSelector](AdParamSelector.md)|The selector that contains the list of substitution parameters for this keyword.


## <a name="bidding"></a>bidding
Returns an object that contains the methods used to manage the keyword's bid values.

### Returns
|Type|Description|
|-|-
[KeywordBidding](./KeywordBidding)|An object that contains the methods used to manage the keyword's bid values.

## <a name="cleardestinationurl"></a>clearDestinationUrl
Clears the keyword's destination URL.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="enable"></a>enable
Enables this keyword.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getadgroup"></a>getAdGroup
Returns the ad group this keyword belongs to.

### Returns
|Type|Description|
|-|-
[AdGroup](AdGroup.md)|The ad group this keyword belongs to.

## <a name="getapprovalstatus"></a>getApprovalStatus
Returns the keyword's editorial approval status.

### Returns
|Type|Description|
|-|-
string|The keyword's editorial approval status, which indicates whether the keyword is pending review, is approved, or is not allowed. Possible values are:<br /><ul><li>APPROVED</li><li>DISAPPROVED</li><li>PENDING_REVIEW</li><li>UNDER_REVIEW</li></ul>

## <a name="getcampaign"></a>getCampaign
Returns the campaign this keyword belongs to.

### Returns
|Type|Description|
|-|-
[Campaign](./Campaign.md)|The campaign this keyword belongs to.

## <a name="getentitytype"></a>getEntityType
Returns this entity's type.

### Returns
|Type|Description|
|-|-
string|This entity's type, which is Keyword.

## <a name="getid"></a>getId
Returns the ID that uniquely identifies this keyword.

### Returns
|Type|Description|
|-|-
string|The ID that uniquely identifies this keyword.

## <a name="getmatchtype"></a>getMatchType
Returns the keyword's match type. 

### Returns
|Type|Description|
|-|-
string|The keyword's match type. Possible values are:<br /><ul><li>BROAD</li><li>PHRASE</li><li>EXACT</li></ul>


## <a name="getstats"></a>getStats
Returns performance data for this keyword. 

### Returns
|Type|Description|
|-|-
[Stats](./Stats.md)|The performance data for the keyword.

## <a name="gettext"></a>getText
Returns the keyword's text. The text is returned in one of the following formats based on the keyword's match type:

- books - broad match
- "books" - phrase match
- [hardcover books] - exact match


### Returns
|Type|Description|
|-|-
string|The keyword's text.

## <a name="isenabled"></a>isEnabled
Returns a Boolean value that indicates whether this keyword is enabled.

### Returns
|Type|Description|
|-|-
Boolean|Returns **true*8 if this keyword is enabled; otherwise, **false**.

## <a name="ispaused"></a>isPaused
Returns a Boolean value that indicates whether this keyword is paused.

### Returns
|Type|Description|
|-|-
Boolean|Returns **true** if this keyword is paused; otherwise, **false**.


## <a name="setadparam~int-index~string-insertiontext~"></a>setAdParam(int index, string insertionText)
Sets the ad substitution value for the specified substitution parameter.

### Arguments
|Name|Type|Description|
|-|-|-
index|int|The index of the substitution parameter that you're setting the substitution value to. The valid index values are 1 through 3, inclusive.
insertionText|string|The text to set the substitution parameter to.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="pause"></a>pause
Pauses this keyword.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="remove"></a>remove
Removes this keyword.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="urls"></a>urls
Returns the Keyword's URL fields.

### Returns
|Type|Description|
|-|-
[KeywordUrls](./KeywordUrls.md)|The keyword's URL fields.



## See also

- [KeywordSelector](./KeywordSelector.md)
- [KeywordIterator](./KeywordIterator.md)
