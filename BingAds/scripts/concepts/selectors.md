---
title: "Bing Ads Scripts Selectors"
description: "Describes how selectors work in the Bing Ads Scripts system."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Selectors

Selectors allow you to specify filter and sort criteria when retrieving Bing Ads entities.  Selectors provide functionality roughly equivalent to SQL `WHERE` and `ORDER BY` clauses. The following methods are provided on all selector classes:

- <code>withCondition()</code> – analogous to a SQL `WHERE` clause; used to specify conditions which must be met for entities to be retrieved.<br />Example:<br />
    &nbsp;&nbsp;&nbsp;`withCondition('Name STARTS_WITH "Contoso"')`<br /><br />
- <code>withIds()</code> – analogous to a SQL `IN` clause; used to specify an array of IDs to retrieve specific entities.<br />&nbsp;Example:<br />
    &nbsp;&nbsp;&nbsp;`withIds([1,2,3,4])`<br /><br />
- <code>forDateRange()</code> – returns elements matching a specified date range.<br />&nbsp;Example:<br />
    &nbsp;&nbsp;&nbsp;`forDateRange("LAST_14_DAYS")`<br /><br />
- <code>orderBy()</code> – orders the returned elements by a specified field.<br />&nbsp;Example:<br />
    &nbsp;&nbsp;&nbsp;`orderBy("Clicks DESC")`<br /><br />
- <code>withLimit()</code> – analogous to a SQL `TOP` clause; returns only the specified number of elements.<br />&nbsp;Example:<br />
    &nbsp;&nbsp;&nbsp;`withLimit(50)`<br /><br />

Because each method returns the selector with the new filter criteria applied, multiple conditions can be chained together to create more specific filters. For example:

```javascript
var campaignSelector = BingAdsApp.campaigns()
    .withCondition("Clicks > 10")
    .withCondition("Impressions > 100")
    .orderBy("Impressions DESC")
    .forDateRange("YESTERDAY");
```

Filters should be as specific as possible to retrieve only the entities you want; this results in improved script performance. Once the selector is instantiated and has had filters applied, it can be used to create an iterator by invoking the selector's `get()` method.

Proceed to the next section to learn how to use [Builders](./builders) to create Bing Ads entities.
> [!div class="nextstepaction"]
> [Builders](./builders)
