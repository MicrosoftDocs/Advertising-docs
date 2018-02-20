# AdViewSpace
Provides a type-specific view of an ad. 

Example usage:
```javascript
 if (ad.isType().expandedTextAd()) {
   var expandedTextAd = ad.asType().expandedTextAd();
   var headlinePart1 = expandedTextAd.getHeadlinePart1();
 }
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[expandedTextAd](#expandedtextad)|[ExpandedTextAd](./ExpandedTextAd)|Returns this ad as an [ExpandedTextAd](./ExpandedTextAd).<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="expandedtextad"></a>expandedTextAd
Returns this ad as an [ExpandedTextAd](./ExpandedTextAd).


### Returns:
|Type|Description|
|-|-
[ExpandedTextAd](./ExpandedTextAd)|The ad as an ExpandedTextAd.
&nbsp;|&nbsp;
