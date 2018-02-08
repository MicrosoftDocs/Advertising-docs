---
title: "Bing Ads Scripts Builders"
description: "Describes how builders work in the Bing Ads Scripts system."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Builders

Builders are used to create new Bing Ads entities. Using a builder you specify the properties of the entity to be built then invoke the `build()` method to return an operation object.  Using the operation object you can determine the outcome of the operation and take appropriate actions. The following example demonstrates how to create a keyword using a builder and the resulting operation object:

```javascript
// Retrieve an ad group.
var adGroup = BingAdsApp.adGroups().get().next();

var keywordOperation = adGroup.newKeywordBuilder()
    .withCpc(1.2)
    .withText("shirts")
    .withFinalUrl("https://www.contoso.com/shirts")
    .build();

// Optional: examine the outcome. The call to isSuccessful()
// will block until the operation completes.
if (keywordOperation.isSuccessful()) {
  // Get the result.
  var keyword = keywordOperation.getResult();
} else {
  // Handle the errors.
  var errors = keywordOperation.getErrors();
}
```
