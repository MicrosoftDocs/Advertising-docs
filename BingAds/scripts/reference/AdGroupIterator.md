# AdGroupIterator
Provides methods to iterate through a list of ad groups.

Example usage:
```javascript
 while (adGroupIterator.hasNext()) {
   var adGroup = adGroupIterator.next();
 }
```

See also:
- [AdGroupSelector.get()](./AdGroupSelector#get)
- [AdGroup](./AdGroup)

# Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|boolean|Returns true if the iterator has more ad group elements.
[next](#next)|[AdGroup](./AdGroup)|Advances to the next ad group in this iterator and returns it.<br />
[totalNumEntities](#totalnumentities)|int|Returns the total number of ad groups indexed by this iterator.
&nbsp;|&nbsp;|&nbsp;

## <a name="hasnext"></a>hasNext
Returns true if the iterator has more ad group elements.
### Returns:
|Type|Description|
|-|-
boolean|True if the iterator has more elements.
&nbsp;|&nbsp;
## <a name="next"></a>next
Advances to the next ad group in this iterator and returns it.

### Returns:
|Type|Description|
|-|-
[AdGroup](./AdGroup)|The next ad group in the iterator.
&nbsp;|&nbsp;
## <a name="totalnumentities"></a>totalNumEntities
Returns the total number of ad groups indexed by this iterator.

The returned number disregards limits, and the iterator is not guaranteed to have this many elements.

hasNext will start to return false and next will start to throw exceptions when the limit for entity reads has been reached, even if the selector matched more entities.

### Returns:
|Type|Description|
|-|-
int|The number of ad groups matched by the selector which generated this iterator.
&nbsp;|&nbsp;
