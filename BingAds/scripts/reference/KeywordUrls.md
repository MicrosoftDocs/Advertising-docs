---
title: "KeywordUrls object"
description: "Contains the methods for managing the keyword's URLs."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# KeywordUrls
Contains the methods for managing the keyword's URLs. For information, see [URL Tracking with Upgraded URLs](/bingads/guides/url-tracking-upgraded-urls).

## Methods
|Method Name|Return Type|Description|
|-|-|-
[clearTrackingTemplate](#cleartrackingtemplate)|void|Removes the keyword's tracking template.
[getCustomParameters](#getcustomparameters)|Object|Returns the keyword's custom parameters.
[getFinalUrl](#getfinalurl)|string|Returns the keyword's final URL.
[getTrackingTemplate](#gettrackingtemplate)|string|Returns the keyword's tracking template.
[setCustomParameters(Object customParameters)](#setcustomparameters~object-customparameters~)|void|Sets the keyword's custom parameters.
[setFinalUrl(String finalUrl)](#setfinalurl~string-finalurl~)|void|Sets the keyword's final URL.
[setTrackingTemplate(String trackingTemplate)](#settrackingtemplate~string-trackingtemplate~)|void|Sets the keyword's tracking template.

## <a name="cleartrackingtemplate"></a>clearTrackingTemplate
Removes the keyword's tracking template. For information about tracking templates, see [Tracking Templates](/bingads/guides/url-tracking-upgraded-urls#trackingtemplatevalidation).

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getcustomparameters"></a>getCustomParameters
Returns the keyword's custom parameters. 

[!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

### Returns
|Type|Description|
|-|-
Object|A map of the keyword's custom parameters.<br /><br />For example, `{key1: 'value1', key2: 'value2', key3: 'value3'}`, where key is the name of the custom parameter and value is the parameter's value.

## <a name="getfinalurl"></a>getFinalUrl
Returns the keyword's final URL. The final URL represents the actual landing page for your ad. 

Final URLs follow the same override rules as destination URLs. For example, a final URL at the keyword level overrides the final URL at the ad level.

### Returns
|Type|Description|
|-|-
string|The keyword's final URL.

## <a name="gettrackingtemplate"></a>getTrackingTemplate
Returns the keyword's tracking template. 

[!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Returns
|Type|Description|
|-|-
string|The keyword's tracking template.

## <a name="setcustomparameters~object-customparameters~"></a>setCustomParameters(Object customParameters)
Sets the keyword's custom parameters. 

[!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

This method replaces all custom parameters already specified in the keyword.

To clear the custom parameters from the keyword, pass an empty object (for example, `setCustomParameters({})`). If you clear the keywords's custom parameters, the keyword inherits the URLs from its parent ad group (if the ad group specifies URLs). To completely clear custom parameters, you must clear them at all levels in the hierarchy.


### Arguments
|Name|Type|Description|
|-|-|-
customParameters|Object|A map of custom parameters to use in the keyword.<br /><br />For example, `{key1: 'value1', key2: 'value2', key3: 'value3'}`, where key is the name of the custom parameter and value is the parameter's value.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="setfinalurl~string-finalurl~"></a>setFinalUrl(String finalUrl)
Sets the keyword's final URL. 

[!INCLUDE[final-url](../includes/final-url.md)]

### Arguments
|Name|Type|Description|
|-|-|-
finalUrl|string|The keyword's final URL.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="settrackingtemplate~string-trackingtemplate~"></a>setTrackingTemplate(String trackingTemplate)
Sets the keyword's tracking template. 

[!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Arguments
|Name|Type|Description|
|-|-|-
trackingTemplate|string|The keyword's tracking template.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

