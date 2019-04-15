---
title: "Bing Advertising Scripts best practices"
description: "Identifies the best practices you should follow to improve script performance."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Best practices

To improve your scripts' performance, and that of the platform, please review and follow the best practices outlined below.

## Working with selectors

### Use filters

Use a selector's filters instead of filtering the entities yourself. Selectors let you filter by IDs and conditions. For example, you can filter by an entity's performance (return campaign's with an average CPC greater than 10), its status (campaign's that are paused), the name of the entity's parent object, and more.

Benefits of using filters:

- Limits the number of entities the [selector](selectors.md) returns to only those entities that you need.  
  
- Lets the script execute faster (fewer entities to return and process)  
  
- Reduces the chance that you'll bump up against entity read limits (see [Script execution limits](execution-limits.md)).


**Right way**

```javascript
    var adGroups = BingAdsApp.adGroups()
        .withCondition('Status = PAUSED')
        .get();

    while (adGroups.hasNext()) {
        var adGroup = adGroups.next();
        // Do something with paused ad group.
    }
```

**Wrong way**

```javascript
    var adGroups = BingAdsApp.adGroups().get();

    while (adGroups.hasNext()) {
        var adGroup = adGroups.next();
        
        if (adGroup.isPaused() == true) {
            // Do something with paused ad group.
        }
    }
```

### Don't traverse the entity hierarchy

If you want to get an entity's child entities or the entity's parent entity, don't traverse the entity hierarchy to get them. 

To get child entities, use the child entity's collection at the level you want it. 

**Right way**


```javascript
    // Get all ads.
    var ads = BingAdsApp.ads().get();

    while (ads.hasNext()) {
        var ad = ads.next();
        // Do something with ad.
    }
```

Or, if you want ads from a specific campaign:

```javascript
    // Get all ads in the campaign, 'mycampaign'.
    var ads = BingAdsApp.ads()
        .withCondition("CampaignName = 'mycampaign'")
        .get();

    while (ads.hasNext()) {
        var ad = ads.next();
        // Do something with ad.
    }
```

Or, getting a campaign's ads if you have the campaign object:

```javascript
    // Get all ads in the campaign.
    var ads = campaign.ads().get();

    while (ads.hasNext()) {
        var ad = ads.next();
        // Do something with ad.
    }
```

**Wrong way**


```javascript
    var campaigns = BingAdsApp.campaigns().get();

    while (campaigns.hasNext()) {
        var adGroups = campaigns.next().adGroups().get();
        
        while (adGroups.hasNext()) {
            var ads = adGroups.next().ads().get();

            while (ads.hasNext()) {
                var ad = ads.next();
                // Do something with ad.
            }
        }
    }
```

The same applies if you want to get an entity's parent. Instead of traversing the hierarchy to get the parent, use the child entity's parent accessor method.

**Right way**


```javascript
    // Get all ads.
    var ads = BingAdsApp.ads().get();

    while (ads.hasNext()) {
        var ad = ads.next();
        
        // Do something with campaign and adGroup.
        var adGroup = ad.adGroup();
        var campaign = ad.campmaign();
    }
```


**Wrong way**


```javascript
    var campaigns = BingAdsApp.campaigns().get();

    while (campaigns.hasNext()) {
        var campaign = campaigns.next();
        var adGroups = campaign.adGroups().get();
        
        while (adGroups.hasNext()) {
            var adGroup = adGroups.next();
            var ads = adGroup.ads().get();

            while (ads.hasNext()) {
                var ad = ads.next();
                
                if ('<some condition is met>') {
                    // Do something with campaign and adGroup.
                }
            }
        }
    }
```



### Use entity IDs when possible

Using IDs to filter entities provides the best performance.

**This**

```javascript
    var adGroups = BingAdsApp.adGroups()
        .withIds(["123456"])
        .get();

    while (adGroups.hasNext()) {
        var adGroup = adGroups.next();
        
        // Do something with adGroup.
    }
```

**Provides better performance than this**


```javascript
    var adGroups = BingAdsApp.adGroups()
        .withCondition("Name = 'myadgroup'")
        .get();

    while (adGroups.hasNext()) {
        var adGroup = adGroups.next();
        
        // Do something with adGroup.
    }
```



