# KeywordBuilder
Provides methods for defining and building a keyword.

|Method|Return Type|Description|
|-|-|-
build|[KeywordOperation](./KeywordOperation)|Returns a keyword operation with the defined properties which can later be used to construct the keyword.<br />
withCpc(double cpc)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the CPC property set to the specified value.<br />
withCustomParameters( String customParameters)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the custom parameters set to the specified value. The custom parameters are in the format: <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.<br />
withDestinationUrl(String destinationUrl)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the destination URL set to the specified value.<br />
withFinalUrl(String finalUrl)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the final URL set to the specified value.<br />
withMobileFinalUrl(String mobileFinalUrl)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the mobile final URL set to the specified value.<br />
withText(String text)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the text set to the specified value. Setting the text requires specifying the match type as well by means of extra characters as shown below:<br /> <br /> &nbsp;•	kwBuilder.withText("books") - broad match.<br /> &nbsp;•	kwBuilder.withText("\"books\"") - phrase match.<br /> &nbsp;•	kwBuilder.withText("[the origin of species]") - exact match<br />        <br />
withTrackingTemplate( String trackingTemplate)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the tracking template set to the specified value.<br />
