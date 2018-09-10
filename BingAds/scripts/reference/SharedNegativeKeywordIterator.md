---
title: "SharedNegativeKeywordIterator object"
description: "Contains the methods for iterating through a list of shared negative keywords."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# SharedNegativeKeywordIterator

Contains the methods for iterating through a list of shared negative keywords. For information about iterators, see [Iterators](../concepts/iterators.md).

Example usage:
```javascript
    // Gets the iterator that iterates all negative keywords
    // in a negative keyword list.
    var nkws = nkwList.negativeKeywords().get();

    // Loops through all the negative keywords.
    while (nkws.hasNext()) {
        var nkw = nkws.next();
        Logger.log(`${nkw.getText()}`);
    }
```


## Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|Boolean|Gets a Boolean value that indicates whether this iterator has more elements.
[next](#next)|[SharedNegativeKeyword](./SharedNegativeKeyword.md)|Advances the iterator and returns the next negative keyword.
[totalNumEntities](#totalnumentities)|int|Gets the number of negative keywords that matched the selector's selection criteria.


## <a name="hasnext"></a>hasNext
Gets a Boolean value that indicates whether this iterator has more elements.

### Returns
|Type|Description|
|-|-
Boolean|Is **true** if this iterator has more elements; otherwise, **false**.


## <a name="next"></a>next
Advances the iterator and returns the next negative keyword.

### Returns
|Type|Description|
|-|-
[SharedNegativeKeyword](./SharedNegativeKeyword.md)|The next negative keyword in the iterator.


## <a name="totalnumentities"></a>totalNumEntities
Gets the number of negative keywords that matched the selector's selection criteria.

<!--
[!INCLUDE[reads-limit](../includes/reads-limit.md)]
-->

### Returns
|Type|Description|
|-|-
int|The number of negative keywords that matched the selector's selection criteria.


## See also

- [SharedNegativeKeywordSelector.get()](./SharedNegativeKeywordSelector.md#get)
- [SharedNegativeKeyword](./SharedNegativeKeyword.md)
- [NegativeKeywordList](./NegativeKeywordList.md)

