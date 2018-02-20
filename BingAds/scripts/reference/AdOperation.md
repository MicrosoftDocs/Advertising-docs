# AdOperation
Represents the definition of an ad constructed via [AdBuilderSpace](./AdBuilderSpace). The ad is only stored in the system when any of the methods on this object are invoked or when the script finishes execution, whichever comes first. For more efficiency, store the operation objects in an array and only invoke its methods when all operations have been constructed. 

Example usage:
```javascript
 // For the purpose of this example, suppose that the fetchAdText() function
 // fetches text ad data from your data source of choice, so that
 // adsToCreate is an array where each element is an object describing an ad.
 var adgroup = BingAdsApp.adGroups().get().next();
 var adsToCreate = fetchAdText();
 var adOps = [];
 for (var i = 0; i < adsToCreate.length; i++) {
     adOps.push(
         adGroup.newAd().expandedTextAdBuilder()
             .withHeadlinePart1(adsToCreate[i].headlinePart1)
             .withHeadlinePart2(adsToCreate[i].headlinePart2)
             .withDescription(adsToCreate[i].description)
             .withPath1(adsToCreate[i].path1)
             .withPath2(adsToCreate[i].path2)
             .withFinalUrl(adsToCreate[i].finalUrl)
             .build());
 }
 for (var i = 0; i < adOps.length; i++) {
   if (adOps[i].isSuccessful()) {
     adOps[i].getResult().applyLabel('myLabel');
   } else {
     Logger.log('Errors from Ad [' + adsToCreate[i].headline + ']: '
         + adOps[i].getErrors());
   }
 }
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[getErrors](#geterrors)|String[]|Returns an empty array if the ad was successfully created, otherwise returns the errors encountered during the execution of this operation.<br />
[getResult](#getresult)|[Ad](./Ad)|Returns the newly created Ad, otherwise returns null if this operation failed to execute.<br />
[isSuccessful](#issuccessful)|boolean|Returns <br />
&nbsp;|&nbsp;|&nbsp;

## <a name="geterrors"></a>getErrors
Returns an empty array if the ad was successfully created, otherwise returns the errors encountered during the execution of this operation.


### Returns:
|Type|Description|
|-|-
String[]|The errors that occurred during the AdOperation.
&nbsp;|&nbsp;
## <a name="getresult"></a>getResult
Returns the newly created Ad, otherwise returns null if this operation failed to execute.


### Returns:
|Type|Description|
|-|-
[Ad](./Ad)|The Ad created by the AdOperation.
&nbsp;|&nbsp;
## <a name="issuccessful"></a>isSuccessful
Returns 


### Returns:
|Type|Description|
|-|-
boolean|true if the operation was successful.
&nbsp;|&nbsp;
