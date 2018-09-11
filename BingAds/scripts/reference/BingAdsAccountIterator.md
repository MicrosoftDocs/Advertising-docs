---
title: "BingAdsAccountIterator object"
description: "Contains the methods for iterating through a list of managed accounts."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# BingAdsAccountIterator

Contains the methods for iterating through a list of managed accounts. For information about iterators, see [Iterators](../concepts/iterators.md).

Example usage:
```javascript
    // Gets the iterator that iterates all managed
    // accounts you have access to.
    var accounts = AccountsApp.accounts().get();

    // Loops through the list of accounts.
    while (accounts.hasNext()) {
        var account = accounts.next();
        Logger.log(`${account.getName()} (${account.getCustomerId()})`);
    }
```


## Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|Boolean|Gets a Boolean value that indicates whether this iterator has more elements.
[next](#next)|[BingAdsAccount](./BingAdsAccount.md)|Advances the iterator and returns the next managed account.
[totalNumEntities](#totalnumentities)|int|Gets the number of managed accounts that matched the selector's selection criteria.

## <a name="hasnext"></a>hasNext
Gets a Boolean value that indicates whether this iterator has more elements.

### Returns
|Type|Description|
|-|-
Boolean|Is **true** if this iterator has more elements; otherwise, **false**.

## <a name="next"></a>next
Advances the iterator and returns the next managed account.

### Returns
|Type|Description|
|-|-
[BingAdsAccount](./BingAdsAccount.md)|The next account in the iterator.

## <a name="totalnumentities"></a>totalNumEntities
Gets the number of managed accounts that matched the selector's selection criteria.

<!--
[!INCLUDE[reads-limit](../includes/reads-limit.md)]
-->

### Returns
|Type|Description|
|-|-
int|The number of managed accounts that matched the selector's selection criteria.


## See also

- [BingAdsAccountSelector.get()](./BingAdsAccountSelector.md#get)
- [BingAdsAccount](./BingAdsAccount.md)
- [MccApp](./AccountsApp.md)
