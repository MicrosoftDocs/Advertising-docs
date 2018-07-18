---
title: "Bing Ads Scripts Builders"
description: "Describes how builders work in Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# What are builders?

[!INCLUDE[preview-note](../includes/preview-note.md)]

You use builders to define and create the entity you want to add. Each parent object, such as [Campaign](../reference/Campaign.md), includes methods for getting builder objects that you use to add child entities. For example, to add an ad group to a campaign, you'd call the `Campaign` object's `newAdGroupBuilder` method. 

The builder object includes methods that you use to set the entity's property values. For example, to specify a keyword's CPC, you'd use the `withCpc` method. After setting all the entity's property values, you'd call the `build` method to create the entity. The build process is an asynchronous process where the request is queued with other build requests and processed in a batch. The batched requests will complete before the script terminates.

To determine whether the build requests succeeded, you can look at the logs or you can use the operation object that the `build` method returns. For example, [AdGroupBuilder](../reference/AdGroupBuilder.md) returns [AdGroupOperation](../reference/AdGroupOperation.md). You can call any of the operation object's methods (`isSuccessful`, `getResult`, or `getErrors`) to determine whether Bing successfully created the entity. But there are performance considerations when calling these methods (see [Performance considerations](#performance-considerations)).

The following conceptually shows how to create a keyword using the builder and operation objects. You should probably only use this flow if you're creating a single entity (or maybe a few).


```javascript
    // Retrieve an ad group.
    var adGroup = BingAdsApp.adGroups().get().next();

    // Use the 'with' methods to specify the keyword's property values.
    // The .build() method adds the build request to the build queue.
    var keywordOperation = adGroup.newKeywordBuilder()
        .withCpc(1.2)
        .withText("shirts")
        .withFinalUrl("https://www.contoso.com/shirts")
        .build();

    // Call isSuccessful() to determine if the build succeeded.
    // Calling any of the operation object's method processes the
    // build request immediately. 
    if (keywordOperation.isSuccessful()) {
        // You only need to call getResult if you need to access
        // the new keyword entity.
        var keyword = keywordOperation.getResult();
    } else {
        // Handle the errors.
        for (var error of keywordOperation.getErrors()) {
            Logger.log(`${error}\n`);
        }
    }
```

## Performance considerations

In order to improve performance, Scripts processes build requests in batches. If you call a build request's operation method, it forces Bing to process the build request immediately, negating any performance gains. If you're creating more than one entity, you should not execute the operation methods in the same loop that you use to build the entity. Instead, create an array to hold the operations and then iterate through that array to retrieve the results.  

### Poor Performance
``` javascript
    for (var i = 0; i < keywords.length; i++)
        var keywordOperation = BingAdsApp.adGroups().get().next()
          .newKeywordBuilder()
          .withText(keywords[i])
          .build();

        // Retrieving the result in the same
        // loop that creates the operation
        // leads to poor performance.
        var newKeyword = keywordOperation.getResult();
    }
```

### Good Performance
``` javascript
    // Create an array to hold the operations.
    var operations = [];

    for (var i = 0; i < keywords.length; i++) {
        var keywordOperation = BingAdsApp.adGroups().get().next()
          .newKeywordBuilder()
          .withText(keywords[i])
          .build();
        operations.push(keywordOperation);
    }

    // Process the operations separately. This gives
    // Bing time to process the build requests in
    // batches.
    for (var i = 0; i < operations.length; i++) {
        var newKeyword = operations[i].getResult();
    }
```


The following is the list of builders.

- [AdGroupBuilder](../reference/AdGroupBuilder.md)
- [KeywordBuilder](../reference/KeywordBuilder.md)
- [NegativeKeywordListBuilder](../reference/NegativeKeywordListBuilder.md)

## Next steps

> [!div class="nextstepaction"]
> [Learn about preview mode](../concepts/preview-mode.md)