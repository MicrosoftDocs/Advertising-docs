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
        .withFinalUrl('LANDING PAGE URL GOES HERE')
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
[withDescription(string description)](#withdescription-string-description-)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder.md)|Sets the ad's copy.
[withFinalUrl(string finalUrl)](#withfinalurl-string-finalurl-)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder.md)|Sets the ad's landing page URL.
[withHeadlinePart1(string headlinePart1)](#withheadlinepart1-string-headlinepart1-)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder.md)|Sets the first part of the ad's title.
[withHeadlinePart2(string headlinePart2)](#withheadlinepart2-string-headlinepart2-)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder.md)|Sets the second part of the ad's title.


## <a name="build"></a>build
Creates the ad and returns an operation object that you can use to check whether Bing successfully added the ad.

For limits on the number of ads you can add to ad group, see [Entity hierarch limits](/bingads/guides/entity-hierarchy-limits#ads).

### Returns
|Type|Description|
|-|-
[AdOperation](./AdOperation.md)|An operation object that you use to check whether Bing successfully added the ad.


## <a name="withdescription-string-description-"></a>withDescription(string description)
Sets the ad's copy text. 

### Arguments
|Name|Type|Description|
|-|-|-
description|string|The ad's copy text. For information about copy limits and including dynamic text strings, see [Bing Ads API](/bingads/campaign-management-service/expandedtextad#text). 

### Returns
|Type|Description|
|-|-
[ExpandedTextAdBuilder](./ExpandedTextAdBuilder.md)|Ad builder with the description applied.


## <a name="withdescription-string-finalurl-"></a>withFinalUrl(string finalUrl)
Sets the ad's landing page URL. 

### Arguments
|Name|Type|Description|
|-|-|-
finalUrl|string|The ad's landing page URL. For information about URL limits, see [Bing Ads API](/bingads/campaign-management-service/expandedtextad#finalurls). 

### Returns
|Type|Description|
|-|-
[ExpandedTextAdBuilder](./ExpandedTextAdBuilder.md)|Ad builder with the final URL applied.


## <a name="withheadlinepart1-string-headlinepart1--"></a>withHeadlinePart1(string headlinePart1)
Sets the first part of the ad's title.

### Arguments
|Name|Type|Description|
|-|-|-
headlinePart1|string|The first part of the ad's title. When Bing generates the ad's title using part 1 and part 2 of the title, it concatenates the parts using " - ". You may not specify the dash in either parts of the title. Each part of the title must contain at least one word. For information about additional title limits and including dynamic text strings in the title, see [Bing Ads API](/bingads/campaign-management-service/expandedtextad#titlepart1). 

### Returns
|Type|Description|
|-|-
[ExpandedTextAdBuilder](./ExpandedTextAdBuilder.md)|Ad builder with part 1 of the ad's title applied.


## <a name="withheadlinepart2-string-headlinepart2--"></a>withHeadlinePart2(string headlinePart2)
Sets the second part of the ad's title.

### Arguments
|Name|Type|Description|
|-|-|-
headlinePart2|string|The second part of the ad's title. When Bing generates the ad's title using part 1 and part 2 of the title, it concatenates the parts using " - ". You may not specify the dash in either parts of the title. Each part of the title must contain at least one word. For information about additional title limits and including dynamic text strings in the title, see [Bing Ads API](/bingads/campaign-management-service/expandedtextad#titlepart1). 

### Returns
|Type|Description|
|-|-
[ExpandedTextAdBuilder](./ExpandedTextAdBuilder.md)|Ad builder with part 1 of the ad's title applied.
