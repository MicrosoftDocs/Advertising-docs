# AdUrls
Provides access to the URLs for this ad.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[getCustomParameters](#getcustomparameters)|Object|Returns the custom query parameters used in the ad's destination URLs.
[getFinalUrl](#getfinalurl)|String|Returns the final destination URL for ads displayed on desktop and tablet devices.
[getMobileFinalUrl](#getmobilefinalurl)|String|Returns the final destination URL for ads displayed on mobile devices.
[getTrackingTemplate](#gettrackingtemplate)|String|Returns the tracking template of this ad.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="getcustomparameters"></a>getCustomParameters
Returns the custom query parameters used in the ad's destination URLs.



### Returns:
|Type|Description|
|-|-
Object|The custom parameters of the ad as an object in the form: {key1: 'value1', key2: 'value2', key3: 'value3'}.
&nbsp;|&nbsp;
## <a name="getfinalurl"></a>getFinalUrl
Returns the final destination URL for ads displayed on desktop and tablet devices.

The final URL represents the actual landing page for your ad. The final URL must be the URL of the page that the user ends up on after clicking on your ad, once all the redirects have taken place.

Final URLs follow the same override rules as destination URLs. For example, a final URL at the keyword level overrides a final URL at an ad level.

### Returns:
|Type|Description|
|-|-
String|The final URL of the ad.
&nbsp;|&nbsp;
## <a name="getmobilefinalurl"></a>getMobileFinalUrl
Returns the final destination URL for ads displayed on mobile devices.

The mobile final URL represents the actual landing page for your ad on a mobile device. The final mobile URL must be the URL of the page that the user ends up on after clicking on your ad on a mobile device, once all the redirects have taken place.

Mobile final URLs follow the same override rules as destination URLs. For example, a mobile final URL at the keyword level overrides a mobile final URL at an ad level.

### Returns:
|Type|Description|
|-|-
String|The mobile final URL of the ad.
&nbsp;|&nbsp;
## <a name="gettrackingtemplate"></a>getTrackingTemplate
Returns the tracking template of this ad.


You can optionally use the tracking template to specify additional tracking parameters or redirects. Bing Ads will use this template to assemble the actual destination URL to associate with the ad.

A tracking template specified at a lower level entity will override the setting specified at a higher level entity, for example, a tracking template at the ad group level overrides the setting at the campaign level.

### Returns:
|Type|Description|
|-|-
String|The tracking template of the ad.
&nbsp;|&nbsp;
