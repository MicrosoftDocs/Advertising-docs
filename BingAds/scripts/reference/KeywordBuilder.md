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

Contains the methods for defining a keyword. For information about Builders, see [Builders](../concepts/builders).

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
[build](#build)|[KeywordOperation](./KeywordOperation.md)|Returns an operation object, which represents the keyword to create. You must call the operation object's methods to add the keyword.
[withCpc(double cpc)](#withcpc~double-cpc~)|[KeywordBuilder](./KeywordBuilder.md)|Sets the maximum CPC bid to use for this new keyword.
[withCustomParameters(Object customParameters)](#withcustomparameters~object-customparameters~)|[KeywordBuilder](./KeywordBuilder.md)|Sets the keyword's custom parameters.
[withFinalUrl(string finalUrl)](#withfinalurl~string-finalurl~)|[KeywordBuilder](./KeywordBuilder.md)|Sets the keyword's final URL.
[withMobileFinalUrl(string mobileFinalUrl)](#withmobilefinalurl~string-mobilefinalurl~)|[KeywordBuilder](./KeywordBuilder.md)|Sets the keyword's final URL for mobile devices.
[withText(string text)](#withtext~string-text~)|[KeywordBuilder](./KeywordBuilder.md)|Sets the keyword's text.
[withTrackingTemplate(string trackingTemplate)](#withtrackingtemplate~string-trackingtemplate~)|[KeywordBuilder](./KeywordBuilder.md)|Sets the tracking template used with this keyword.


## <a name="build"></a>build
Returns an operation object, which represents the keyword to create. You must call the operation object's methods to add the keyword.

### Returns
|Type|Description|
|-|-
[KeywordOperation](./KeywordOperation.md)|An operation object, which you use to add the keyword.

## <a name="withcpc~double-cpc~"></a>withCpc(double cpc)
Sets the maximum CPC bid to use for this new keyword.

### Arguments
|Name|Type|Description|
|-|-|-
cpc|double|The maximum CPC bid to apply to the keyword. The default bid is 0.30 cents (USD).

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
customParameters|Object|The custom parameters to apply to the ad group. Specify the parameters as a dictionary of key-value pairs. For example, `{key1: 'value1', key2: 'value2', key3: 'value3'}`, where key is the custom parameter's name and value is the parameter's value.

### Returns
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder.md)|Keyword builder with the custom parameters applied.

## <a name="withfinalurl~string-finalurl~"></a>withFinalUrl(string finalUrl)
Sets the keyword's final URL. The final URL represents the actual landing page for your ad. 

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


The final URL is the actual landing page for your ad on a mobile device. The final URL must be the URL of the page that the user ends up on after clicking your ad on a mobile device and after all the redirects have taken place.

Mobile final URLs follow the same override rules as destination URLs. For example, a mobile final URL at the keyword level overrides a mobile final URL at an ad level.

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
- For phrase match, surround the text in quotes (for example, `keywordBuilder.withText("\"books\"")`).
- For exact match, surround the text in square brackets (for example, `keywordBuilder.withText("[hardcover books]")`).


### Arguments
|Name|Type|Description|
|-|-|-
text|string|The keyword's text.

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

