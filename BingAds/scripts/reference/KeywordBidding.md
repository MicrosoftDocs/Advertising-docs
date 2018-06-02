---
title: "KeywordBidding object"
description: "Contains the methods for specifying the keyword's bid values."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# KeywordBidding

Contains the methods for specifying the keyword's bid values.

## Methods
|Method Name|Return Type|Description|
|-|-|-
[clearCpc](#clearcpc)|void|Removes the keyword's CPC bid.
[getCpc](#getcpc)|double|Returns the keyword's CPC bid.
[setCpc(double cpc)](#setcpc~double-cpc~)|void|Sets the maximum CPC bid for the keyword.

## <a name="clearcpc"></a>clearCpc
Removes the keyword's CPC bid. 

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getcpc"></a>getCpc
Returns the keyword's CPC bid. 

### Returns
|Type|Description|
|-|-
double|The keyword's CPC bid.

## <a name="setcpc~double-cpc~"></a>setCpc(double cpc)
Sets the maximum CPC bid for the keyword. 

### Arguments
|Name|Type|Description|
|-|-|-
cpc|double|The maximum CPC bid for the keyword.

### Returns
|Type|Description|
|-|-
void|Returns nothing.



## See also

[Keyword.bidding()](Keyword.md#bidding)