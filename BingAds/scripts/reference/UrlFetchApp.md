---
title: "UrlFetchApp object"
description: "The top-level object that you use to fetch resources from the web."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# UrlFetchApp

This is the top-level object that you use to fetch resources from the web.


Example usage:
```javascript
function main() {
    // Simple GET request to fetch a stock quote.
    var response = UrlFetchApp.fetch('https://api.iextrading.com/1.0/stock/msft/quote');
    var stock = JSON.parse(response.getContentText());
    Logger.log(`stock symbol: ${stock["symbol"]}`);
    Logger.log(`company: ${stock["companyName"]}`);
    Logger.log(`close price: ${stock["close"]}`);
    Logger.log("\nstatus code: " + response.getResponseCode());
}
```

```javascript
    // Sends a GET request to a resource that requires an OAuth access token
    // and returns a JSON object in the response.
    var token = "<the oauth token goes here>";
    var response = UrlFetchApp.fetch('https://contoso.com', { headers: { Authorization: `Bearer ${token}` } });    
    var jsonObject = JSON.parse(response.getContentText());    
```

```javascript
    // Sends a POST request with a JSON payload.
    var jsonObject = {
        'id' : '123abc',
        'name' : 'leg',
        'color' : 'red'
    };
    var formData = {
        'method' : 'post',
        'contentType' : 'application/json',
        'payload' : JSON.stringify(jsonObject)
    } 
    var response = UrlFetchApp.fetch('https://contoso.com', formData);    
    var jsonObject = JSON.parse(response.getContentText());    
```


## Methods

|Method Name|Return Type|Description|
|-|-|-
[fetch(url)](#fetch-string-url-)|[HTTPResponse](./HTTPResponse.md)|Gets a resource from the web.
[fetch(url, params)](#fetch-string-url-object-params-)|[HTTPResponse](./HTTPResponse.md)|Lets you manage a web resource.


## <a name="fetch-string-url-"></a>fetch(string url)
Gets a resource from the web. 

This is the equivalent of an HTTP GET request. This method waits until the request completes.

### Arguments
|Name|Type|Description|
|-|-|-
url|string|The URL of the web resource to get. Supports HTTP and HTTPS requests. The URL may include query parameters.

### Returns
|Type|Description|
|-|-
[HTTPResponse](HTTPResponse.md)|Contains the methods for getting the response's payload and status code.


## <a name="fetch-string-url-object-params-"></a>fetch(string url, object params)
Lets you manage a web resource.

You can use this method to get, post, put, patch or delete a web resource. This method waits until the request completes.

### Arguments
|Name|Type|Description|
|-|-|-
url|string|The URL of the web resource.
params|object|A form-data object that contains one or more of the following name-value pairs:<ul><li>contentType &mdash; A string that contains the media type of data in the request's payload. The default is, application/x-www-form-urlencoded.</li><li>headers &mdash; An object that contains a key-value pair for each request header you want to specify.</li><li>method &mdash; A string that contains the HTTP verb to use in the request. Possible values are: GET, POST, PUT, PATCH, and DELETE. The default is GET.</li><li>payload &mdash; The payload for a POST, PUT, or PATCH request. The payload can be a string or an object. If the payload is an object, it may contain one or more name-value pairs.</li><li>muteHttpExceptions &mdash; A Boolean value that determines whether to prevent this method from throwing an exception if the response's status code is a failure code. Set to **true** to mute HTTP failure codes. The default is **false**.</li></ul>

### Returns
|Type|Description|
|-|-
[HTTPResponse](HTTPResponse.md)|Contains the methods for getting the response's payload and status code.


## See also

- [UrlFetch limits](../concepts/urlfetch-limits.md)