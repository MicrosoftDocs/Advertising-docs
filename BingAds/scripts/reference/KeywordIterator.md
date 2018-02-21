# KeywordIterator
Provides methods to iterate through keywords.

Example usage:
```javascript
 while (keywordIterator.hasNext()) {
   var keyword = keywordIterator.next();
 }
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|boolean|Returns <br />
[next](#next)|[Keyword](./Keyword)|Advances to the next keyword in this iterator and returns it.<br />
[totalNumEntities](#totalnumentities)|int|Returns the total number of keywords indexed by this iterator.
&nbsp;|&nbsp;|&nbsp;

## <a name="hasnext"></a>hasNext
Returns 

### Returns:
|Type|Description|
|-|-
boolean|true if the iterator has more elements.
&nbsp;|&nbsp;
## <a name="next"></a>next
Advances to the next keyword in this iterator and returns it.

### Returns:
|Type|Description|
|-|-
[Keyword](./Keyword)|The next keyword in the iterator.
&nbsp;|&nbsp;
## <a name="totalnumentities"></a>totalNumEntities
Returns the total number of keywords indexed by this iterator.

The returned number disregards limits, and the iterator is not guaranteed to have this many elements.

hasNext will start to return false and next will start to throw exceptions when the limit for entity reads has been reached, even if the selector matched more entities.

### Returns:
|Type|Description|
|-|-
int|The number of keywords matched by the selector which generated this iterator.
&nbsp;|&nbsp;
