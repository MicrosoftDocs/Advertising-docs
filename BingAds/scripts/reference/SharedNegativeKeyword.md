---
title: "SharedNegativeKeyword object"
description: "Contains the methods for managing a shared negative keyword."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# SharedNegativeKeyword

Contains the methods for managing a shared negative keyword. For information about negative keywords, see [Negative Keywords](/bingads/guides/entity-hierarchy-limits#negativekeywords).


## Methods
|Method Name|Return Type|Description|
|-|-|-
[getEntityType](#getentitytype)|string|Gets this entity's type.
[getMatchType](#getmatchtype)|String|Gets this negative keyword's match type.
[getNegativeKeywordList](#getnegativekeywordlist)|[NegativeKeywordList](./NegativeKeywordList.md)|Gets the negative keyword list that this negative keyword belongs to.
[getText](#gettext)|string|Gets this negative keyword's text.
[remove](#remove)|void|Removes this negative keyword from the list.


## <a name="getentitytype"></a>getEntityType
Returns this entity's type.

### Returns
|Type|Description|
|-|-
string|This entity's type, which is *SharedNegativeKeyword*.


## <a name="getmatchtype"></a>getMatchType
Gets this negative keyword's match type. 

### Returns
|Type|Description|
|-|-
string|The negative keyword's match type. Possible values are:<br /><ul><li>PHRASE</li><li>EXACT</li></ul>Broad match type is not supported. For information about these types, see [What are keyword match types, and how do I use them?](https://help.bingads.microsoft.com/apex/index/3/en-us/50822#!)


## <a name="getnegativekeywordlist"></a>getNegativeKeywordList
Gets the negative keyword list that this negative keyword belongs to.

### Returns
|Type|Description|
|-|-
[NegativeKeywordList](./NegativeKeywordList.md)|The negative keyword list that this negative keyword belongs to.


## <a name="gettext"></a>getText
Gets this negative keyword's text. The text includes the keyword's match type syntax, if any. For example:

- The keyword is *"books"* if the match type is **phrase**
- The keyword is *[hardcover books]* if the match type is **exact**

If the keyword does not include match-type syntax, phrase match type is assumed. Broad match type is not supported.

For information about these types, see [What are keyword match types, and how do I use them?](https://help.bingads.microsoft.com/apex/index/3/en-us/50822#!)

### Returns
|Type|Description|
|-|-
string|The negative keyword's text.


## <a name="remove"></a>remove
Removes this negative keyword from the list.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## See also

- [NegativeKeywordList.addNegativeKeyword()](./NegativeKeywordList.md)
- [SharedNegativeKeywordSelector](./SharedNegativeKeywordSelector.md)
- [SharedNegativeKeywordIterator](./SharedNegativeKeywordIterator.md)
