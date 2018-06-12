---
title: "KeywordBuilder object"
description: "Contains the methods for defining a keyword."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# KeywordBuilder

Contains the methods for defining and building a keyword. For information about builders, see [Builders](../concepts/builders.md).

Example usage:
```javascript
 var keywordOperation = adGroup.newKeywordBuilder()
    .withText("text")
    .withCpc(1.5)
    .withFinalUrl("http://www.example.com")
    .build();
 var keyword = keywordOperation.getResult();
```

## Methods
|Method Name|Return Type|Description|
|-|-|-
[build](#build)|[KeywordOperation](./KeywordOperation.md)|Returns an operation object that you use to add the keyword to the ad group.
[withCpc(double cpc)](#withcpc~double-cpc~)|[KeywordBuilder](./KeywordBuilder.md)|Sets the keyword's maximum CPC bid.
[withCustomParameters(Object customParameters)](#withcustomparameters~object-customparameters~)|[KeywordBuilder](./KeywordBuilder.md)|Sets the keyword's custom parameters.
[withFinalUrl(string finalUrl)](#withfinalurl~string-finalurl~)|[KeywordBuilder](./KeywordBuilder.md)|Sets the keyword's final URL.
[withMobileFinalUrl(string mobileFinalUrl)](#withmobilefinalurl~string-mobilefinalurl~)|[KeywordBuilder](./KeywordBuilder.md)|Sets the keyword's final URL for mobile devices.
[withText(string text)](#withtext~string-text~)|[KeywordBuilder](./KeywordBuilder.md)|Sets the keyword's text.
[withTrackingTemplate(string trackingTemplate)](#withtrackingtemplate~string-trackingtemplate~)|[KeywordBuilder](./KeywordBuilder.md)|Sets the tracking template used with this keyword.


## <a name="build"></a>build
Returns an operation object that you use to add the keyword to the ad group.

### Returns
|Type|Description|
|-|-
[KeywordOperation](./KeywordOperation.md)|An operation object that you use to add the keyword.

## <a name="withcpc~double-cpc~"></a>withCpc(double cpc)
Sets the keyword's maximum CPC bid.

Specifies the bid amount to use when the keyword matches the user's search term and the ad group's bid strategy is ManualCpc or EnhancedCpc.

To use the bid amount specified at the ad group level, do not call this method.

For more information about bid amounts, see [Bid](/bingads/campaign-management-service/keyword#bid) and [BiddingScheme](/bingads/campaign-management-service/keyword#biddingscheme). 


### Arguments
|Name|Type|Description|
|-|-|-
cpc|double|The CPC bid to apply to the keyword. The account's currency determines the minimum and maximum bid values. For more information, see [Bid and budget currencies](/bingads/guides/currencies#bidandbudget).

### Returns
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder.md)|Keyword builder with the CPC bid applied.


## <a name="withcustomparameters~object-customparameters~"></a>withCustomParameters(Object customParameters)
Sets the keyword's custom parameters. 

[!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

### Arguments
|Name|Type|Description|
|-|-|-
customParameters|Object|The custom parameters to apply to the keyword's final URL. These are the query parameters you want to add to the final URL. You can specify a maximum of three custom parameters. Specify the parameters as a map of key-value pairs.<br /><br />For example, `{key1: 'value1', key2: 'value2', key3: 'value3'}`, where key is the custom parameter's name and value is the parameter's value.

### Returns
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder.md)|Keyword builder with the custom parameters applied.


## <a name="withfinalurl~string-finalurl~"></a>withFinalUrl(string finalUrl)
Sets the keyword's final URL.  

[!INCLUDE[final-url](../includes/final-url.md)]

### Arguments
|Name|Type|Description|
|-|-|-
finalUrl|string|The final URL for the keyword.

### Returns
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder.md)|Keyword builder with the final URL applied.



## <a name="withmobilefinalurl~string-mobilefinalurl~"></a>withMobileFinalUrl(string mobileFinalUrl)
Sets the keyword's final URL for mobile devices.

The final URL must be the URL of the page that the user ends up on after clicking your ad (and after all redirects have taken place).

Final URLs follow the same override rules as destination URLs. For example, a mobile final URL at the keyword level overrides a mobile final URL at the ad level.

If you specify a mobile final URL you must also specify FinalUrl.

### Arguments
|Name|Type|Description|
|-|-|-
mobileFinalUrl|string|The final URL for mobile devices.

### Returns
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder.md)|Keyword builder with the mobile final URL applied.

## <a name="withtext~string-text~"></a>withText(string text)
Sets the keyword's text. 

To specify the keyword's match type, use the following syntax:

- For broad match, use no match type syntax (for example, `keywordBuilder.withText("books")`).
- For broad match modifier, prepend the text with a plus sign (+) (for example, `keywordBuilder.withText("+books")`).
- For phrase match, place quotes around the text (for example, `keywordBuilder.withText("\"books\"")`).
- For exact match, place square brackets around the text (for example, `keywordBuilder.withText("[hardcover books]")`).


### Arguments
|Name|Type|Description|
|-|-|-
text|string|The keyword's text. The text may contain a maximum of 100 characters. Specify the keyword in the locale of the ad group's language value.

### Returns
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder.md)|Keyword builder with the keyword text applied.

## <a name="withtrackingtemplate~string-trackingtemplate~"></a>withTrackingTemplate(string trackingTemplate)
Sets the tracking template to use with the keyword. 

[!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Arguments
|Name|Type|Description|
|-|-|-
trackingTemplate|string|The tracking template to use with this keyword.

### Returns
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder.md)|Keyword builder with the tracking template applied.

