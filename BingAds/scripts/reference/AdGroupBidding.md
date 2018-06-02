---
title: "AdGroupBidding object"
description: "Contains the methods for specifying the ad group's bid values."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# AdGroupBidding

Contains the methods used to manage the ad group's bid values.

## Methods
|Method Name|Return Type|Description|
|-|-|-
[clearCpc](#clearcpc)|void|Clears the ad group's CPC bid.
[getCpc](#getcpc)|double|Returns the ad group's CPC bid.
[setCpc(double cpc)](#setcpc~double-cpc~)|void|Sets the maximum CPC bid for the ad group.

## <a name="clearcpc"></a>clearCpc
Clears the ad group's CPC bid. 

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getcpc"></a>getCpc
Returns the ad group's CPC bid. 

### Returns
|Type|Description|
|-|-
double|The ad group's maximum CPC bid.

## <a name="setcpc~double-cpc~"></a>setCpc(double cpc)
Sets the maximum CPC bid for the ad group. 

### Arguments
|Name|Type|Description|
|-|-|-
cpc|double|The maximum CPC bid for the ad group.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## See also

[AdGroup.bidding()](AdGroup.md#bidding)