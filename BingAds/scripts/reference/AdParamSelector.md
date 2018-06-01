---
title: "AdParamSelector object"
description: "Contains the methods for filtering the list of substitution parameters to return."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# AdParamSelector


Contains the methods for filtering the list of substitution parameters. For information about selectors, see [Selectors](../concepts/selectors.md).


## Methods

|Method Name|Return Type|Description|
|-|-|-
[get](#get)|[AdParamIterator](AdParamIterator.md)|Returns an iterator based on the selector's selection criteria.



## <a name="get"></a>get
Returns an [iterator](../concepts/iterators.md) based on the selector's selection criteria.

### Returns
|Type|Description|
|-|-
[AdParamIterator](AdParamIterator.md)|Iterator that you use to iterate through the substitution parameters that were selected based on the selector's selection criteria.


## See also

- [Keyword.adParams()](Keyword.md#adparams)