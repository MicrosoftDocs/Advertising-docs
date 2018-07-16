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
[setCpc(double cpc)](#setcpc-double-cpc-)|void|Sets the maximum CPC bid for the ad group.

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

## <a name="setcpc-double-cpc-"></a>setCpc(double cpc)
Sets the CPC bid for the ad group. 

Specifies the bid amount to use when the keyword matches the user's search term and the ad group's bid strategy is ManualCpc or EnhancedCpc. This bid is used if a lower-level entity such as keyword does not override it.

If you specify a property value that's not valid, the call silently fails. To confirm whether the property was actually updated, you must get the object again and test whether the property's value equals the new value. For information, see [Handling errors and warnings](../concepts/errors-and-warnings.md).

### Arguments
|Name|Type|Description|
|-|-|-
cpc|double|The CPC bid for the ad group. The account's currency determines the minimum and maximum bid values. For more information, see [Bid and budget currencies](/bingads/guides/currencies#bidandbudget).

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## See also

[AdGroup.bidding()](AdGroup.md#bidding)