# CampaignIterator
Provides methods to iterate through campaigns.

|Method|Return Type|Description|
|-|-|-
hasNext|boolean|Returns true if this iterator has more campaign elements <br />
next|[Campaign](./Campaign)|Advances to the next campaign in this iterator and returns it.<br />
totalNumEntities|int|Returns the total number of campaigns indexed by this iterator. If the total number of  entities returned by this method exceeds the limit for entity reads, the hasNext method will return  false and next will throw an error as soon as the latter is reached.<br />
