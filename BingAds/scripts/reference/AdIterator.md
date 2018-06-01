# AdIterator
Provides methods to iterate through a list of ads. For information about Iterators, see [Iterators](../concepts/iterators).

Example usage:
```javascript
 while (adIterator.hasNext()) {
   var ad = adIterator.next();
 }
```

See also:
- [AdSelector.get()](./AdSelector#get)
- [Ad](./Ad)

# Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|boolean|Returns a Boolean value that determines if this iterator has more elements.
[next](#next)|[Ad](./Ad)|Advances the iterator and returns the next ad.
[totalNumEntities](#totalnumentities)|int|Returns the number of ads matched by the selector which generated this iterator.

## <a name="hasnext"></a>hasNext
Returns a Boolean value that determines if this iterator has more elements.

### Returns:
|Type|Description|
|-|-
boolean|Boolean value that determines if this iterator has more elements.

## <a name="next"></a>next
Advances the iterator and returns the next ad.

### Returns:
|Type|Description|
|-|-
[Ad](./Ad)|Next ad in the iterator.

## <a name="totalnumentities"></a>totalNumEntities
Returns the number of ads matched by the selector which generated this iterator. [!INCLUDE[reads-limit](../includes/reads-limit.md)]

### Returns:
|Type|Description|
|-|-
int|Number of ads matched by the selector which generated this iterator.

