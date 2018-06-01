---
title: "AdGroupUrls object"
description: "Contains the methods for managing the ad group's URLs."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# AdGroupUrls

Contains the methods for managing the ad group's URLs. For more information, see [URL Tracking with Upgraded URLs](/bingads/guides/url-tracking-upgraded-urls).


Example usage:
```javascript
var adGroupSelector = BingAdsApp.adGroups();
 var adGroupIterator = adGroupSelector.get();
 while (adGroupIterator.hasNext()) {
   var adGroup = adGroupIterator.next();

   var adGroupUrls = adGroup.urls();
 }
```

## Methods
|Method Name|Return Type|Description|
|-|-|-
[clearTrackingTemplate](#cleartrackingtemplate)|void|Clears the tracking template from this ad group.
[getCustomParameters](#getcustomparameters)|Object|Returns the ad group's custom parameters.
[getTrackingTemplate](#gettrackingtemplate)|string|Returns the ad group's tracking template.
[setCustomParameters(Object customParameters)](#setcustomparameters~object-customparameters~)|void|Sets the ad group's custom parameters.
[setTrackingTemplate(string trackingTemplate)](#settrackingtemplate~string-trackingtemplate~)|void|Sets the ad group's tracking template.

## <a name="cleartrackingtemplate"></a>clearTrackingTemplate
Clears the tracking template from this ad group. For information about tracking templates, see [Tracking Templates](/bingads/guides/url-tracking-upgraded-urls#trackingtemplatevalidation).

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getcustomparameters"></a>getCustomParameters
Returns the ad group's custom parameters. 

[!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

### Returns
|Type|Description|
|-|-
Object|A map of the ad group's custom parameters. For example, `{key1: 'value1', key2: 'value2', key3: 'value3'}`, where key is the name of the custom parameter and value is the parameter's value.

## <a name="gettrackingtemplate"></a>getTrackingTemplate
Returns the ad group's tracking template.

[!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Returns
|Type|Description|
|-|-
string|The ad group's tracking template.

## <a name="setcustomparameters~object-customparameters~"></a>setCustomParameters(Object customParameters)
Sets the custom parameters for this ad group. 

[!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

This method replaces existing custom parameters already specified in the ad group.

To clear the custom parameters from the ad group, pass an empty object (for example, `setCustomParameters({})`). Because URLs are inherited you must clear the URLs at all levels in the hierarchy. For example, if you clear the ad group's custom parameters, the ad group will inherit the URLs from its parent campaign (if the campaign specifies URLs). To completely clear custom parameters, you must clear them at all levels.


### Arguments
|Name|Type|Description|
|-|-|-
customParameters|Object|A map of custom parameters to use in the ad group. For example, `{key1: 'value1', key2: 'value2', key3: 'value3'}`, where key is the name of the custom parameter and value is the parameter's value.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="settrackingtemplate~string-trackingtemplate~"></a>setTrackingTemplate(string trackingTemplate)
Sets the tracking template to use with this ad group. 

[!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Arguments
|Name|Type|Description|
|-|-|-
trackingTemplate|string|The tracking template to use with this ad group.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

