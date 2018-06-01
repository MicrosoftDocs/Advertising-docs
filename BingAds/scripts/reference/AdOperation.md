# AdOperation
Represents the definition of an ad. The ad is added to the campaign only when one of this object's methods is invoked or when the script finishes execution, whichever comes first. To improve performance, store the operation objects in an array and only invoke its methods when all operations have been constructed.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[getErrors](#geterrors)|String[]|Returns an empty array if the ad is successfully created; otherwise, it contains the list of errors.
[getResult](#getresult)|[AdGroup](./AdGroup)|Returns the newly created ad, otherwise returns null if this operation failed to execute.
[isSuccessful](#issuccessful)|Boolean|Returns a Boolean value that indicates if this operation was successful.

## <a name="geterrors"></a>getErrors
Returns an empty array if the ad is successfully created; otherwise, it contains the list of errors.

### Returns:
|Type|Description|
|-|-
String[]|An empty array if the ad is successfully created; otherwise, it contains the list of errors.

## <a name="getresult"></a>getResult
Returns the newly created ad, otherwise returns null if this operation failed to execute.

### Returns:
|Type|Description|
|-|-
[AdGroup](./AdGroup)|Newly created ad, otherwise returns null if this operation failed to execute.

## <a name="issuccessful"></a>isSuccessful
Returns a Boolean value that indicates if this operation was successful.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this operation was successful.

