# AdOperation
Represents the definition of an ad constructed via [AdBuilderSpace](./AdBuilderSpace). The ad is only stored in the system when any of the methods on this object are invoked or when the script finishes execution, whichever comes first. For more efficiency, store the operation objects in an array and only invoke its methods when all operations have been constructed. 

|Method|Return Type|Description|
|-|-|-
[getErrors]('#geterrors')|String[]|Returns an empty array if the ad was successfully created, otherwise returns the errors encountered during the execution of this operation.<br />
[getResult]('#getresult')|[Ad](./Ad)|Returns the newly created Ad, otherwise returns null if this operation failed to execute.<br />
[isSuccessful]('#issuccessful')|boolean|Returns <br />

## <a name="geterrors"></a>getErrors
Returns an empty array if the ad was successfully created, otherwise returns the errors encountered during the execution of this operation.


## <a name="getresult"></a>getResult
Returns the newly created Ad, otherwise returns null if this operation failed to execute.


## <a name="issuccessful"></a>isSuccessful
Returns 


