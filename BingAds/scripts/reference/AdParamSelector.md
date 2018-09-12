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


Contains the methods for filtering a list of substitution parameters. For information about selectors, see [Selectors](../concepts/selectors.md).


## Methods

|Method Name|Return Type|Description|
|-|-|-
[get](#get)|[AdParamIterator](AdParamIterator.md)|Gets an iterator that you use to iterate through the list of substitution parameters.



## <a name="get"></a>get
Gets an [iterator](../concepts/iterators.md) that you use to iterate through the list of substitution parameters.

### Returns
|Type|Description|
|-|-
[AdParamIterator](AdParamIterator.md)|An iterator that you use to iterate through the substitution parameters.


## See also

- [Keyword.adParams()](Keyword.md#adparams)