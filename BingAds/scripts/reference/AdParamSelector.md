# AdParamSelector
Provides methods to select ad params by using filtering and sorting.

Example usage:
```javascript
 var adParamSelector = BingAdsApp.adParams();

 var adParamIterator = adParamSelector.get();
 while (adParamIterator.hasNext()) {
   var adParam = adParamIterator.next();
 }
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[get](#get)|[AdParamIterator](./AdParamIterator)|Returns an iterator indexing the ad params in this selector.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="get"></a>get
Returns an iterator indexing the ad params in this selector.


### Returns:
|Type|Description|
|-|-
[AdParamIterator](./AdParamIterator)|Iterator of the requested ad params.
&nbsp;|&nbsp;
