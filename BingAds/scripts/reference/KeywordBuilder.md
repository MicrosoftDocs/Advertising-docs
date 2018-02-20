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
[withCustomParameters( String customParameters)](#withcustomparameters~-string-customparameters~)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the custom parameters set to the specified value. The custom parameters are in the format: <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.<br />
[withDestinationUrl(String destinationUrl)](#withdestinationurl~string-destinationurl~)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the destination URL set to the specified value.<br />
[withFinalUrl(String finalUrl)](#withfinalurl~string-finalurl~)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the final URL set to the specified value.<br />
[withMobileFinalUrl(String mobileFinalUrl)](#withmobilefinalurl~string-mobilefinalurl~)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the mobile final URL set to the specified value.<br />
[withText(String text)](#withtext~string-text~)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the text set to the specified value. Setting the text requires specifying the match type as well by means of extra characters as shown below:<br /> <br /> &nbsp;•	kwBuilder.withText("books") - broad match.<br /> &nbsp;•	kwBuilder.withText("\"books\"") - phrase match.<br /> &nbsp;•	kwBuilder.withText("[the origin of species]") - exact match<br />        <br />
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
Returns a keyword builder with the custom parameters set to the specified value. The custom parameters are in the format: <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.


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
## <a name="withdestinationurl~string-destinationurl~"></a>withDestinationUrl(String destinationUrl)
Returns a keyword builder with the destination URL set to the specified value.


### Returns:
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder)|
&nbsp;|&nbsp;
## <a name="withfinalurl~string-finalurl~"></a>withFinalUrl(String finalUrl)
Returns a keyword builder with the final URL set to the specified value.


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
Returns a keyword builder with the text set to the specified value. Setting the text requires specifying the match type as well by means of extra characters as shown below:<br /> <br /> &nbsp;•	kwBuilder.withText("books") - broad match.<br /> &nbsp;•	kwBuilder.withText("\"books\"") - phrase match.<br /> &nbsp;•	kwBuilder.withText("[the origin of species]") - exact match<br />        


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
