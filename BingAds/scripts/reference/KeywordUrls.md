# KeywordUrls
Provides access to the URLs for this keyword.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[clearFinalUrl](#clearfinalurl)|void|Clears the final URL of this keyword.<br />
[clearMobileFinalUrl](#clearmobilefinalurl)|void|Clears the mobile final URL of this keyword. <br />
[clearTrackingTemplate](#cleartrackingtemplate)|void|Clears the tracking template of this keyword.<br />
[getCustomParameters](#getcustomparameters)|Object|Returns the custom parameters of this keyword. The returned object is in the format <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.<br />
[getFinalUrl](#getfinalurl)|String|Returns the final URL of this keyword.<br />
[getMobileFinalUrl](#getmobilefinalurl)|String|Returns the mobile final URL of this keyword. <br />
[getTrackingTemplate](#gettrackingtemplate)|String|Returns the tracking template of this keyword.<br />
[setCustomParameters(Object customParameters)](#setcustomparameters~object-customparameters~)|void|Sets the custom parameters of this keyword. The returned object is in the format <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.<br />
[setFinalUrl(String finalUrl)](#setfinalurl~string-finalurl~)|void|Sets the final URL of this keyword.<br />
[setMobileFinalUrl(String mobileFinalUrl)](#setmobilefinalurl~string-mobilefinalurl~)|void|Sets the mobile final URL of this keyword. <br />
[setTrackingTemplate(String trackingTemplate)](#settrackingtemplate~string-trackingtemplate~)|void|Sets the tracking template of this keyword.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="clearfinalurl"></a>clearFinalUrl
Clears the final URL of this keyword.

### Returns:
|Type|Description|
|-|-
void|
&nbsp;|&nbsp;
## <a name="clearmobilefinalurl"></a>clearMobileFinalUrl
Clears the mobile final URL of this keyword. 

### Returns:
|Type|Description|
|-|-
void|
&nbsp;|&nbsp;
## <a name="cleartrackingtemplate"></a>clearTrackingTemplate
Clears the tracking template of this keyword.


If you clear the tracking template specified at a lower level entity (for example, a keyword), and you have also specified tracking template on a higher level entity, (for example, the parent ad group), then Bing Ads will use the tracking template specified at the higher level entity (the ad group level tracking template will be used). To completely clear the tracking template, it must be cleared at all levels of the hierarchy at which it was set.

### Returns:
|Type|Description|
|-|-
void|
&nbsp;|&nbsp;
## <a name="getcustomparameters"></a>getCustomParameters
Returns the custom parameters of this keyword. The returned object is in the format <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.


The name of a custom parameter can contain only alphanumeric characters, and custom parameter values may not contain white space. When referring to the custom parameter in final URLs and tracking templates, you should surround the custom parameter in braces, and prefix an underscore to its name, for example {_param}.

You can have up to 3 custom parameters for an entity. The key and value must not exceed 16 and 200 bytes respectively.

Custom parameters specified at a lower level entity will override the setting specified at a higher level entity, for example, setting custom parameters at the ad group level overrides the setting at the campaign level, and custom parameters specified at the ad level override the setting at the ad group level.

### Returns:
|Type|Description|
|-|-
Object|The custom parameters of the keyword as a map of the following form: {key1: 'value1', key2: 'value2', key3: 'value3'}.
&nbsp;|&nbsp;
## <a name="getfinalurl"></a>getFinalUrl
Returns the final URL of this keyword.

### Returns:
|Type|Description|
|-|-
String|The final URL of the keyword.
&nbsp;|&nbsp;
## <a name="getmobilefinalurl"></a>getMobileFinalUrl
Returns the mobile final URL of this keyword. 

### Returns:
|Type|Description|
|-|-
String|The mobile final URL of the keyword.
&nbsp;|&nbsp;
## <a name="gettrackingtemplate"></a>getTrackingTemplate
Returns the tracking template of this keyword.


You can optionally use the tracking template to specify additional tracking parameters or redirects. Bing Ads will use this template to assemble the actual destination URL to associate with the ad.

A tracking template specified at a lower level entity will override the setting specified at a higher level entity, for example, a tracking template at the ad group level overrides the setting at the campaign level.

### Returns:
|Type|Description|
|-|-
String|The tracking template of the keyword.
&nbsp;|&nbsp;
## <a name="setcustomparameters~object-customparameters~"></a>setCustomParameters(Object customParameters)
Sets the custom parameters of this keyword. The returned object is in the format <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.


The name of a custom parameter can contain only alphanumeric characters, and custom parameter values may not contain white space. When referring to the custom parameter in final URLs and tracking templates, you should surround the custom parameter in braces, and prefix an underscore to its name, for example {_param}.

You can have up to 3 custom parameters for an entity. The key and value must not exceed 16 and 200 bytes respectively.

Custom parameters specified at a lower level entity will override the setting specified at a higher level entity, for example, setting custom parameters at the ad group level overrides the setting at the campaign level, and custom parameters specified at the ad level override the setting at the ad group level.

This method will replace any existing custom parameters.

To clear the custom parameters of the keyword, pass an empty object, for example `setCustomParamters({})`.  If custom parameters are cleared at a lower level entity (for example a keyword). and custom parameters are specified on a higher level entity, (for example, the parent ad group), then Bing Ads uses the custom parameters specified at the higher level (for example, the ad group custom parameters will be used).  To completely clear custom parameters they must be cleared at all levels.

### Arguments:
|Name|Type|Description|
|-|-|-
customParameters|Object|The custom parameters of the keyword as a map of the<br />        form <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
void|
&nbsp;|&nbsp;
## <a name="setfinalurl~string-finalurl~"></a>setFinalUrl(String finalUrl)
Sets the final URL of this keyword.

### Arguments:
|Name|Type|Description|
|-|-|-
finalUrl|String|The final URL of the keyword.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
void|
&nbsp;|&nbsp;
## <a name="setmobilefinalurl~string-mobilefinalurl~"></a>setMobileFinalUrl(String mobileFinalUrl)
Sets the mobile final URL of this keyword. 

### Arguments:
|Name|Type|Description|
|-|-|-
mobileFinalUrl|String|The mobile final URL of the keyword.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
void|
&nbsp;|&nbsp;
## <a name="settrackingtemplate~string-trackingtemplate~"></a>setTrackingTemplate(String trackingTemplate)
Sets the tracking template of this keyword.

### Arguments:
|Name|Type|Description|
|-|-|-
trackingTemplate|String|The tracking template of the keyword.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
void|
&nbsp;|&nbsp;
