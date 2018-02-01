# ExpandedTextAdBuilder
Provides methods to define an expanded text ad.

Example usage:
```javascript
 var adOperation = adGroup.newAd().expandedTextAdBuilder()
    .withHeadlinePart1("First headline of ad")
    .withHeadlinePart2("Second headline of ad")
    .withDescription("Ad description")
    .withPath1("path1")
    .withPath2("path2")
    .withFinalUrl("http://www.example.com")
    .build();
 var ad = adOperation.getResult();
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[build](#build)|[AdOperation](./AdOperation)|Creates and returns an ad operation that can later be used to construct the new expanded text ad in the system.<br />
[withCustomParameters(String customParameters)](#withcustomparameters~string-customparameters~)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|Sets the custom parameters used with this new expanded text ad. The parameters must be specified as an Object in the form of a map such as <code>{key1: ‘value1’, key2: ‘value2’, key3: ‘value3’}</code>."<br />
[withDescription(String description)](#withdescription~string-description~)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|Sets the description of this new expanded text ad. <br />
[withFinalUrl(String finalUrl)](#withfinalurl~string-finalurl~)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|Sets the final URL of this new expanded text to the specified value.<br />
[withHeadlinePart1(String headlinePart1)](#withheadlinepart1~string-headlinepart1~)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|Sets the first part of the headline of this new expanded text ad to the specified value.<br />
[withHeadlinePart2(String headlinePart2)](#withheadlinepart2~string-headlinepart2~)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|Sets the second part of the headline of this new expanded text ad to the specified value.<br />
[withMobileFinalUrl(String mobileFinalUrl)](#withmobilefinalurl~string-mobilefinalurl~)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|Sets the mobile final URL of this new expanded text ad to the specified value.<br />
[withPath1(String path1)](#withpath1~string-path1~)|[ExpandedTextAdBuilder](ExpandedTextAdBuilder)|Sets the first path of the display URL of this new expanded text ad to the specified value.<br />
[withPath2(String path2)](#withpath2~string-path2~)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|Sets the second path of the display URL of this new expanded text ad to the specified value.<br />
[withTrackingTemplate(String trackingTemplate)](#withtrackingtemplate~string-trackingtemplate~)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|Sets the tracking template of this new expanded text ad to the specified value.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="build"></a>build
Creates and returns an ad operation that can later be used to construct the new expanded text ad in the system.

### Returns:
|Type|Description|
|-|-
[AdOperation](./AdOperation)|The associated ad operation.
&nbsp;|&nbsp;
## <a name="withcustomparameters~string-customparameters~"></a>withCustomParameters(String customParameters)
Sets the custom parameters used with this new expanded text ad. The parameters must be specified as an Object in the form of a map such as <code>{key1: ‘value1’, key2: ‘value2’, key3: ‘value3’}</code>."

### Arguments:
|Name|Type|Description|
|-|-|-
customParameters|Object|The custom parameters of the ad as a map of the<br />        following form: <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|The ad builder with the specified custom parameters.
&nbsp;|&nbsp;
## <a name="withdescription~string-description~"></a>withDescription(String description)
Sets the description of this new expanded text ad. 

### Arguments:
|Name|Type|Description|
|-|-|-
description|String|The ad description.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|Ad builder with the specified description.
&nbsp;|&nbsp;
## <a name="withfinalurl~string-finalurl~"></a>withFinalUrl(String finalUrl)
Sets the final URL of this new expanded text to the specified value.

### Arguments:
|Name|Type|Description|
|-|-|-
finalUrl|String|The final URL for the ad.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|The ad builder with the specified final URL.
&nbsp;|&nbsp;
## <a name="withheadlinepart1~string-headlinepart1~"></a>withHeadlinePart1(String headlinePart1)
Sets the first part of the headline of this new expanded text ad to the specified value.

### Arguments:
|Name|Type|Description|
|-|-|-
headlinePart1|String|The first part of the headline for the ad.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|Ad builder with the specified first part of the headline.
&nbsp;|&nbsp;
## <a name="withheadlinepart2~string-headlinepart2~"></a>withHeadlinePart2(String headlinePart2)
Sets the second part of the headline of this new expanded text ad to the specified value.

### Arguments:
|Name|Type|Description|
|-|-|-
headlinePart2|String|The second part of the headline for the ad.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|Ad builder with the specified second part of the headline.
&nbsp;|&nbsp;
## <a name="withmobilefinalurl~string-mobilefinalurl~"></a>withMobileFinalUrl(String mobileFinalUrl)
Sets the mobile final URL of this new expanded text ad to the specified value.

### Arguments:
|Name|Type|Description|
|-|-|-
mobileFinalUrl|String|The mobile final URL for the ad.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|The ad builder with the specified final URL.
&nbsp;|&nbsp;
## <a name="withpath1~string-path1~"></a>withPath1(String path1)
Sets the first path of the display URL of this new expanded text ad to the specified value.

### Arguments:
|Name|Type|Description|
|-|-|-
urlPath1|String|The text of the first path.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[ExpandedTextAdBuilder](ExpandedTextAdBuilder)|Ad builder with the specified first URL path.
&nbsp;|&nbsp;
## <a name="withpath2~string-path2~"></a>withPath2(String path2)
Sets the second path of the display URL of this new expanded text ad to the specified value.

### Arguments:
|Name|Type|Description|
|-|-|-
urlPath2|String|The text of the second path.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|Ad builder with the specified second URL path.
&nbsp;|&nbsp;
## <a name="withtrackingtemplate~string-trackingtemplate~"></a>withTrackingTemplate(String trackingTemplate)
Sets the tracking template of this new expanded text ad to the specified value.

### Arguments:
|Name|Type|Description|
|-|-|-
trackingTemplate|String|The tracking template for the ad.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|The ad builder with the specified tracking template.
&nbsp;|&nbsp;
