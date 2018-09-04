---
title: "ExecutionResult object"
description: "Contains the methods used to get information about the execution results of the executeInParallel functions."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# ExecutionResult

Contains the methods used to get information about the execution result of the `executeInParallel` function (see [ManagedAccountSelector](./ManagedAccountSelector.md)).


## Methods
|Method Name|Return Type|Description|
|-|-|-
[getCustomerId](#getcustomerid)|String|Gets the customer ID of the owner of the account.
[getError](#geterror)|String|Gets the error that occurred when Bing ran the executeInParallel function.
[getReturnValue](#getreturnvalue)|String|Gets the return value that the executeInParallel function returned.
[getStatus](#getstatus)|String|Gets the status that indicates whether the function succeeded.


## <a name="getcustomerid"></a>getCustomerId
Gets the customer ID of the owner of the account.

### Returns
|Type|Description|
|-|-
String|The customer ID of the owner of the account.


## <a name="geterror"></a>getError
Gets the error that occurred when Bing ran the executeInParallel function.

### Returns
|Type|Description|
|-|-
String|The error that occurred when Bing ran the executeInParallel function. Returns null if there was no error.


## <a name="getreturnvalue"></a>getReturnValue
Gets the return value that the executeInParallel function returned. For details, see [ManagedAccountSelector](./ManagedAccountSelector.md).

### Returns
|Type|Description|
|-|-
String|The return value that the executeInParallel function returned. Returns null if the function did not return a value.


## <a name="getStatus"></a>getStatus
Gets the status that indicates whether the function succeeded.

### Returns
|Type|Description|
|-|-
String|The status that indicates whether the function succeeded. Possible values are:<ul><li>OK &mdash; The function finished successfully.</li><li>ERROR &mdash; An error occurred while executing the function.</li><li>TIMEOUT &mdash; The function failed to complete in the required time.

