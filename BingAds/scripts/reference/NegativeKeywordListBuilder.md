---
title: "NegativeKeywordListBuilder object"
description: "Contains the methods for defining a negative keyword list."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# NegativeKeywordListBuilder

Contains the methods for defining a negative keyword list. For information about Builders, see [Builders](../concepts/builders.md).

Example usage:
```javascript
 var negativeKeywordListBuilder = BingAdsApp.newNegativeKeywordListBuilder()
         .withName("NegativeKeywordList");

 var negativeKeywordListOperation = negativeKeywordListBuilder.build();

 var negativeKeywordList = negativeKeywordListOperation.getResult();
```


# Methods
|Method Name|Return Type|Description|
|-|-|-
[build](#build)|[NegativeKeywordListOperation](./NegativeKeywordListOperation.md)|Returns an operation object, which represents the negative keyword list to create. You must call the operation object's methods to add the negative keyword list to the account.
[withName(string name)](#withname~string-name~)|[NegativeKeywordListBuilder](./NegativeKeywordListBuilder.md)|Sets the name of the negative keyword list.

## <a name="build"></a>build
Returns an operation object, which represents the negative keyword list to create. You must call the operation object's methods to add the negative keyword list to the account.

### Returns
|Type|Description|
|-|-
[NegativeKeywordListOperation](./NegativeKeywordListOperation.md)|An operation object, which you use to add the negative keyword list to the account.

## <a name="withname~string-name~"></a>withName(string name)
Sets the name of the negative keyword list.

### Arguments
|Name|Type|Description|
|-|-|-
name|string|The name of the negative keyword list.

### Returns
|Type|Description|
|-|-
[NegativeKeywordListBuilder](./NegativeKeywordListBuilder.md)|Negative keyword list builder with the name applied.

