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
Contains the methods for managing the keyword's URLs, tracking template, and custom parameters. For information, see [URL Tracking with Upgraded URLs](/bingads/guides/url-tracking-upgraded-urls).

## Methods
|Method Name|Return Type|Description|
|-|-|-
[clearFinalUrl](#clearfinalurl)|void|Removes the keyword's final URL.
[clearMobileFinalUrl](#clearmobilefinalurl)|void|Removes the keyword's final URL for mobile devices.
[clearTrackingTemplate](#cleartrackingtemplate)|void|Removes the keyword's tracking template.
[getCustomParameters](#getcustomparameters)|Object|Gets the keyword's custom parameters.
[getFinalUrl](#getfinalurl)|string|Gets the keyword's final URL.
[getMobileFinalUrl](#getmobilefinalurl)|string|Gets the keyword's final URL for mobile devices.
[getTrackingTemplate](#gettrackingtemplate)|string|Gets the keyword's tracking template.
[setCustomParameters(Object customParameters)](#setcustomparameters-object-customparameters-)|void|Sets the keyword's custom parameters.
[setFinalUrl(String finalUrl)](#setfinalurl-string-finalurl-)|void|Sets the keyword's final URL.
[setMobileFinalUrl(String finalUrl)](#setmobilefinalurl-string-finalurl-)|void|Sets the keyword's final URL for mobile.
[setTrackingTemplate(String trackingTemplate)](#settrackingtemplate-string-trackingtemplate-)|void|Sets the keyword's tracking template.

## <a name="clearfinalurl"></a>clearFinalUrl
Removes the keyword's final URL.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="clearmobilefinalurl"></a>clearMobileFinalUrl
Removes the keyword's final URL for mobile devices.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="cleartrackingtemplate"></a>clearTrackingTemplate
Removes the keyword's tracking template. 

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="getcustomparameters"></a>getCustomParameters
Gets the keyword's custom parameters. 

[!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

### Returns
|Type|Description|
|-|-
Object|A map of the keyword's custom parameters.<br /><br />For example, `{key1: 'value1', key2: 'value2', key3: 'value3'}`, where key is the name of the custom parameter and value is the parameter's value.


## <a name="getfinalurl"></a>getFinalUrl
Gets the keyword's final URL. This is the URL of the webpage that the user is taken to when they click your ad. 

The same override rules apply as elsewhere. For example, specifying a keyword's final URL overrides the ad's final URL.

### Returns
|Type|Description|
|-|-
string|The keyword's final URL.


## <a name="getmobilefinalurl"></a>getMobileFinalUrl
Gets the keyword's final URL for mobile devices. This is the URL of the mobile webpage that the user is taken to when they click your ad. 

The same override rules apply as elsewhere. For example, specifying a keyword's mobile final URL overrides the ad's mobile final URL.

### Returns
|Type|Description|
|-|-
string|The keyword's final URL for mobile devices.


## <a name="gettrackingtemplate"></a>getTrackingTemplate
Gets the keyword's tracking template. 

[!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Returns
|Type|Description|
|-|-
string|The keyword's tracking template.

## <a name="setcustomparameters-object-customparameters-"></a>setCustomParameters(Object customParameters)
Sets the keyword's custom parameters. Use this method if you include custom substitution strings in your final URL or tracking template.

To use a customer parameter name in the final URL or tracking template, you must enclose the name in curly braces and prepend an underscore (\_) to the name. For example, if the parameter name is foo, use {_foo} in the tracking template or final URL. Do not add a leading underscore to the parameter name when you define the custom parameters object. 

Calling this method replaces the keywords's existing custom parameters.

To clear the custom parameters from the keyword, pass an empty object (for example, `setCustomParameters({})`). If you clear the keywords's custom parameters, the keyword inherits the URLs from its parent ad group (if the ad group specifies URLs). To completely clear custom parameters, you must clear them at all levels in the hierarchy.

[!INCLUDE[custom-parameters](../includes/custom-parameters.md)]


### Arguments
|Name|Type|Description|
|-|-|-
customParameters|Object|A map of custom parameters to use in the keyword.<br /><br />For example, `{key1: 'value1', key2: 'value2', key3: 'value3'}`, where key is the name of the custom parameter and value is the parameter's value. The parameter's name may contain only alphanumeric characters and the parameter's value may not contain white space. The name may contain a maximum of 60 bytes and the value may contain a maximum of 200 bytes.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="setfinalurl-string-finalurl-"></a>setFinalUrl(String finalUrl)
Sets the keyword's final URL. 

[!INCLUDE[final-url](../includes/final-url.md)]

If you specify a property value that's not valid, the call silently fails. To confirm whether the property was actually updated, you must get the object again and test whether the property's value equals the new value. For information, see [Handling errors and warnings](../concepts/errors-and-warnings.md).

### Arguments
|Name|Type|Description|
|-|-|-
finalUrl|string|The keyword's final URL.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="setmobilefinalurl-string-finalurl-"></a>setMobileFinalUrl(String finalUrl)
Sets the keyword's final URL for mobile devices. 

The final URL identifies the webpage that the user is taken to when they click your ad. If not specified, the entity inherits the final URL from its parent entity. For example, the keyword entity inherits the ad's final URL. Specify the keyword's final URL if you want to override the ad's final URL.

For more information, see [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)

To specify a final URL for mobil devices, you must first specify a final URL for non-mobile devices (see `setFinalUrl()`).

If you specify a property value that's not valid, the call silently fails. To confirm whether the property was actually updated, you must get the object again and test whether the property's value equals the new value. For information, see [Handling errors and warnings](../concepts/errors-and-warnings.md).

### Arguments
|Name|Type|Description|
|-|-|-
finalUrl|string|The keyword's final URL mobile devices.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="settrackingtemplate-string-trackingtemplate-"></a>setTrackingTemplate(String trackingTemplate)
Sets the keyword's tracking template. 

[!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

If you specify a property value that's not valid, the call silently fails. To confirm whether the property was actually updated, you must get the object again and test whether the property's value equals the new value. For information, see [Handling errors and warnings](../concepts/errors-and-warnings.md).

### Arguments
|Name|Type|Description|
|-|-|-
trackingTemplate|string|The keyword's tracking template.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

