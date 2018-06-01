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
[clearCpc](#clearcpc)|void|Clears the CPC bid for the ad group.
[getCpc](#getcpc)|double|Returns the CPC bid for the ad group.
[setCpc(double cpc)](#setcpc~double-cpc~)|void|Sets the maximum CPC bid for the ad group.

## <a name="clearcpc"></a>clearCpc
Clears the CPC bid for the ad group. 

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getcpc"></a>getCpc
Returns the CPC bid for the ad group. 

### Returns
|Type|Description|
|-|-
double|The maximum CPC bid for the ad group.

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