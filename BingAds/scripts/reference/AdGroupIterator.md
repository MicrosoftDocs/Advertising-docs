---
title: "AdGroupIterator object"
description: "Contains the methods for iterating through a list of ad groups."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# AdGroupIterator

Contains the methods for iterating through a list of ad groups. For information about Iterators, see [Iterators](../concepts/iterators.md).

Example usage:
```javascript
var adGroupIterator = BingAdsApp.adGroups().get();

while (adGroupIterator.hasNext()) {
  var adGroup = adGroupIterator.next();
}
```

## Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|Boolean|Returns a Boolean value that indicates whether the iterator has more elements.
[next](#next)|[AdGroup](./AdGroup.md)|Advances the iterator and returns the next ad group.
[totalNumEntities](#totalnumentities)|int|Returns the number of ad groups that matched the selector's selection criteria.

## <a name="hasnext"></a>hasNext
Returns a Boolean value that indicates whether the iterator has more elements.

### Returns
|Type|Description|
|-|-
Boolean|Returns **true** if the iterator has more elements; otherwise, **false**.

## <a name="next"></a>next
Advances the iterator and returns the next ad group.

### Returns
|Type|Description|
|-|-
[AdGroup](./AdGroup.md)|The next ad group in the iterator.

## <a name="totalnumentities"></a>totalNumEntities
Returns the number of ad groups that matched the selector's selection criteria. 

[!INCLUDE[reads-limit](../includes/reads-limit.md)]

### Returns
|Type|Description|
|-|-
int|The number of ad groups that matched the selector's selection criteria.



## See also
- [AdGroupSelector.get()](./AdGroupSelector.md#get)
- [AdGroup](./AdGroup.md)
