---
title: "AdViewSpace object"
description: "Contains the methods used to cast this ad to a specific type."
author: eric-urban
ms.author: eur
ms.service: "bing-ads-scripts"
ms.topic: "article"
---

# AdViewSpace

Contains the methods used to cast this ad to a specific type.


Example usage:
```javascript
    if (ad.isType().expandedTextAd()) {
        var expandedAd = ad.asType().expandedTextAd();
        Logger.log(`Id: ${expandedAd.getId()}
            copy: ${expandedAd.getDescription()}
            title part 1: ${expandedAd.getHeadlinePart1()}
            title part 2: ${expandedAd.getHeadlinePart2()}
            final URL: ${expandedAd.urls().getFinalUrl()}\n\n`);
    }
```


## Methods
|Method Name|Return Type|Description|
|-|-|-
[expandedTextAd](#expandedtextad)|[ExpandedTextAd](ExpandedTextAd.md)|Casts this ad to an expanded text ad.


## <a name="expandedtextad"></a>expandedTextAd
Casts this ad to an expanded text ad.

### Returns
|Type|Description|
|-|-
[ExpandedTextAd](ExpandedTextAd.md)|Contains the methods used to access the expanded text ad's properties.

