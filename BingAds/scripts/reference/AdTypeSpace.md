# AdTypeSpace
Provides information about the type of an ad. Use [Ad.getType](./Ad#getType) for ad types that are not fully supported.      

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
[expandedTextAd](#expandedtextad)|boolean|Returns true if this ad is an ExpandedTextAd. <br />
&nbsp;|&nbsp;|&nbsp;

## <a name="expandedtextad"></a>expandedTextAd
Returns true if this ad is an ExpandedTextAd. 

### Returns:
|Type|Description|
|-|-
boolean|Whether the ad is an ExpandedTextAd.
&nbsp;|&nbsp;
