---
title: "ExpandedTextAd object"
description: "Contains the methods used to manage an expanded text ad."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# ExpandedTextAd

Contains the methods used to manage an expanded text ad. 

This object derives from the [Ad](Ad.md) object. The list of methods includes all applicable inherited methods. 


## Methods
|Method Name|Return Type|Description|Inherited
|-|-|-
[asType](#astype)|[AdViewSpace](AdViewSpace.md)|Contains the methods used to cast this ad to a specific ad type.|Yes
[enable](#enable)|void|Enables this ad.|Yes
[getAdGroup](#getadgroup)|[AdGroup](Adgroup.md)|Gets the ad group that this ad belongs to.|Yes
[getCampaign](#getcampaign)|[Campaign](Campaign.md)|Gets the campaign that this ad belongs to.|Yes
[getDescription](#getdescription)|string|Gets this ad's copy text.|Yes
[getEntityType](#getentitytype)|string|Gets this entity's type.|Yes
[getHeadlinePart1](#getheadlinepart1)|string|Gets the first part of this ad's title.|No
[getHeadlinePart2](#getheadlinepart2)|string|Gets the second part of this ad's title.|No
[getId](#getid)|string|Gets the ID that uniquely identifies this ad.|Yes
[getPath1](#getpath1)|string|Gets the optional first path that's appended to this ad's display URL.|No
[getPath2](#getpath2)|string|Gets the optional second path that's appended to this ad's display URL.|No
[getPolicyApprovalStatus](#getpolicyapprovalstatus)|string|Gets this ad's editorial approval status.|Yes
[getStats](#getstats)|[Stats](Stats.md)|Gets this ad's performance data.|Yes
[getType](#gettype)|string|Gets this ad's derived type.|Yes
[isEnabled](#isenabled)|boolean|Gets a Boolean value that indicates whether this ad is enabled.|Yes
[isPaused](#ispaused)|Boolean|Gets a Boolean value that indicates whether this ad is paused.|Yes
[isType](#istype)|[AdTypeSpace](AdTypeSpace.md)|Contains the methods used to test if an ad is of the specified type.|Yes
[pause](#pause)|void|Pauses this ad.|Yes
[remove](#remove)|void|Removes this ad.|Yes
[urls](#urls)|[AdUrls](AdUrls.md)|Contains the methods used to get this ad's final URLs, tracking template, and custom parameters.|Yes


## <a name="astype"></a>asType
Contains the methods used to cast this ad to a specific ad type.

### Returns
|Type|Description|
|-|-
[AdViewSpace](AdViewSpace.md)|Contains the methods used to cast this ad to a specific ad type.


## <a name="enable"></a>enable
Enables this ad. (Inherited)

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="getadgroup"></a>getAdGroup
Gets the ad group that this ad belongs to.

### Returns
|Type|Description|
|-|-
[AdGroup](Adgroup.md)|The ad group that this ad belongs to.


## <a name="getcampaign"></a>getCampaign
Gets the campaign that this ad belongs to.

### Returns
|Type|Description|
|-|-
[Campaign](Campaign.md)|The campaign that this ad belongs to.


## <a name="getentitytype"></a>getEntityType
Gets this entity's type.

### Returns
|Type|Description|
|-|-
string|This entity's type, which is *Ad*.


## <a name="getdescription"></a>getDescription
Gets this ad's copy text.

### Returns
|Type|Description|
|-|-
string|The ad's copy text.


## <a name="getheadlinepart1"></a>getHeadlinePart1
Gets the first part of this ad's title.

### Returns
|Type|Description|
|-|-
string|The first part of this ad's title.


## <a name="getheadlinepart2"></a>getHeadlinePart2
Gets the second part of this ad's title.

### Returns
|Type|Description|
|-|-
string|The second part of this ad's title.


## <a name="getid"></a>getId
Gets the ID that uniquely identifies this ad.

### Returns
|Type|Description|
|-|-
string|The ID that uniquely identifies this ad.


## <a name="getpath1"></a>getPath1
Gets the optional first path that's appended to this ad's display URL.

### Returns
|Type|Description|
|-|-
string|The first path that's appended to this ad's display URL.


## <a name="getpath2"></a>getPath2
Gets the optional second path that's appended to this ad's display URL.

### Returns
|Type|Description|
|-|-
string|The second path that's appended to this ad's display URL.


## <a name="getpolicyapprovalstatus"></a>getPolicyApprovalStatus
Gets this ad's editorial approval status.

### Returns
|Type|Description|
|-|-
string|The ad's editorial approval status. The following are the possible values.<ul><li>APPROVED</li><li>APPROVED_LIMITED</li><li>UNDER_REVIEW</li><li>DISAPPROVED</li></ul>


## <a name="getstats"></a>getStats
Gets this ad's performance data. 

### Returns
|Type|Description|
|-|-
[Stats](Stats.md)|The ad's performance data.


## <a name="gettype"></a>getType
Gets this ad's derived type.

### Returns
|Type|Description|
|-|-
string|This ad's derived type. The following are the possible types.<ul><li>EXPANDED_TEXT_AD</li></ul>.


## <a name="isenabled"></a>isEnabled
Gets a Boolean value that indicates whether this ad is enabled.

### Returns
|Type|Description|
|-|-
boolean|Is **true** if this ad is enabled; otherwise, **false**.


## <a name="ispaused"></a>isPaused
Gets a Boolean value that indicates whether this ad is paused.

### Returns
|Type|Description|
|-|-
Boolean|Is **true** if this ad is paused; otherwise, **false**.


## <a name="istype"></a>isType
Contains the methods used to test if an ad is of the specified type.

### Returns
|Type|Description|
|-|-
[AdTypeSpace](AdTypeSpace.md)|Contains the methods used to test if an ad is of the specified type.


## <a name="pause"></a>pause
Pauses this ad.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="remove"></a>remove
Removes this ad.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="urls"></a>urls
Contains the methods used to get this ad's final URLs, tracking template, and custom parameters.

### Returns
|Type|Description|
|-|-
[AdUrls](AdUrls.md)|The object used to get this ad's final URLs, tracking template, and custom parameters.



## See also

- [AdIterator.next()](AdIterator.md#next)
- [AdOperation.getResult()](AdOperation.md#getresult)
- [Ad](Ad.md)
