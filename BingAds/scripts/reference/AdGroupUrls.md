# AdGroupUrls
Provides access to the URLs for this ad group.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[clearTrackingTemplate](#cleartrackingtemplate)|void|Clears the tracking template of this ad group.<br />
[getCustomParameters](#getcustomparameters)|Object|Returns the custom parameters of this ad group.
[getTrackingTemplate](#gettrackingtemplate)|String|Returns the tracking template of this ad group.<br />
[setCustomParameters(Object customParameters)](#setcustomparameters~object-customparameters~)|void|Sets the custom parameters of this ad group.<br />
[setTrackingTemplate(String trackingTemplate)](#settrackingtemplate~string-trackingtemplate~)|void|Sets the tracking template of this ad group.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="cleartrackingtemplate"></a>clearTrackingTemplate
Clears the tracking template of this ad group.


If you clear the tracking template specified at a lower level entity (for example, a keyword), and you have also specified tracking template on a higher level entity, (for example, the parent ad group), then Bing Ads will use the tracking template specified at the higher level entity (the ad group level tracking template will be used). To completely clear the tracking template, it must be cleared at all levels of the hierarchy at which it was set.

### Returns:
|Type|Description|
|-|-
void|
&nbsp;|&nbsp;
## <a name="getcustomparameters"></a>getCustomParameters
Returns the custom parameters of this ad group.

The name of a custom parameter can contain only alphanumeric characters, and custom parameter values may not contain white space. When referring to the custom parameter in final URLs and tracking templates, you should surround the custom parameter in braces, and prefix an underscore to its name, for example {_param}.

You can have up to 3 custom parameters for an entity. The key and value must not exceed 16 and 200 bytes respectively.

Custom parameters specified at a lower level entity will override the setting specified at a higher level entity, for example, setting custom parameters at the ad group level overrides the setting at the campaign level, and custom parameters specified at the ad level override the setting at the ad group level.

### Returns:
|Type|Description|
|-|-
Object|The custom parameters of the ad group as a map of the form: `{key1: 'value1', key2: 'value2', key3: 'value3'}`.
&nbsp;|&nbsp;
## <a name="gettrackingtemplate"></a>getTrackingTemplate
Returns the tracking template of this ad group.


You can optionally use the tracking template to specify additional tracking parameters or redirects. Bing Ads will use this template to assemble the actual destination URL to associate with the ad.

A tracking template specified at a lower level entity will override the setting specified at a higher level entity, for example, a tracking template at the ad group level overrides the setting at the campaign level.

### Returns:
|Type|Description|
|-|-
String|The tracking template of the ad group.
&nbsp;|&nbsp;
## <a name="setcustomparameters~object-customparameters~"></a>setCustomParameters(Object customParameters)
Sets the custom parameters of this ad group.


The name of a custom parameter can contain only alphanumeric characters, and custom parameter values may not contain white space. When referring to the custom parameter in final URLs and tracking templates, you should surround the custom parameter in braces, and prefix an underscore to its name, for example {_param}.

You can have up to 3 custom parameters for an entity. The key and value must not exceed 16 and 200 bytes respectively.

Custom parameters specified at a lower level entity will override the setting specified at a higher level entity, for example, setting custom parameters at the ad group level overrides the setting at the campaign level, and custom parameters specified at the ad level override the setting at the ad group level.

This method will replace any existing custom parameters.

To clear the custom parameters of the ad group pass an empty object, for example `setCustomParamters({})`.  If custom parameters are cleared at a lower level entity (for example a keyword). and custom parameters are specified on a higher level entity, (for example, the parent ad group), then Bing Ads uses the custom parameters specified at the higher level (for example, the ad group custom parameters will be used).  To completely clear custom parameters they must be cleared at all levels.

### Arguments:
|Name|Type|Description|
|-|-|-
customParameters|Object|The custom parameters of the ad group as a map of the<br />        form <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
void|
&nbsp;|&nbsp;
## <a name="settrackingtemplate~string-trackingtemplate~"></a>setTrackingTemplate(String trackingTemplate)
Sets the tracking template of this ad group.


You can optionally use the tracking template to specify additional tracking parameters or redirects. Bing Ads will use this template to assemble the actual destination URL to associate with the ad.

A tracking template specified at a lower level entity will override the setting specified at a higher level entity, for example, a tracking template at the ad group level overrides the setting at the campaign level.

### Arguments:
|Name|Type|Description|
|-|-|-
trackingTemplate|String|The tracking template of the ad group.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
void|
&nbsp;|&nbsp;
