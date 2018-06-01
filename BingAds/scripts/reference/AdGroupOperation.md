---
title: "AdGroupOperation object"
description: "Contains the methods for creating the ad group."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# AdGroupOperation

Contains the methods for adding the ad group. Use the [AdGroupBuilder](./AdGroupBuilder.md) object to define the ad group and create this operation object.

The ad group is added to the campaign only after calling any of this object's methods or after the script finishes execution, whichever comes first. To improve performance, store the operation objects in an array and only invoke its methods when all operations have been constructed. For more information about the builder and operation objects' usage, see [What are builders?](../concepts/builders.md)

## Methods
|Method Name|Return Type|Description|
|-|-|-
[getErrors](#geterrors)|string[]|Returns an empty array if the ad group is successfully created; otherwise, it contains the list of errors.
[getResult](#getresult)|[AdGroup](./AdGroup.md)|Returns the newly added ad group if the operation succeeded; otherwise, null.
[isSuccessful](#issuccessful)|Boolean|Returns a Boolean value that indicates whether this operation succeeded.

## <a name="geterrors"></a>getErrors
Returns an empty array if the ad group is successfully created; otherwise, it contains the list of errors.

### Returns
|Type|Description|
|-|-
string[]|Contains an empty array if the ad group is successfully created; otherwise, it contains the list of errors.

## <a name="getresult"></a>getResult
Returns the newly created ad group if the operation succeeded; otherwise, null.

### Returns
|Type|Description|
|-|-
[AdGroup](./AdGroup.md)|The newly created ad group if the operation succeeded; otherwise, null.

## <a name="issuccessful"></a>isSuccessful
Returns a Boolean value that indicates if this operation succeeded.

### Returns:
|Type|Description|
|-|-
Boolean|Returns **true** if the operation succeeded; otherwise, **false**.

