# KeywordOperation
Represents the definition of a keyword constructed via [KeywordBuilder](./KeywordBuilder). The keyword is only stored in the system when any of the methods on this object are invoked or when the script finishes execution, whichever comes first. For more efficiency, store the operation objects in an array and only invoke its methods when all operations have been constructed.

|Method|Return Type|Description|
|-|-|-
[getErrors]('#getErrors')|String[]|Returns an empty array if the keyword was successfully created, otherwise returns the errors encountered during the execution of this operation.<br />
[getResult]('#getResult')|[Keyword](./Keyword)|Returns the newly created Keyword, otherwise returns null if this operation failed to execute.<br />
[isSuccessful]('#isSuccessful')|boolean|Returns <br />

<a name="#getErrors"></a>
## getErrors
Returns an empty array if the keyword was successfully created, otherwise returns the errors encountered during the execution of this operation.


<a name="#getResult"></a>
## getResult
Returns the newly created Keyword, otherwise returns null if this operation failed to execute.


<a name="#isSuccessful"></a>
## isSuccessful
Returns 


