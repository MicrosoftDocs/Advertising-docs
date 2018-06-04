---
title: "NegativeKeywordListOperation object"
description: "Contains the methods for creating the negative keyword list."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# NegativeKeywordListOperation

Contains the methods for creating the negative keyword list that you defined using the [NegativeKeywordListBuilder](./NegativeKeywordListBuilder.md).

The negative keyword list is added when you call this object's methods or after the script finishes execution, whichever comes first. To improve performance, store the operation objects in an array and only invoke its methods when all operations have been constructed. For more information about the builder and operation objects' usage, see [What are builders?](../concepts/builders.md)


## Methods
|Method Name|Return Type|Description|
|-|-|-
[getErrors](#geterrors)|string[]|Returns an empty array if the negative keywords list is successfully created; otherwise, a list of errors.
[getResult](#getresult)|[NegativeKeywordList](./NegativeKeywordList.md)|Returns the newly created negative keywords list if the operation succeeded; otherwise, null.
[isSuccessful](#issuccessful)|Boolean|Returns a Boolean value that indicates whether this operation succeeded.

## <a name="geterrors"></a>getErrors
Returns an empty array if the negative keywords list is successfully created; otherwise, a list of errors.

### Returns
|Type|Description|
|-|-
string[]|An empty array if the negative keywords list is successfully created; otherwise, a list of errors.

## <a name="getresult"></a>getResult
Returns the newly created negative keywords list if the operation succeeded; otherwise, null.

### Returns
|Type|Description|
|-|-
[NegativeKeywordList](./NegativeKeywordList.md)|The newly created negative keywords list if the operation succeeded; otherwise, null.

## <a name="issuccessful"></a>isSuccessful
Returns a Boolean value that indicates whether this operation succeeded.

### Returns
|Type|Description|
|-|-
Boolean|Returns **true** if this operation succeeded; otherwise, **false**.

