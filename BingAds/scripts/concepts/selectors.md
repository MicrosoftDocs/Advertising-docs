---
title: "Bing Ads Scripts Selectors"
description: "Describes how selectors work in Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# What are selectors?

[!INCLUDE[preview-note](../includes/preview-note.md)]

Selectors let you apply filter and sort criteria when retrieving Bing Ads entities such as keywords and campaigns.  Selectors provide functionality roughly equivalent to SQL `WHERE` and `ORDER BY` clauses. The selector class supports the following methods:

- **withCondition()** &mdash; Use to specify conditions that entities must meet to be selected. If multiple conditions are used, the selector returns only entities that match all of the specified conditions. This is equivalent to a SQL `WHERE` clause.  
  
  Example: `withCondition('Name STARTS_WITH "Contoso"')`  
  
- **withIds()** &mdash; Use to specify the IDs of entities to select. This is equivalent to a SQL `IN` clause.  
  
  Example: `withIds(["1","2","3","4"])`  

- **forDateRange()** &mdash; Use to return entities matching a specified date range. If a condition specifies a metric column, you must include `forDateRange` in the selector's chain.  
  
  Example: `forDateRange("LAST_14_DAYS")`  

- **orderBy()** &mdash; Use to order the entities that the selector returns by a specified field. This is equivalent to a SQL `ORDER BY` clause.  
  
  Example: `orderBy("Clicks DESC")`  

- **withLimit()** &mdash; Use to return at most the specified number of entities. This is equivalent to a SQL `TOP` clause.  
  
  Example: `withLimit(50)`  

Because each method returns the selector with the filter criteria applied, you may chain together (using dot notation) multiple conditions to refine the filter criteria. For example:

```javascript
var campaignSelector = BingAdsApp.campaigns()
    .withCondition("Clicks > 10")
    .withCondition("Impressions > 100")
    .orderBy("Impressions DESC")
    .forDateRange("YESTERDAY");
```

The following are the possible selectors.

- [AdGroupSelector](../reference/AdGroupSelector.md)
- [CampaignSelector](../reference/CampaignSelector.md)
- [KeywordSelector](../reference/KeywordSelector.md)
- [NegativeKeywordListSelector](../reference/NegativeKeywordListSelector.md)

To improve script performance, use specific filter conditions to ensure that you retrieve only the entities you want. After getting the selector, call the `get` method to retrieve an iterator that you use to iterate through the list of entities.

```javascript
var campaigns = campaignSelector.get();
```

Or 

```javascript
var campaigns = BingAdsApp.campaigns()
    .withCondition("Clicks > 10")
    .withCondition("Impressions > 100")
    .orderBy("Impressions DESC")
    .forDateRange("YESTERDAY");
    .get();
```



### Next steps

> [!div class="nextstepaction"]
> [Learn about iterators](./iterators.md)
