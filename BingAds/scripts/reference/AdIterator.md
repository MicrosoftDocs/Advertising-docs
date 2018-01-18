# AdIterator
Provides methods to iterate through ads.

|Method|Return Type|Description|
|-|-|-
hasNext|boolean|Returns <br />
next|[Ad](./Ad)|Advances to the next ad in this iterator and returns it.<br />
totalNumEntities|int|Returns the total number of ads indexed by this iterator. Note that if the total number of entities returned by this method exceeds the limit for entity reads, the hasNext method will return false and next will throw an error as soon as the latter is reached.<br />
