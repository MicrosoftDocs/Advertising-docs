# AdIterator
Provides methods to iterate through ads.

Example usage:
```javascript
 while (adIterator.hasNext()) {
   var ad = adIterator.next();
 }
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|boolean|Returns <br />
[next](#next)|[Ad](./Ad)|Advances to the next ad in this iterator and returns it.<br />
[totalNumEntities](#totalnumentities)|int|Returns the total number of ads indexed by this iterator.
&nbsp;|&nbsp;|&nbsp;

## <a name="hasnext"></a>hasNext
Returns 

### Returns:
|Type|Description|
|-|-
boolean|true if the iterator has more elements.
&nbsp;|&nbsp;
## <a name="next"></a>next
Advances to the next ad in this iterator and returns it.

### Returns:
|Type|Description|
|-|-
[Ad](./Ad)|The next ad in the iterator.
&nbsp;|&nbsp;
## <a name="totalnumentities"></a>totalNumEntities
Returns the total number of ads indexed by this iterator.

The returned number disregards limits, and the iterator is not guaranteed to have this many elements.

hasNext will start to return false and next will start to throw exceptions when the limit for entity reads has been reached, even if the selector matched more entities.

### Returns:
|Type|Description|
|-|-
int|The number of ads matched by the selector which generated this iterator.
&nbsp;|&nbsp;