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
[totalNumEntities](#totalnumentities)|int|Returns the total number of keywords indexed by this iterator. If the total number of entities returned by this method exceeds the limit for entity reads, the hasNext method will return false and next will throw an error as soon as the latter is reached.<br />

## <a name="hasnext"></a>hasNext
Returns 


## <a name="next"></a>next
Advances to the next keyword in this iterator and returns it.


## <a name="totalnumentities"></a>totalNumEntities
Returns the total number of keywords indexed by this iterator. If the total number of entities returned by this method exceeds the limit for entity reads, the hasNext method will return false and next will throw an error as soon as the latter is reached.


