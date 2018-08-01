---
title: "AdOperation object"
description: "Contains the methods for determining whether the ad was successfully added."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# AdOperation

Contains the methods for determining whether the ad was successfully added. For information about builders, operation objects, and performance considerations, see [What are builders?](../concepts/builders.md)

Because calling any of this object's methods forces Bing to flush the build queue, be sure to read the performance considerations carefully.


Example usage:
```javascript
    if (operation.isSuccessful()) {
        var ad = operation.getResult();
    }
    else {
        for (var error of operation.getErrors()) {
            Logger.log(`${error}\n`);
        }
    }
```


## Methods
|Method Name|Return Type|Description|
|-|-|-
[getErrors](#geterrors)|string[]|Gets any errors that occurred when you added the ad.
[getResult](#getresult)|[AdGroup](./AdGroup.md)|Gets the ad that you added.
[isSuccessful](#issuccessful)|Boolean|Gets a Boolean value that indicates whether the add operation succeeded.

## <a name="geterrors"></a>getErrors
Gets any errors that occurred when you added the ad.

### Returns
|Type|Description|
|-|-
string[]|An array of error codes if the operation failed; otherwise, an empty array. For example, if you forget to specify the final URL, the call returns CampaignServiceInvalidAdDestinationUrl. For a description of these codes, see [Operation error codes](/bingads/guides/operation-error-codes).

## <a name="getresult"></a>getResult
Gets the ad that you added.

### Returns
|Type|Description|
|-|-
[Ad](./Ad.md)|The ad that you created if the operation succeeded; otherwise, null.

## <a name="issuccessful"></a>isSuccessful
Gets a Boolean value that indicates whether the add operation succeeded.

### Returns:
|Type|Description|
|-|-
Boolean|Is **true** if the operation succeeded; otherwise, **false**.

