---
title: "Bing Ads Scripts Iterators"
description: "Describes how iterators work in the Bing Ads Scripts system."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Iterators

Iterators are used to visit each item in a list of items such as a list of Bing Ads entities. Iterators are similar to arrays with a few differences; the length or item count may not be known so it is not possible to directly access an item by index. Additionally, iterators help to reduce memory pressure by loading only a single item at a time rather than the entire set of items.  Methods defined on iterators are as follows:

- <code>boolean hasNext()</code> – returns true if the current position is not the last element in the list.
- <code>Object next()</code> – advances the current position and returns the object at the new position in the list.
- <code>totalNumEntities()</code> – returns the number of items in the iterator.

While it is not possible to access an item directly by index, the number of entities that would be returned can be determined by using the `totalNumEntities()` method.  This can be helpful when partitioning data for processing.  For example:

```javascript
var keywords = campaign.keywords()
    .withCondition("Ctr > 0.01")
    .forDateRange("YESTERDAY")
    .get();
// Did we retrieve too many?
if (keywords.totalNumEntities() > 50000) {
    // Adjust the condition to retrieve fewer keywords.
    keywords = campaign.keywords()
      .withCondition("Ctr > 0.015")
      .forDateRange("YESTERDAY")
      .get();
}
```

Proceed to the next section to understand how to use [Selectors](./selectors.md) to obtain iterators.
> [!div class="nextstepaction"]
> [Selectors](./selectors.md)