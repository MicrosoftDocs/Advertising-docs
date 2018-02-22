# KeywordBuilder
Provides methods for defining and building a keyword.

Example usage:
```javascript
 var keywordOperation = adGroup.newKeywordBuilder()
    .withText("text")
    .withCpc(1.5)
    .withFinalUrl("http://www.example.com")
    .build();
 var keyword = keywordOperation.getResult();
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[build](#build)|[KeywordOperation](./KeywordOperation)|Returns a keyword operation with the defined properties which can later be used to construct the keyword.<br />
[withCpc(double cpc)](#withcpc~double-cpc~)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the CPC property set to the specified value.<br />
[withCustomParameters( String customParameters)](#withcustomparameters~-string-customparameters~)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the custom parameters set to the specified value.
[withFinalUrl(String finalUrl)](#withfinalurl~string-finalurl~)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the final URL set to the specified value.<br />
[withMobileFinalUrl(String mobileFinalUrl)](#withmobilefinalurl~string-mobilefinalurl~)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the mobile final URL set to the specified value.<br />
[withText(String text)](#withtext~string-text~)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the text set to the specified value.      <br />
[withTrackingTemplate( String trackingTemplate)](#withtrackingtemplate~-string-trackingtemplate~)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the tracking template set to the specified value.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="build"></a>build
Returns a keyword operation with the defined properties which can later be used to construct the keyword.

### Returns:
|Type|Description|
|-|-
[KeywordOperation](./KeywordOperation)|The associated keyword operation.
&nbsp;|&nbsp;
## <a name="withcpc~double-cpc~"></a>withCpc(double cpc)
Returns a keyword builder with the CPC property set to the specified value.

### Arguments:
|Name|Type|Description|
|-|-|-
cpc|double|The max CPC bid of the keyword.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder)|The keyword builder with the specified max CPC.
&nbsp;|&nbsp;
## <a name="withcustomparameters~-string-customparameters~"></a>withCustomParameters( String customParameters)
Returns a keyword builder with the custom parameters set to the specified value.

The name of a custom parameter can contain only alphanumeric characters, and custom parameter values may not contain white space. When referring to the custom parameter in final URLs and tracking templates, you should surround the custom parameter in braces, and prefix an underscore to its name, for example {_param}.

You can have up to 3 custom parameters for an entity. The key and value must not exceed 16 and 200 bytes respectively.

Custom parameters specified at a lower level entity will override the setting specified at a higher level entity, for example, setting custom parameters at the ad group level overrides the setting at the campaign level, and custom parameters specified at the ad level override the setting at the ad group level.

### Arguments:
|Name|Type|Description|
|-|-|-
customParameters|Object|The custom parameters of the keyword as a map of the<br />        following form: <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder)|The keyword builder with the specified custom parameters.
&nbsp;|&nbsp;
## <a name="withfinalurl~string-finalurl~"></a>withFinalUrl(String finalUrl)
Returns a keyword builder with the final URL set to the specified value.


The final URL represents the actual landing page for your ad. The final URL must be the URL of the page that the user ends up on after clicking on your ad, once all the redirects have taken place.

Final URLs follow the same override rules as destination URLs. For example, a final URL at the keyword level overrides a final URL at an ad level.

### Arguments:
|Name|Type|Description|
|-|-|-
finalUrl|String|The final URL for the keyword.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder)|The keyword builder with the specified final URL.
&nbsp;|&nbsp;
## <a name="withmobilefinalurl~string-mobilefinalurl~"></a>withMobileFinalUrl(String mobileFinalUrl)
Returns a keyword builder with the mobile final URL set to the specified value.


The mobile final URL represents the actual landing page for your ad on a mobile device. The final mobile URL must be the URL of the page that the user ends up on after clicking on your ad on a mobile device, once all the redirects have taken place.

Mobile final URLs follow the same override rules as destination URLs. For example, a mobile final URL at the keyword level overrides a mobile final URL at an ad level.

### Arguments:
|Name|Type|Description|
|-|-|-
mobileFinalUrl|String|The mobile final URL for the keyword.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder)|The keyword builder with the specified final URL.
&nbsp;|&nbsp;
## <a name="withtext~string-text~"></a>withText(String text)
Returns a keyword builder with the text set to the specified value.      


To specify match type for the new keyword:

- `keywordBuilder.withText("books")` - broad match.
- `keywordBuilder.withText("\"books\"")` - phrase match.
- `keywordBuilder.withText("[hardcover books]")` - exact match.


### Arguments:
|Name|Type|Description|
|-|-|-
text|String|The text of the keyword.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder)|Keyword builder with the specified text.
&nbsp;|&nbsp;
## <a name="withtrackingtemplate~-string-trackingtemplate~"></a>withTrackingTemplate( String trackingTemplate)
Returns a keyword builder with the tracking template set to the specified value.


You can optionally use the tracking template to specify additional tracking parameters or redirects. Bing Ads will use this template to assemble the actual destination URL to associate with the ad.

A tracking template specified at a lower level entity will override the setting specified at a higher level entity, for example, a tracking template at the ad group level overrides the setting at the campaign level.

### Arguments:
|Name|Type|Description|
|-|-|-
trackingTemplate|String|The tracking template for the keyword.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder)|The keyword builder with the specified tracking template.
&nbsp;|&nbsp;
