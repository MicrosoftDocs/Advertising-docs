# AdBuilderSpace
Provides a method to create an ad in an ad group.

Example usage:
```javascript
 var adOperation = adGroup.newAd().expandedTextAdBuilder()
    .withHeadlinePart1(&quot;First headline of ad&quot;)
    .withHeadlinePart2(&quot;Second headline of ad&quot;)
    .withDescription(&quot;Ad description&quot;)
    .withPath1(&quot;path1&quot;)
    .withPath2(&quot;path2&quot;)
    .withFinalUrl(&quot;http://www.example.com&quot;)
    .build();
 var ad = adOperation.getResult();
```

|Method|Return Type|Description|
|-|-|-
[expandedTextAdBuilder](#expandedtextadbuilder)|[ExpandedTextAdBuilder](./ExpandedTextAdBuilder)|Returns a new expanded text ad builder object associated with the parent ad group.<br />

## <a name="expandedtextadbuilder"></a>expandedTextAdBuilder
Returns a new expanded text ad builder object associated with the parent ad group.


