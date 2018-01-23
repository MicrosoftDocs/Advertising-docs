# KeywordBuilder
Provides methods for defining and building a keyword.

|Method|Return Type|Description|
|-|-|-
[build]('#build')|[KeywordOperation](./KeywordOperation)|Returns a keyword operation with the defined properties which can later be used to construct the keyword.<br />
[withCpc(double cpc)]('#withCpc-double-cpc)')|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the CPC property set to the specified value.<br />
[withCustomParameters( String customParameters)]('#withCustomParameters--String customParameters)')|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the custom parameters set to the specified value. The custom parameters are in the format: <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.<br />
[withDestinationUrl(String destinationUrl)]('#withDestinationUrl-String-destinationUrl)')|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the destination URL set to the specified value.<br />
[withFinalUrl(String finalUrl)]('#withFinalUrl-String-finalUrl)')|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the final URL set to the specified value.<br />
[withMobileFinalUrl(String mobileFinalUrl)]('#withMobileFinalUrl-String-mobileFinalUrl)')|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the mobile final URL set to the specified value.<br />
[withText(String text)]('#withText-String-text)')|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the text set to the specified value. Setting the text requires specifying the match type as well by means of extra characters as shown below:<br /> <br /> &nbsp;•	kwBuilder.withText("books") - broad match.<br /> &nbsp;•	kwBuilder.withText("\"books\"") - phrase match.<br /> &nbsp;•	kwBuilder.withText("[the origin of species]") - exact match<br />        <br />
[withTrackingTemplate( String trackingTemplate)]('#withTrackingTemplate--String trackingTemplate)')|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the tracking template set to the specified value.<br />

<a name="build"></a>
## build
Returns a keyword operation with the defined properties which can later be used to construct the keyword.


<a name="withCpc-double-cpc)"></a>
## withCpc(double cpc)
Returns a keyword builder with the CPC property set to the specified value.


<a name="withCustomParameters--String customParameters)"></a>
## withCustomParameters( String customParameters)
Returns a keyword builder with the custom parameters set to the specified value. The custom parameters are in the format: <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.


<a name="withDestinationUrl-String-destinationUrl)"></a>
## withDestinationUrl(String destinationUrl)
Returns a keyword builder with the destination URL set to the specified value.


<a name="withFinalUrl-String-finalUrl)"></a>
## withFinalUrl(String finalUrl)
Returns a keyword builder with the final URL set to the specified value.


<a name="withMobileFinalUrl-String-mobileFinalUrl)"></a>
## withMobileFinalUrl(String mobileFinalUrl)
Returns a keyword builder with the mobile final URL set to the specified value.


<a name="withText-String-text)"></a>
## withText(String text)
Returns a keyword builder with the text set to the specified value. Setting the text requires specifying the match type as well by means of extra characters as shown below:<br /> <br /> &nbsp;•	kwBuilder.withText("books") - broad match.<br /> &nbsp;•	kwBuilder.withText("\"books\"") - phrase match.<br /> &nbsp;•	kwBuilder.withText("[the origin of species]") - exact match<br />        


<a name="withTrackingTemplate--String trackingTemplate)"></a>
## withTrackingTemplate( String trackingTemplate)
Returns a keyword builder with the tracking template set to the specified value.


