# CampaignIterator
Provides methods to iterate through campaigns.

Example usage:
```javascript
 while (campaignIterator.hasNext()) {
   var campaign = campaignIterator.next();
 }
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|boolean|Returns true if this iterator has more campaign elements <br />
[next](#next)|[Campaign](./Campaign)|Advances to the next campaign in this iterator and returns it.<br />
[totalNumEntities](#totalnumentities)|int|Returns the total number of campaigns indexed by this iterator.
&nbsp;|&nbsp;|&nbsp;

## <a name="hasnext"></a>hasNext
Returns true if this iterator has more campaign elements 

### Returns:
|Type|Description|
|-|-
boolean|true if the iterator has more elements.
&nbsp;|&nbsp;
## <a name="next"></a>next
Advances to the next campaign in this iterator and returns it.

### Returns:
|Type|Description|
|-|-
[Campaign](./Campaign)|The next campaign in the iterator.
&nbsp;|&nbsp;
## <a name="totalnumentities"></a>totalNumEntities
Returns the total number of campaigns indexed by this iterator.
### Returns:
|Type|Description|
|-|-
int|The number of campaigns matched by the selector which generated this iterator.
&nbsp;|&nbsp;
