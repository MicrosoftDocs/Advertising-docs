# AdGroupOperation
Represents the definition of an ad group constructed via [AdGroupBuilder](./AdGroupBuilder). The ad group is only stored in the system when any of the methods on this object are invoked or when the script finishes execution, whichever comes first. For more efficiency, store the operation objects in an array and only invoke its methods when all operations have been constructed.

|Method|Return Type|Description|
|-|-|-
getErrors|String[]|Returns an empty array if the ad group was successfully created, otherwise returns the errors encountered during the execution of this operation.<br />
getResult|[AdGroup](./AdGroup)|Returns the newly created <br />
isSuccessful|boolean|Returns <br />
