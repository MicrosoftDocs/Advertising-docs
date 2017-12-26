# AdBuilderSpace
Provides a method to create an ad in an ad group.

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
[expandedTextAdBuilder](#expandedtextadbuilder)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|Returns a new expanded text ad builder object associated with the parent ad group.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="expandedtextadbuilder"></a>expandedTextAdBuilder
Returns a new expanded text ad builder object associated with the parent ad group.

### Returns:
|Type|Description|
|-|-
[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|A new expanded text ad builder associated with the ad group.
&nbsp;|&nbsp;
