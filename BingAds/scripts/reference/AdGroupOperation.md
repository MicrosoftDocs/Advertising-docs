# AdGroupOperation
Represents the definition of an ad group constructed via [AdGroupBuilder](./AdGroupBuilder). The ad group is only stored in the system when any of the methods on this object are invoked or when the script finishes execution, whichever comes first. For more efficiency, store the operation objects in an array and only invoke its methods when all operations have been constructed.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[getErrors](#geterrors)|String[]|Returns an empty array if the ad group was successfully created, otherwise returns the errors encountered during the execution of this operation.<br />
[getResult](#getresult)|[AdGroup](./AdGroup)|Returns the newly created `AdGroup`, otherwise returns `null` if this operation failed to execute.<br />
[isSuccessful](#issuccessful)|boolean|Returns <br />
&nbsp;|&nbsp;|&nbsp;

## <a name="geterrors"></a>getErrors
Returns an empty array if the ad group was successfully created, otherwise returns the errors encountered during the execution of this operation.


### Returns:
|Type|Description|
|-|-
String[]|The errors that occurred during the AdGroupOperation.
&nbsp;|&nbsp;
## <a name="getresult"></a>getResult
Returns the newly created `AdGroup`, otherwise returns `null` if this operation failed to execute.<br />

### Returns:
|Type|Description|
|-|-
[AdGroup](./AdGroup)|The AdGroup created by the AdGroupOperation.
&nbsp;|&nbsp;
## <a name="issuccessful"></a>isSuccessful
Returns 


### Returns:
|Type|Description|
|-|-
boolean|true if the operation was successful.
&nbsp;|&nbsp;
