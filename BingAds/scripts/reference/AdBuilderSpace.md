---
title: "AdBuilderSpace object"
description: "The AdBuilderSpace object contains the method used to create an ad in an ad group."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# AdBuilderSpace

Contains the method used to define an ad that you want to create.


Example usage:
```javascript
 var adOperation = adGroup.newAd().expandedTextAdBuilder()
    .withHeadlinePart1("First headline of ad")
    .withHeadlinePart2("Second headline of ad")
    .withDescription("Ad description")
    .withPath1("path1")
    .withPath2("path2")
    .withFinalUrl("http://www.example.com")
    .build();
 var ad = adOperation.getResult();
```

## Methods
|Method Name|Return Type|Description|
|-|-|-
[expandedTextAdBuilder](#expandedtextadbuilder)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|Returns a builder object that you use to define a text ad.

## <a name="expandedtextadbuilder"></a>expandedTextAdBuilder
Returns a [builder](../concepts/builders.md) object that you use to define a text ad.

### Return type
|Type|Description|
|-|-
[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|A new expanded text ad builder associated with the ad group.

