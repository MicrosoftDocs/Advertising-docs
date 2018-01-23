# CampaignIterator
Provides methods to iterate through campaigns.

|Method|Return Type|Description|
|-|-|-
[hasNext]('#hasNext')|boolean|Returns true if this iterator has more campaign elements <br />
[next]('#next')|[Campaign](./Campaign)|Advances to the next campaign in this iterator and returns it.<br />
[totalNumEntities]('#totalNumEntities')|int|Returns the total number of campaigns indexed by this iterator. If the total number of  entities returned by this method exceeds the limit for entity reads, the hasNext method will return  false and next will throw an error as soon as the latter is reached.<br />

<a name="hasNext"></a>
## hasNext
Returns true if this iterator has more campaign elements 


<a name="next"></a>
## next
Advances to the next campaign in this iterator and returns it.


<a name="totalNumEntities"></a>
## totalNumEntities
Returns the total number of campaigns indexed by this iterator. If the total number of  entities returned by this method exceeds the limit for entity reads, the hasNext method will return  false and next will throw an error as soon as the latter is reached.


