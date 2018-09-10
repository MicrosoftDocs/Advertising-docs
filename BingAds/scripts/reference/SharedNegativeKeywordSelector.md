---
title: "SharedNegativeKeywordSelector object"
description: "Contains the methods for filtering the list of negative keywords to return."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# SharedNegativeKeywordSelector

Contains the methods for filtering and ordering the list of shared negative keywords. For information about selectors, see [Selectors](../concepts/selectors.md).

Example usage:
```javascript
    var nkws = nkwList.negativeKeywords().get();

    while (nkws.hasNext()) {
        var nkw = nkws.next();
        Logger.log(`${nkw.getText()}`);
    }
```

## Methods
|Method Name|Return Type|Description|
|-|-|-
[get](#get)|[SharedNegativeKeywordIterator](./SharedNegativeKeywordIterator.md)|Gets an iterator that you use to iterate through the list of negative keywords.
[orderBy(string orderBy)](#orderby-string-orderby-)|[SharedNegativeKeywordSelector](./SharedNegativeKeywordSelector.md)|Applies the specified ordering to the selected negative keywords.
[withCondition(string condition)](#withcondition-string-condition-)|[SharedNegativeKeywordSelector](./SharedNegativeKeywordSelector.md)|Applies filter criteria to the negative keywords.
[withLimit(int limit)](#withlimit-int-limit-)|[SharedNegativeKeywordSelector](./SharedNegativeKeywordSelector.md)|Gets the top *n* negative keywords that match the selection criteria.


## <a name="get"></a>get
Gets an [iterator](../concepts/iterators.md) that you use to iterate through the list of negative keywords.

### Returns
|Type|Description|
|-|-
[SharedNegativeKeywordIterator](./SharedNegativeKeywordIterator.md)|An iterator that you use to iterate through the selected negative keywords.


## <a name="orderby-string-orderby-"></a>orderBy(string orderBy)
Applies the specified ordering to the selected negative keywords.

Specify the *orderBy* parameter in the form, "columnName orderDirection" where:

- *columnName* is one of the [supported columns](#supported-keyword-columns).
- *orderDirection* is the order to sort the results in. Set to ASC to order the results in ascending order or DESC to order the results in descending order. The default is ASC.

For example, the following call returns results in ascending order by KeywordText.

`selector = selector.orderBy("KeywordText");`

[!INCLUDE[order-by-limit](../includes/order-by-limit.md)]

### Arguments
|Name|Type|Description|
|-|-|-
orderBy|string|The ordering to apply.

### Returns
|Type|Description|
|-|-
[SharedNegativeKeywordSelector](./SharedNegativeKeywordSelector.md)|Selector with ordering applied.


## <a name="withcondition-string-condition-"></a>withCondition(String condition)
Applies filter criteria to the negative keywords. 

Specify the *condition* parameter in the form, "columnName operator value" where: 

- *columnName* is one of the [supported columns](#supported-keyword-columns).
- *operator* is one of the supported [operators](#operators).

### Operators

The operator that you use depends on the column's type. Operators are case-sensitive. For example, you must use STARTS_WITH instead of starts\_with. 

Operators for columns that contain integers and long values: 

```
<
<=
>
>=
=
!=
```

Operators for columns that contain string values: 

```
=
!=
STARTS_WITH
STARTS_WITH_IGNORE_CASE
CONTAINS
CONTAINS_IGNORE_CASE
DOES_NOT_CONTAIN
DOES_NOT_CONTAIN_IGNORE_CASE
```


<a name="supported-keyword-columns"></a>
### Supported columns

The following are the entity properties you may filter negative keywords by. The column names are case sensitive.

|Column|Type|Example
|-|-|-
KeywordText|string|The negative keyword's text. Include only the keyword's text. Don't include the keyword's match type in the text. For example, if you added an exact match keyword such as [books], use *books* not *[books]*.<br /><br />`withCondition("KeywordText STARTS_WITH 'flowers'")`
KeywordMatchType|enumeration|The keyword's match type. Possible case-sensitive values are: <ul><li>EXACT</li><li>PHRASE</li></ul>`withCondition("KeywordMatchType = EXACT")`<br /><br />Broad match type is not supported.

### Arguments
|Name|Type|Description|
|-|-|-
condition|string|The condition to add to the selector.

### Returns
|Type|Description|
|-|-
[SharedNegativeKeywordSelector](./SharedNegativeKeywordSelector.md)|Selector with the condition applied.


## <a name="withlimit-int-limit-"></a>withLimit(int limit)
Gets the top *n* negative keywords that match the selection criteria.

### Arguments
|Name|Type|Description|
|-|-|-
limit|int|The number of negative keywords to return. The actual number may be less.

### Returns
|Type|Description|
|-|-
[SharedNegativeKeywordSelector](./SharedNegativeKeywordSelector.md)|Selector with limit applied.



## See also

- [NegativeKeywordList.negativeKeywords()](NegativeKeywordList.md)
- [SharedNegativeKeywordIterator](./SharedNegativeKeywordIterator.md)
- [SharedNegativeKeyword](./SharedNegativeKeyword.md)

