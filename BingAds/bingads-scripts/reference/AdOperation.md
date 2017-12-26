# AdOperation
Represents the definition of an ad constructed via [AdBuilderSpace](./AdBuilderSpace). The ad is only stored in the system when any of the methods on this object are invoked or when the script finishes execution, whichever comes first. For more efficiency, store the operation objects in an array and only invoke its methods when all operations have been constructed. 

|Method|Return Type|Description|
|-|-|-
getErrors|String[]|Returns an empty array if the ad was successfully created, otherwise returns the errors encountered during the execution of this operation.<br />
getResult|[Ad](./Ad)|Returns the newly created Ad, otherwise returns null if this operation failed to execute.<br />
isSuccessful|boolean|Returns <br />
