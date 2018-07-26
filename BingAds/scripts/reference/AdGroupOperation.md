---
title: "AdGroupOperation object"
description: "Contains the methods for determining whether the ad group was successfully added."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# AdGroupOperation

Contains the methods for determining whether the ad group was successfully added. For information about builders, operation objects, and performance considerations, see [What are builders?](../concepts/builders.md)

Because calling any of this object's methods forces Bing to flush the build queue, be sure to read the performance considerations carefully.


## Methods
|Method Name|Return Type|Description|
|-|-|-
[getErrors](#geterrors)|string[]|Gets any errors that occured when you added the ad group.
[getResult](#getresult)|[AdGroup](./AdGroup.md)|Gets the ad group that you added.
[isSuccessful](#issuccessful)|Boolean|Gets a Boolean value that indicates whether the add operation succeeded.

## <a name="geterrors"></a>getErrors
Gets any errors that occured when you added the ad group.

### Returns
|Type|Description|
|-|-
string[]|An array of error codes if the operation failed; otherwise, an empty array. For example, if you specify an invalid bid amount, the call returns CampaignServiceInvalidSearchBids. For a description of these codes, see [Operation error codes](/bingads/guides/operation-error-codes).

## <a name="getresult"></a>getResult
Gets the ad group that you added.

### Returns
|Type|Description|
|-|-
[AdGroup](./AdGroup.md)|The ad group that you created if the operation succeeded; otherwise, null.

## <a name="issuccessful"></a>isSuccessful
Gets a Boolean value that indicates whether the add operation succeeded.

### Returns:
|Type|Description|
|-|-
Boolean|Is **true** if the operation succeeded; otherwise, **false**.

