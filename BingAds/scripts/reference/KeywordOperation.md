---
title: "KeywordOperation object"
description: "Contains the methods for determining whether the keyword was successfully added."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# KeywordOperation

Contains the methods for determining whether the keyword was successfully added. For information about builders, operation objects, and performance considerations, see [What are builders?](../concepts/builders.md)

## Methods

|Method Name|Return Type|Description|
|-|-|-
[getErrors](#geterrors)|string[]|Returns an empty array if the keyword is successfully created; otherwise, a list of errors.
[getResult](#getresult)|[Keyword](./Keyword.md)|Returns the newly added keyword if the operation succeeded; otherwise, null.
[isSuccessful](#issuccessful)|boolean|Returns a Boolean value that indicates whether this operation succeeded.

## <a name="geterrors"></a>getErrors

Returns an empty array if the keyword is successfully created; otherwise, a list of error codes.

### Returns

|Type|Description|
|-|-
string[]|An empty array if the keyword is successfully created; otherwise, a list of symbolic error codes. For example, if you specify an invalid bid amount, the call returns CampaignServiceInvalidSearchBids. For a description of these codes, see [Operation error codes](/bingads/guides/operation-error-codes).


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

