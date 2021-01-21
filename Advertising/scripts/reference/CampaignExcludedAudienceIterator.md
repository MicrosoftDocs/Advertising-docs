---
title: "CampaignExcludedAudienceIterator object"
description: "Contains the methods for iterating through a list of campaign excluded audiences."
author: eric-urban
ms.author: eur
ms.service: "bing-ads-scripts"
ms.topic: "article"
---

# CampaignExcludedAudienceIterator

Contains the methods for iterating through a list of campaign excluded audiences. For information about iterators, see [Iterators](../concepts/iterators.md).

Example usage:
```javascript
    // Gets the iterator that iterates all campaigns
    // in the account.
    var iterator = AdsApp.adGroups().get();

    // Loops through all campaigns in the account.
    while (iterator.hasNext()) {
        var adGroup = iterator.next();

        // Gets the iterator that iterates all campaign excluded audiences
        // in the campaign.
        var audienceIterator = adGroup.targeting().excludedAudiences().get();
    
        // Loops through all campaign excluded audiences in the campaign.
        while (audienceIterator.hasNext()) {
            var audience = iterator.next();
        }
    }
```

## Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|Boolean|Gets a Boolean value that indicates whether the iterator has more elements.
[next](#next)|[CampaignExcludedAudience](./CampaignExcludedAudience.md)|Advances the iterator and returns the next campaign excluded audience.
[totalNumEntities](#totalnumentities)|int|Gets the number of campaign excluded audiences that matched the selector's selection criteria.

## <a name="hasnext"></a>hasNext
Gets a Boolean value that indicates whether the iterator has more elements.

### Returns
|Type|Description|
|-|-
Boolean|Is **true** if the iterator has more elements; otherwise, **false**.

## <a name="next"></a>next
Advances the iterator and returns the next campaign excluded audience.

### Returns
|Type|Description|
|-|-
[CampaignExcludedAudience](./CampaignExcludedAudience.md)|The next campaign excluded audience in the iterator.

## <a name="totalnumentities"></a>totalNumEntities
Gets the number of campaign excluded audiences that matched the selector's selection criteria. 

### Returns
|Type|Description|
|-|-
int|The number of campaign excluded audiences that matched the selector's selection criteria.



## See also
- [CampaignSelector.get()](./CampaignSelector.md#get)
- [Campaign](./Campaign.md)
