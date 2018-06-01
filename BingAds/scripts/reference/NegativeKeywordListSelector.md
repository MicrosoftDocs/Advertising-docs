---
title: "NegativeKeywordListSelector object"
description: "Contains the methods for filtering the list of negative keyword lists to return."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# NegativeKeywordListSelector

Contains the methods for filtering the list of negative keyword lists to return. For information about Selectors, see [Selectors](../concepts/selectors.md).

Example usage:
```javascript
var negativeKeywordListSelector = BingAdsApp.negativeKeywordLists()
     .withCondition("MemberCount > 5")
     .orderBy("Name");

 var negativeKeywordListIterator = negativeKeywordListSelector.get();
 while (negativeKeywordListIterator.hasNext()) {
   var negativeKeywordList = negativeKeywordListIterator.next();
 }
```

## Methods
|Method Name|Return Type|Description|
|-|-|-
[get](#get)|[NegativeKeywordListIterator](./NegativeKeywordListIterator.md)|Returns a negative keywords list iterator based on the selector's selection criteria.
[orderBy(string orderBy)](#orderby~string-orderby~)|[NegativeKeywordListSelector](./NegativeKeywordListSelector.md)|Returns a selector with the specified ordering applied.
[withCondition(string condition)](#withcondition~string-condition~)|[NegativeKeywordListSelector](./NegativeKeywordListSelector.md)|Returns a selector that limits the negative keyword lists it returns to those that match the filter criteria.
[withIds(string[] ids)](#withids~string-ids~)|[NegativeKeywordListSelector](./NegativeKeywordListSelector.md)|Returns a selector that returns only negative keyword lists with the specified IDs.
[withLimit(int limit)](#withlimit~int-limit~)|[NegativeKeywordListSelector](./NegativeKeywordListSelector.md)|Returns a selector with the top *n* negative keyword lists that match the selection criteria.

## <a name="get"></a>get
Returns a negative keywords list [iterator](../concepts/iterators.md) based on the selector's selection criteria.

### Returns
|Type|Description|
|-|-
[NegativeKeywordListIterator](./NegativeKeywordListIterator.md)|An iterator that you use to iterate through the negative keywords lists that were selected based on the selector's selection criteria.

## <a name="orderby~string-orderby~"></a>orderBy(string orderBy)
Returns a selector with the specified ordering applied. 

Specify the `orderBy` parameter in the form, "columnName orderDirection" where:

- *columnName* is a supported column, see [Supported Columns](#supported-negative-keyword-list-columns)
- *orderDirection* is the direction to order the results in. Set to ASC to order the results in ascending order or DESC to order the results in descending order. The default is ASC.

For example, the following call returns negative keyword lists in ascending order by MemberCount.

`negativeKeywordListSelector = negativeKeywordListSelector.orderBy("MemberCount");`

[!INCLUDE[order-by-limit](../includes/order-by-limit.md)]

### Arguments
|Name|Type|Description|
|-|-|-
orderBy|string|The ordering to apply.

### Returns
|Type|Description|
|-|-
[NegativeKeywordListSelector](./NegativeKeywordListSelector.md)|Selector with ordering applied.

## <a name="withcondition~string-condition~"></a>withCondition(string condition)
Returns a selector that limits the negative keyword lists it returns to those that match the filter criteria. 

Specify the condition parameter in the form, "columnName operator value" where: 

- *columnName* is one of the [supported columns](#supported-negative-keyword-list-columns).
- *operator* is one of the supported [operators](#operators).

[!INCLUDE[operators](../includes/operators.md)]

<a name="supported-negative-keyword-list-columns"></a>
### Supported Columns

|Column|Type|Example|
|-|-|-|-
<strong>Shared Set Attributes</strong>|
MemberCount|int|`withCondition("MemberCount > 5")`
Name|string|`withCondition("Name = 'negative keyword list'")`
ReferenceCount|int|`withCondition("ReferenceCount > 5")`
SharedSetId|double|`withCondition("SharedSetId > 5")`
Status|string|`withCondition("Status = ACTIVE")`<br /><br />Possible status values are: <ul><li>ACTIVE</li><li>DELETED</li></ul>


### Arguments
|Name|Type|Description|
|-|-|-
condition|string|The condition to add to the selector.

### Returns
|Type|Description|
|-|-
[NegativeKeywordListSelector](./NegativeKeywordListSelector.md)|Selector with the condition applied.

## <a name="withids~string-ids~"></a>withIds(string[] ids)
Returns a selector that contains only negative keyword lists with the specified IDs. 

[!INCLUDE[with-ids-chaining](../includes/with-ids-chaining.md)] For example, the following call selects only negative keywords list 33333.

```javascript
BingAdsApp.negativeKeywordLists()
    .withIds([11111, 22222, 33333])
    .withIds([33333, 44444, 55555])
```

[!INCLUDE[maximum-number-of-ids](../includes/maximum-number-of-ids.md)] 


### Arguments
|Name|Type|Description|
|-|-|-
ids|string[]|An array of negative keyword lists IDs. The maximum number of IDs that you may specify is 1,000. If you specify more than 1,000 IDs, calling the `get` method fails with a runtime error.

### Returns
|Type|Description|
|-|-
[NegativeKeywordListSelector](./NegativeKeywordListSelector.md)|Selector restricted to the given IDs.

## <a name="withlimit~int-limit~"></a>withLimit(int limit)
Returns a selector with the top *n* negative keyword lists that match the selection criteria.

### Arguments
|Name|Type|Description|
|-|-|-
limit|int|The number of negative keyword lists to return.

### Returns
|Type|Description|
|-|-
[NegativeKeywordListSelector](./NegativeKeywordListSelector.md)|Selector with limit applied.



## See also
- [NegativeKeywordListIterator](./NegativeKeywordListIterator.md)
- [NegativeKeywordList](./NegativeKeywordList.md)
