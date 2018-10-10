---
title: "HTTPResponse object"
description: "Contains the methods for accessing the content you fetched from the web."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# HTTPResponse

Contains the methods for getting the response's payload and status code.


Example usage:
```javascript
function main() {
    var response = UrlFetchApp.fetch('http://microsoft.com');
    Logger.log("payload as a string: " + response.getContentText());
    Logger.log("\nstatus code: " + response.getResponseCode());
}
```


## Methods

|Method Name|Return Type|Description|
|-|-|-
[getContent()](#getcontent)|byte[]|Gets the response's payload as a byte array.
[getContentText()](#getcontenttext)|string|Gets the response's payload as a string.
[getResponseCode()](#getresponsecode)|integer|Gets the response's HTTP status code.


## <a name="getcontent"></a>getContent

Gets the response's payload as a byte array.

### Returns

|Type|Description|
|-|-
byte[]|The response's payload as a byte array.


## <a name="getcontenttext"></a>getContentText

Gets the response's payload as a string.

### Returns

|Type|Description|
|-|-
string|The response's payload as a string. If the payload is a JSON object, use JSON.parse(response.getContentText()) to get the object.


## <a name="getresponsecode"></a>getResponseCode

Gets the response's HTTP status code.

### Returns

|Type|Description|
|-|-
integer|The response's HTTP status code, which indicates the request's success or failure. For example, 200 if the GET request succeeded.

