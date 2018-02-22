# AdViewSpace
Provides the methods used to convert the base ad object to other ad types such as an enhanced text ad object.
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
