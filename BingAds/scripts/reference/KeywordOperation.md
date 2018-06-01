---
title: "KeywordOperation object"
description: "Contains the methods for creating the keyword."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# KeywordOperation
Contains the methods for adding the keyword. Use the [KeywordBuilder](KeywordBuilder.md) object to define the keyword and create this operation object.

The keyword is added only after calling any of this object's methods or after the script finishes execution, whichever comes first. To improve performance, store the operation objects in an array and only invoke its methods when all operations have been constructed. For more information about the builder and operation objects' usage, see [What are builders?](../concepts/builders.md)


## Methods
|Method Name|Return Type|Description|
|-|-|-
[getErrors](#geterrors)|string[]|Returns an empty array if the keyword is successfully created; otherwise, it contains the list of errors.
[getResult](#getresult)|[Keyword](./Keyword)|Returns the newly added keyword if the operation succeeded; otherwise, null.
[isSuccessful](#issuccessful)|boolean|Returns a Boolean value that indicates whether this operation succeeded.

## <a name="geterrors"></a>getErrors
Returns an empty array if the keyword is successfully created; otherwise, it contains the list of errors.

### Returns
|Type|Description|
|-|-
string[]|An empty array if the keyword is successfully created; otherwise, it contains the list of errors.

## <a name="getresult"></a>getResult
Returns the newly added keyword if the operation succeeded; otherwise, null.

### Returns
|Type|Description|
|-|-
[Keyword](./Keyword.md)|The newly added keyword; otherwise, null.

## <a name="issuccessful"></a>isSuccessful
Returns a Boolean value that indicates whether this operation succeeded.

### Returns
|Type|Description|
|-|-
Boolean|Returns **true** if this operation succeeded; otherwise, **false**.

