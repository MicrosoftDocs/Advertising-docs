---
title: "ExpandedTextAdBuilder object"
description: "Contains the methods for creating an expanded text ad."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# ExpandedTextAdBuilder

Contains the methods for defining and creating an expanded text ad. For information about builders, see [Builders](../concepts/builders.md).

Example usage:
```javascript
    var operation = adGroup.newAd().expandedTextAdBuilder()
        .withHeadlinePart1('FIRST PART OF TITLE GOES HERE')
        .withHeadlinePart2('SECOND PART OF TITLE GOES HERE')
        .withDescription('AD TEXT GOES HERE')
        .withFinalUrl('URL GOES HERE')
        .build();

    // See the Builders topic for performance considerations
    // when using the operation object's methods.
    if (!operation.isSuccessful()) {
        for (var error of operation.getErrors()) {
            Logger.log(`${error}\n`);
        }
    }
```

## Methods
|Method Name|Return Type|Description|
|-|-|-
[build](#build)|[AdOperation](./AdOperation.md)|Creates the ad and returns an operation object that you can use to check whether Bing successfully added the ad.
[withDescription(string description)](#withdescription-string-description-)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder.md)|Sets the ad's text.
[withFinalUrl(string finalUrl)](#withfinalurl-string-finalurl-)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder.md)|Sets the ad's landing page URL.
[withHeadlinePart1(string headlinePart1)](#withheadlinepart1-string-headlinepart1-)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder.md)|Sets the first part of the ad's title.
[withHeadlinePart2(string headlinePart2)](#withheadlinepart2-string-headlinepart2-)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder.md)|Sets the second part of the ad's title.


## <a name="build"></a>build
Creates the ad and returns an operation object that you can use to check whether Bing successfully added the ad.

### Returns
|Type|Description|
|-|-
[AdOperation](./AdOperation.md)|An operation object that you use to check whether Bing successfully added the ad.

## <a name="withbiddingstrategy-string-biddingstrategy-"></a>withBiddingStrategy(string biddingStrategy)
Sets the ad group's bidding strategy. 

### Arguments
|Name|Type|Description|
|-|-|-
biddingStrategy|string|The bidding strategy to apply to the ad group. The following are the possible case-sensitive values.<ul><li>MANUAL_CPC</li></ul>For information about these strategies, see [Bid Strategy Types](/bingads/guides/budget-bid-strategies#bidstrategytypes).

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the bidding strategy applied.
