---
title: "AdGroupIterator object"
description: "Contains the methods for iterating through a list of keywords."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# KeywordIterator
Contains the methods for iterating through a list of keywords. For information about Iterators, see [Iterators](../concepts/iterators).

Example usage:
```javascript
 var keywordSelector = BingAdsApp.keywords();
 var keywordIterator = keywordSelector.get();
 while (keywordIterator.hasNext()) {
   var keyword = keywordIterator.next();
 }
```


## Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|Boolean|Returns a Boolean value that indicates whether this iterator has more elements.
[next](#next)|[Keyword](./Keyword)|Advances the iterator and returns the next keyword.
[totalNumEntities](#totalnumentities)|int|Returns the number of keywords that matched the selector's selection criteria.

## <a name="hasnext"></a>hasNext
Returns a Boolean value that indicates whether this iterator has more elements.

### Returns
|Type|Description|
|-|-
Boolean|Returns **true** if this iterator has more elements; otherwise, **false**.

## <a name="next"></a>next
Advances the iterator and returns the next keyword.

### Returns
|Type|Description|
|-|-
[Keyword](./Keyword.md)|The next keyword in the iterator.

## <a name="totalnumentities"></a>totalNumEntities
Returns the number of keywords that matched the selector's selection criteria.

[!INCLUDE[reads-limit](../includes/reads-limit.md)]

### Returns
|Type|Description|
|-|-
int|The number of keywords that matched the selector's selection criteria.


## See also

- [KeywordSelector.get()](./KeywordSelector.md#get)
- [Keyword](./Keyword.md)
