# BingAdsAccountIterator
Provides methods to iterate through a list of accounts. For information about Iterators, see [Iterators](../concepts/iterators).
See also:
- [BingAdsAccountSelector.get()](./BingAdsAccountSelector#get)
- [BingAdsAccount](./BingAdsAccount)

# Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|Boolean|Returns a Boolean value that indicates if this iterator has more elements.
[next](#next)|[BingAdsAccount](./BingAdsAccount)|Advances the iterator and returns the next account.
[totalNumEntities](#totalnumentities)|int|Returns the number of accounts matched by the selector which generated this iterator.

## <a name="hasnext"></a>hasNext
Returns a Boolean value that indicates if this iterator has more elements.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this iterator has more elements.

## <a name="next"></a>next
Advances the iterator and returns the next account.

### Returns:
|Type|Description|
|-|-
[BingAdsAccount](./BingAdsAccount)|Next account in the iterator.

## <a name="totalnumentities"></a>totalNumEntities
Returns the number of accounts matched by the selector which generated this iterator. [!INCLUDE[reads-limit](../includes/reads-limit.md)]

### Returns:
|Type|Description|
|-|-
int|Number of accounts matched by the selector which generated this iterator.

