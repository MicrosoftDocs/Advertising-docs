---
title: "CampaignUrls object"
description: "Contains the methods for managing the campaign's URLs."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# CampaignUrls

Contains the methods for managing the campaign's URLs. For more information, see [URL Tracking with Upgraded URLs](/bingads/guides/url-tracking-upgraded-urls).

## Methods
|Method Name|Return Type|Description|
|-|-|-
[clearTrackingTemplate](#cleartrackingtemplate)|void|Removes the tracking template from this campaign.
[getCustomParameters](#getcustomparameters)|Object|Returns the campaign's custom parameters.
[getTrackingTemplate](#gettrackingtemplate)|string|Returns the campaign's tracking template.
[setCustomParameters(Object customParameters)](#setcustomparameters~object-customparameters~)|void|Sets the campaign's custom parameters.
[setTrackingTemplate(String trackingTemplate)](#settrackingtemplate~string-trackingtemplate~)|void|Sets the campaign's tracking template.

## <a name="cleartrackingtemplate"></a>clearTrackingTemplate
Removes the tracking template from this campaign. For information about tracking templates, see [Tracking Templates](/bingads/guides/url-tracking-upgraded-urls#trackingtemplatevalidation).

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getcustomparameters"></a>getCustomParameters
Returns the campaign's custom parameters.  

[!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

### Returns
|Type|Description|
|-|-
Object|A map of the campaign's custom parameters.<br /><br />For example, `{key1: 'value1', key2: 'value2', key3: 'value3'}`, where key is the name of the custom parameter and value is the parameter's value.

## <a name="gettrackingtemplate"></a>getTrackingTemplate
Returns the campaign's tracking template. 

[!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Returns
|Type|Description|
|-|-
string|The campaign's tracking template.

## <a name="setcustomparameters~object-customparameters~"></a>setCustomParameters(Object customParameters)
Sets the custom parameters for this campaign. Use this method if you include custom substitution strings in your final URL or tracking template.

[!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

This method replaces the campaign's existing custom parameters.

To clear the custom parameters from the campaign, pass an empty object (for example, `setCustomParameters({})`).

### Arguments
|Name|Type|Description|
|-|-|-
customParameters|Object|A map of custom parameters to use in the campaign.<br /><br />For example, `{key1: 'value1', key2: 'value2', key3: 'value3'}`, where key is the name of the custom parameter and value is the parameter's value.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="settrackingtemplate~string-trackingtemplate~"></a>setTrackingTemplate(string trackingTemplate)
Sets the tracking template to use with this campaign. 

[!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Arguments
|Name|Type|Description|
|-|-|-
trackingTemplate|string|The tracking template to use with this campaign.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

