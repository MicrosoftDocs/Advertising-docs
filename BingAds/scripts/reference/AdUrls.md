# AdUrls
Provides access to the URLs for this ad.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[getCustomParameters](#getcustomparameters)|Object|Returns the custom parameters of the ad.
[getFinalUrl](#getfinalurl)|String|Returns the final URL of this ad.<br />
[getMobileFinalUrl](#getmobilefinalurl)|String|Returns the mobile final URL of this ad.<br />
[getTrackingTemplate](#gettrackingtemplate)|String|Returns the tracking template of this ad.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="getcustomparameters"></a>getCustomParameters
Returns the custom parameters of the ad.

The returned object is in the format <code>{key1: 'value1', key2: 'value2', key3: 'value3'}.</code>


The name of a custom parameter can contain only alphanumeric characters, and custom parameter values may not contain white space. When referring to the custom parameter in final URLs and tracking templates, you should surround the custom parameter in braces, and prefix an underscore to its name, for example {_param}.

You can have up to 3 custom parameters for an entity. The key and value must not exceed 16 and 200 bytes respectively.

Custom parameters specified at a lower level entity will override the setting specified at a higher level entity, for example, setting custom parameters at the ad group level overrides the setting at the campaign level, and custom parameters specified at the ad level override the setting at the ad group level.



### Returns:
|Type|Description|
|-|-
Object|The custom parameters of the ad as a map of the following form: {key1: 'value1', key2: 'value2', key3: 'value3'}.
&nbsp;|&nbsp;
## <a name="getfinalurl"></a>getFinalUrl
Returns the final URL of this ad.

### Returns:
|Type|Description|
|-|-
String|The final URL of the ad.
&nbsp;|&nbsp;
## <a name="getmobilefinalurl"></a>getMobileFinalUrl
Returns the mobile final URL of this ad.

### Returns:
|Type|Description|
|-|-
String|The mobile final URL of the ad.
&nbsp;|&nbsp;
## <a name="gettrackingtemplate"></a>getTrackingTemplate
Returns the tracking template of this ad.

### Returns:
|Type|Description|
|-|-
String|The tracking template of the ad.
&nbsp;|&nbsp;
