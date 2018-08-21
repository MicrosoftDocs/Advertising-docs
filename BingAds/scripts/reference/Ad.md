---
title: "Ad object"
description: "The base object that ads such as expanded text ads derive from."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Ad

The base object that ads such as expanded text ads derive from.


## Methods
|Method Name|Return Type|Description|
|-|-|-
[asType](#astype)|[AdViewSpace](AdViewSpace.md)|Contains the methods used to cast this ad to a specific ad type.
[getEntityType](#getentitytype)|string|Gets this entity's type.
[getId](#getid)|string|Gets the ID that uniquely identifies this ad.
[getPolicyApprovalStatus](#getpolicyapprovalstatus)|string|Gets this ad's editorial approval status.
[getType](#gettype)|string|Gets this ad's derived type.
[isType](#istype)|[AdTypeSpace](AdTypeSpace.md)|Contains the methods used to test if an ad is of the specified type..
[urls](#urls)|[AdUrls](AdUrls.md)|Contains the methods used to get this ad's final URLs, tracking template, and custom parameters.

## <a name="astype"></a>asType
Contains the methods used to cast this ad to a specific ad type.

### Returns
|Type|Description|
|-|-
[AdViewSpace](AdViewSpace.md)|Contains the methods used to cast this ad to a specific ad type.


## <a name="getentitytype"></a>getEntityType
Gets this entity's type.

### Returns
|Type|Description|
|-|-
string|This entity's type, which is *Ad*.


## <a name="getid"></a>getId
Gets the ID that uniquely identifies this ad.

### Returns
|Type|Description|
|-|-
string|The ID that uniquely identifies this ad.


## <a name="getpolicyapprovalstatus"></a>getPolicyApprovalStatus
Gets this ad's editorial approval status.

### Returns
|Type|Description|
|-|-
string|The ad's editorial approval status. The following are the possible values.<ul><li>APPROVED</li><li>APPROVED_LIMITED</li><li>UNDER_REVIEW</li><li>DISAPPROVED</li></ul>


## <a name="gettype"></a>getType
Gets this ad's derived type.

### Returns
|Type|Description|
|-|-
string|This ad's derived type. The following are the possible types.<ul><li>EXPANDED_TEXT_AD</li></ul>.


## <a name="istype"></a>isType
Contains the methods used to test if an ad is of the specified type.

### Returns
|Type|Description|
|-|-
[AdTypeSpace](AdTypeSpace.md)|Contains the methods used to test if an ad is of the specified type.


## <a name="urls"></a>urls
Contains the methods used to get this ad's final URLs, tracking template, and custom parameters.

### Returns
|Type|Description|
|-|-
[AdUrls](AdUrls.md)|The object used to get this ad's final URLs, tracking template, and custom parameters.


## See also

- [AdIterator.next()](AdIterator.md#next)
- [AdOperation.getResult()](AdOperation.md#getresult)
- [ExpandedTextAd](ExpandedTextAd.md)