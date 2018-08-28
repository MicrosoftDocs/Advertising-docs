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

Contains the methods used to manage an expanded text ad. This object derives from [Ad](Ad.md).


## Methods
|Method Name|Return Type|Description|
|-|-|-
[getAdGroup](#getadgroup)|[AdGroup](Adgroup.md)|Gets the ad group that this ad belongs to.
[getCampaign](#getcampaign)|[Campaign](Campaign.md)|Gets the campaign that this ad belongs to.
[getDescription](#getdescription)|string|Gets this ad's copy text.
[getHeadlinePart1](#getheadlinepart1)|string|Gets the first part of this ad's title.
[getHeadlinePart2](#getheadlinepart2)|string|Gets the second part of this ad's title.
[getPath1](#getpath1)|string|Gets the optional first path that's appended to this ad's display URL.
[getPath2](#getpath2)|string|Gets the optional second path that's appended to this ad's display URL.
[getStats](#getstats)|[Stats](Stats.md)|Gets this ad's performance data.
[urls](#urls)|[AdUrls](AdUrls.md)|Contains the methods used to get this ad's final URLs, tracking template, and custom parameters.


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


## <a name="getstats"></a>getStats
Gets this ad's performance data. 

### Returns
|Type|Description|
|-|-
[Stats](Stats.md)|The ad's performance data.


## <a name="urls"></a>urls
Contains the methods used to get this ad's final URLs, tracking template, and custom parameters.

### Returns
|Type|Description|
|-|-
[AdUrls](AdUrls.md)|The object used to get this ad's final URLs, tracking template, and custom parameters.
