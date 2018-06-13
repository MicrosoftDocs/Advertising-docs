---
title: "Bing Ads Scripts single account access"
description: "Provides an overview of how you use BingAdsApp to access a single account's entities."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Single account access

If you want to access a single user account, everything starts with the [BingAdsApp](../reference/BingAdsApp.md) object.  

## How do I access the entities in my account?

You use BingAdsApp to access all entities in the account. The object contains a selector method for each entity that returns all of that entity's objects. For example, to get all the ad groups in the account, you call the `adGroups()` method.

```javascript
    var selector = BingAdsApp.adGroups();
```

### But what if I want a specific entity or subset of entities?

The selector provides different ways to filter the list of entities. You can use the selector’s `withIds()` method to get specific entities by IDs or you can use `withCondition()` to specify the selection criteria for selecting the entities. The selectors for all entity types, except for negative keyword lists, provide the ability to filter the list of entities you want returned.

Use dot notation to string multiple filters together. If you specify multiple filters, they're treated as an AND operation where all filters must return true. 

To get all ad groups in a campaign, use the `withCondition()` method to specify the campaign's name.

```javascript
    var campaignName = 'My Campaign';
    var selector = BingAdsApp.adGroups()
        .withCondition('CampaignName = "' + campaignName + '"');
```

For a list of conditions and operators that you can use to filter the entities list, see the entity's `withCondition()` method. For example, for a list of ad group conditions, see the ad group selector's [withCondition](../reference/AdGroupSelector.md#withcondition~string-condition~) method.

To get an ad group by ID, use the `withIds()` method to specify the ad group to get.

```javascript
    var ids = ["123456789"];
    var selector = BingAdsApp.adGroups()
        .withIds(ids);
```

Or, you can get the ad group by name.

```javascript
    var campaignName = 'My Campaign';
    var adGroupName = 'My AdGroup';
    var selector = BingAdsApp.adGroups()
        .withCondition('CampaignName = "' + campaignName + '"')
        .withCondition('Name = "' + adGroupName + '"');
```

For more information about selectors, see [What are selectors?](../concepts/selectors.md).


### How do I use the selector to iterate through the filtered lits of entities?

You don't. The selector just defines the entities you want to get. To actually get the entities, you use an iterator. To get the iterator, you call the selector's `get()` method.

```javascript
    var ids = ["123456789"];
    var iterator = BingAdsApp.adGroups()
        .withIds(ids)
        .get();
```

Use a simple **while** loop to iterate over the list of entities.

```javascript
    while (iterator.hasNext()) {
        var adGroup = iterator.next();
        
        // Do something with the entity
    }
```

For more information about iterators, see [What are iterators?](../concepts/iterators.md).


### How do I get performance data for an entity?

Most entities let you request performance data, if available. But first you need to specify a date range for the performance data you want when you get the selector. You can specify a date range using a predefined literal, such as YESTERDAY or LAST_MONTH, or using dates. For more information, see [withDateRange(string dateRange)](../reference/AdGroupSelector.md#fordaterange~string-daterange~) and [forDateRange(Object dateFrom, Object dateTo)](../reference/AdGroupSelector.md#fordaterange~object-datefrom_-object-dateto~).

```javascript
    var campaignName = 'My Campaign';
    var adGroupName = 'My AdGroup';
    var iterator = BingAdsApp.adGroups()
        .withDateRange('LAST_30_DAYS')
        .withCondition('CampaignName = "' + campaignName + '"')
        .withCondition('Name = "' + adGroupName + '"')
        .get();

    while (iterator.hasNext()) {
        var adGroup = iterator.next();
        
        var stats = adGroup.getStats();
        Logger.log(`Ad group: ${adGroup.getName()} (${adGroup.getId()})`);
        Logger.log(`Clicks: ${stats.getClicks()}, Impressions: ${stats.getImpressions()}\n`);
    }
```


You also need to specify a date range if you specify a performance data column in a selector's `withCondition()` method. For example, if you want only ad groups that have a CTR of greater than .12 percent, you need to specify a date range.

```javascript
    var startDate = {year: 2018, month: 6, day: 3};
    var endDate = {year: 2018, month: 6, day: 13};

    var iterator = BingAdsApp.adGroups()
        .withDateRange(startDate, endDate)
        .withCondition("Ctr > 0.12")
        .get();
```


## How do I add an entity?

Adding entities is a multi-step process where you first use a builder object to define the entity and then use an operation object to actually add the entity. To get a builder object, you call the **new\*** method on the parent object that you're adding children to. For example, to add ad groups to a campaign, you call the campaign's `newAdGroupBuilder()` method.

The builder object contains methods for setting all of the object's properties that you're allowed to specify. It also includes a `build()` method that you use to get the operation object. The following shows how to build an ad group and get its operation object.

```javascript
        var adGroupName = "My ad group";
        var endDate = {year: 2018, month: 6, day: 13};
        var customParameters = {key1: 'value1', key2: 'value2', key3: 'value3'};

        var adGroupOperation = campaign.newAdGroupBuilder()
            .withName(adGroupName)
            .withStatus('ENABLED')
            .withLanguage('English')
            .withBiddingStrategy('MANUAL_CPC')
            .withCpc(1.2)
            .withCustomParameters(customParameters)
            .withEndDate(endDate)
            .build();
```

Now that you have the operation object you can call any of its methods to add the object. The following shows the typical calling pattern.

```javascript
    if (adGroupOperation.isSuccessful()) {
        var adGroup = adGroupOperation.getResult();

        Logger.log("Added ad group, " + adGroup.getName());
    }
    else {
        for (var error of adGroupOperation.getErrors()) {
            Logger.log(`${error}\n`);
        }
    }
```

## How do I update an entity?

After using a builder and operation object to add an entity, you use the entity's method to update its properties. The following example updates the ad group's CPC bid amount.

```javascript
    var ids = ["123456789"];
    var adGroups = BingAdsApp.adGroups()
        .withIds(ids)
        .get();

    if (adGroups.hasNext()) {
        var adGroup = adGroups.next();
        adGroup.bidding().setCpc(1.5);
    }
```

### But how do I know that the update worked?

If you try to update a property with an invalid value, Scripts writes an error to the Change log but it doesn't throw an exception, so your script continues executing. The only way to know whether a property update succeeded is to get the entity again and check its property value.

```javascript
```

## Writing to the log file

Scripts does provide a log file for you to write tracing and debug information to. For information, see [Change logs and text logs](../concepts/change-and-text-logs.md).


## Next steps

> [!div class="nextstepaction"]
> [Get Started](../get-started.md)
