---
title: "Bing Ads Scripts Iterators"
description: "Describes how iterators work in Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# What are iterators?

[!INCLUDE[preview-note](../includes/preview-note.md)]

Iterators enumerate items that a [selector](selectors.md) returns. Iterators are similar to arrays except you can't use an index to directly access an item. Iterators also help reduce memory pressure by loading only a single item at a time rather than the entire set of items. The following are the iterator methods.

- **boolean hasNext()** &mdash; Returns true if the current position is not the last item in the list
- **Object next()** &mdash; Advances the current position and returns the object at the new position
- **totalNumEntities()** &mdash; Returns the number of items available in the iterator.

The following code shows how to use an iterator to iterate over all campaigns in your account.

```javascript
var campaignIterator = BingAdsApp.campaigns().get();

while (campaignIterator.hasNext()) {
  var campaign = campaignIterator.next();
  Logger.log(campaign.getName() +
      "; active? " + campaign.isEnabled() +
      "; budget=" + campaign.getBudget().getAmount());
}
```

> [!NOTE]
> The iterators don't support the **for-of** loop construct (for example, **for (var campaign of BingAdsApp.campaigns().get())**).

The following is the list of iterators.

- [AdGroupIterator](../reference/AdGroupIterator.md)
- [CampaignIterator](../reference/CampaignIterator.md)
- [KeywordIterator](../reference/KeywordIterator.md)
- [NegativeKeywordListIterator](../reference/NegativeKeywordListIterator.md)

### Next steps

> [!div class="nextstepaction"]
> [Learn about builders](./builders.md)