### Avoid tight loops with selectors and an unnecessary number of gets

Avoid loops with get requests that get a single entity. For example, let's say you run a keyword performance report and want to update keywords in the report. Instead of getting a row from the report, getting the keyword, and then updating it, you should create a list of the keyword IDs as you loop through each row in the report. Then, pass the list of IDs to the selector to get all the keywords in a single get request. You can then iterator through the list of keywords and update them.

**Right way**

```javascript
    var report = BingAdsApp.report('<report query goes here>');

    var rows = report.rows();
    var idLists = []; // an array where each element contains an array of IDs.
    var idList = [];  // array of IDs that's limited to maxCount.
    var maxCount = 10000;

    while (rows.hasNext()) {
        var row = rows.next();

        if (idList.length < maxCount) {
            idList.push(row['id']);
        }
        else {
            idLists.push(idList);
            idList = [];
        }
    }

    for (idList of idLists) {
        var keywords = BingAdsApp.keywords()
            .withIds(idList)
            .get();

        while (keywords.hasNext()) {
            var keyword = keywords.next();
            // update the keyword        
        }
    }
```



**Wrong way**

```javascript
    var report = BingAdsApp.report('<report query goes here>');

    var rows = report.rows();

    while (rows.hasNext()) {
        var row = rows.next();

        var keyword = BingAdsApp.keywords()
            .withIds([row['id']])
            .get()
            .next();

        // update the keyword        
    }
```


### Include the forDateRange method only if you plan to call the entity's getStats method

Calling a selector's `forDateRange` method causes the selector to get the entity's performance data. Getting an entity's performance data is expensive, so only get it if you plan to call the entity's `getStats` method and use the data.


### Don't change an entity's property that's used as a condition in the selector

Iterators reduce memory pressure by loading only a single item at a time rather than the entire set of items. Because of this, changing a property that you used as a condition in the selector can cause unexpected behavior.

**Right way**

```javascript
    var adGroups = []; 

    var iterator = BingAdsApp.adGroups()
        .withCondition('Status = ENABLED')
        .get();

    while (iterator.hasNext()) {
        adGroups.push(iterator.next());
    }

    for (var adGroup of adGroups) {
        adGroup.pause();
    }
```


**Wrong way**

```javascript
    var adGroups = BingAdsApp.adGroups()
        .withCondition('Status = ENABLED')
        .get();

    while (adGroups.hasNext()) {
        var adGroup = adGroups.next();
        adGroup.pause();
    }
```



## Batching updates

In order to improve performance, Bing processes build requests in batches. If you call a build request's operation method, it forces Bing to process the queued build requests immediately, negating any performance gains. If you're creating more than one entity, don't execute the operation methods in the same loop that you use to build the entity. This leads to poor performance because only one entity at a time is processed. Instead, create an array of the operations and process them after the build loop.


**Right way**

``` javascript
    // An array to hold the operations, so you 
    // can process them after all the entities are queued.
    var operations = []; 

    // Create all the new entities.
    for (var i = 0; i < keywords.length; i++) {
        var keywordOperation = BingAdsApp.adGroups().get().next()
          .newKeywordBuilder()
          .withText(keywords[i])
          .build();
        operations.push(keywordOperation);
    }

    // Now call the operation method so the build requests
    // get processed in batches.
    for (var i = 0; i < operations.length; i++) {
        var newKeyword = operations[i].getResult();
    }
```

**Wrong way**

``` javascript
    for (var i = 0; i < keywords.length; i++) {
        var keywordOperation = BingAdsApp.adGroups().get().next()  // Get the first ad group
          .newKeywordBuilder()  // Add the keyword to the ad group
          .withText(keywords[i])
          .build();

        // Don't get results in the same loop that creates
        // the entity because Bing then only processes one
        // entity at a time.
        var newKeyword = keywordOperation.getResult();
    }
```

The same is true if you update an entity and then get the same property you updated. Don't do this:

``` javascript
    while (keywords.hasNext()) {
        var keyword = keywords.next();

        // Update and log the keyword that was updated
        keyword.bidding().setCpc(1.2);
        Logger.log(`${keyword.getText()} : ${keyword.bidding().getCpc()}`);
    }
```

