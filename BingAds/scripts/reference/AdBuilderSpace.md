---
title: "AdBuilderSpace object"
description: "Describes the methods for getting ad builders."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# AdBuilderSpace

Contains the methods used to get ad builders.



Example usage:
```javascript
    var builder = adGroup.newAd().expandedTextAdBuilder();
```


## Methods
|Method Name|Return Type|Description|
|-|-|-
[expandedTextAdBuilder](#expandedTextAdBuilder)|[ExpandedTextAdBuilder](ExpandedTextAdBuilder.md)|Gets a builder used to add an expanded text ad to the ad group.


## <a name="expandedTextAdBuilder"></a>expandedTextAdBuilder
Gets a [builder](../concepts/builders.md) that you use to add an expaned text ad to this ad group.

### Returns

|Type|Description|
|-|-
[ExpandedTextAdBuilder](ExpandedTextAdBuilder.md)|The builder that you use to add expanded text ads to this ad group.
