---
title: "NegativeKeywordListIterator object"
description: "Contains the methods for iterating through a list of negative keyword lists."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# NegativeKeywordListIterator

Contains the methods for iterating through a list of negative keyword lists. For information about Iterators, see [Iterators](../concepts/iterators.md).

Example usage:
```javascript
var negativeKeywordListSelector = BingAdsApp.negativeKeywordLists();
var negativeKeywordListIterator = negativeKeywordListSelector.get();
while (negativeKeywordListIterator.hasNext()) {
  var negativeKeywordList = negativeKeywordListIterator.next();
}
```

## Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|Boolean|Returns a Boolean value that indicates whether this iterator has more elements.
[next](#next)|[AdGroup](./AdGroup.md)|Advances the iterator and returns the next negative keyword list.
[totalNumEntities](#totalnumentities)|int|Returns the number of negative keywords lists that matched selector's selection criteria.

## <a name="hasnext"></a>hasNext
Returns a Boolean value that indicates whether this iterator has more elements.

### Returns
|Type|Description|
|-|-
Boolean|Returns **true** if this iterator has more elements; otherwise, **false**.

## <a name="next"></a>next
Advances the iterator and returns the next negative keyword list.

### Returns
|Type|Description|
|-|-
[NegativeKeywordList](NegativeKeywordList.md)|The next negative keywords list in the iterator.

## <a name="totalnumentities"></a>totalNumEntities
Returns the number of negative keywords lists that matched the selector's selection criteria. 

[!INCLUDE[reads-limit](../includes/reads-limit.md)]

### Returns
|Type|Description|
|-|-
int|The number of negative keywords lists that matched the selector's selection criteria.


## See also
- [NegativeKeywordListSelector.get()](./NegativeKeywordListSelector.md#get)
- [NegativeKeywordList](./NegativeKeywordList.md)