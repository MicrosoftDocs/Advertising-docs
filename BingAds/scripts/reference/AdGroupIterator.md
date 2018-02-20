# AdGroupIterator
Provides methods to iterate through ad groups.

Example usage:
```javascript
 while (adGroupIterator.hasNext()) {
   var adGroup = adGroupIterator.next();
 }
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|boolean|Returns <br />
[next](#next)|[AdGroup](./AdGroup)|Advances to the next ad group in this iterator and returns it.<br />
[totalNumEntities](#totalnumentities)|int|Returns the total number of ad groups indexed by this iterator.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="hasnext"></a>hasNext
Returns 

### Returns:
|Type|Description|
|-|-
boolean|true if the iterator has more elements.
&nbsp;|&nbsp;
## <a name="next"></a>next
Advances to the next ad group in this iterator and returns it.

### Returns:
|Type|Description|
|-|-
[AdGroup](./AdGroup)|The next AdGroup in the iterator.
&nbsp;|&nbsp;
## <a name="totalnumentities"></a>totalNumEntities
Returns the total number of ad groups indexed by this iterator.

### Returns:
|Type|Description|
|-|-
int|The number of entities matched by the selector which generated this iterator.
&nbsp;|&nbsp;
