---
title: "Using UrlFetchApp to fetch resources from the web"
description: "Use UrlFetchApp's methods to GET, POST, PUT, and DELETE web resources."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Fetching resources from the web

If you need to manage resources on the web, use the the following methods of [UrlFetchApp](../reference/UrlFetchApp.md).

- [fetch(url)](../reference/UrlFetchApp.md#fetch-string-url-)
- [fetch(url, params)](../reference/UrlFetchApp.md#fetch-string-url-urlfetchparams-params-)

### Simple GET request

Use `fetch(url)` if you just need to get a web resource.

```javascript
    var response = UrlFetchApp.fetch('https://api.iextrading.com/1.0/stock/msft/quote');
```

The `fetch(url)` method returns an [HTTResponse](../reference/HTTPResponse.md) object, which has the methods for reading the response. Use the `getContentText` method for reading a text response and `getContent` for reading a binary response.

For the stock quote request above, use `getContentText` to get the JSON response. To acces the individual fields in the JSON response, use the `JSON.parse()` method to parse the response.

```javascript
    var stock = JSON.parse(response.getContentText());
    Logger.log(`stock symbol: ${stock["symbol"]}`);
    Logger.log(`company: ${stock["companyName"]}`);
    Logger.log(`close price: ${stock["close"]}`);
```

### Handling HTTP errors

If the request fails (for example, with 400 Bad request), the service stops processing your script and writes an error message to the log. The message includes the request's HTTP status code but not the error message that might be in the body of the response. 

If you need to get the response body, call the `fetch(url, params)` method instead and set the muteHttpExceptions parameter to **true**. Setting muteHttpExceptions to **true** always returns control to your script. You'll then need to call the `getResponseCode()` method to determine the success or failure of the request and act accordingly.

```javascript
    var response = UrlFetchApp.fetch('https://contoso.com', { muteHttpExceptions: true });    

    if (200 == response.getResponseCode())
    {
        Logger.log('HTTP request succeeded');
    }
    else
    {
        Logger.log('HTTP request failed');
    }
```

### Adding, updating, or deleting a web resource

If you need to add, update, or delete a web resource, use the [fetch(url, params)](../reference/UrlFetchApp.md#fetch-string-url-urlfetchparams-params-) method. This method lets you specify the HTTP verb to use, the Content-Type header, any other headers your request needs, and the request's payload. For details about these parameters, see the [UrlFetchParams](../reference/UrlFetchParams.md) object.

The following example gets a resource that requires an OAuth access token. Because GET is the fetch method's default HTTP verb, the only parameter you need to specify is the `headers` parameter.


```javascript
    var token = "<the oauth token goes here>";
    var response = UrlFetchApp.fetch('https://contoso.com', { headers: { Authorization: `Bearer ${token}` } });    
    var jsonObject = JSON.parse(response.getContentText());    
```

This example sends a POST request with a JSON payload. Because the payload is a JSON object, the example sets the `contentType` parameter to *application/json*.

```javascript
    var myData = {
        'id' : '123abc',
        'name' : 'leg',
        'color' : 'red'
    };

    var options = {
        'method' : 'post',
        'contentType' : 'application/json',
        'payload' : JSON.stringify(myData)
    };

    var response = UrlFetchApp.fetch('https://contoso.com', options);    
    var jsonObject = JSON.parse(response.getContentText());    
```

## Using UrlFetchApp to get a data file or CSV file from OneDrive.

There are a couple of options for using [UrlFetchApp](../reference/UrlFetchApp.md) to get a data from OneDrive.

### Option 1 uses a OneDrive download link

Option 1 uses a link to download the data file from your OneDrive Live account (i.e., https://onedrive.live.com). This option is easier but it's undocumented, so this functionality is subject to change without notice.

To get the link:

- Select the data file in OneDrive
- Click Embed
- Copy the snippet to an editor (e.g., Notepad)
- In the URL, change /embed to /download
- Copy and use the URL in your script's `fetch` method.

After getting the URL, call the `fetch(url)` method to download the data file. You can then parse the file.

```javascript
function main() {
    var response = UrlFetchApp.fetch("https://onedrive.live.com/download?cid=659E...&resid=659E...&authkey=AC5z...");
 
    var sheet = response.getContentText();
}
```

### Option 2 uses Microsoft Graph to get a OneDrive download link

Option 2 uses Microsoft Graph to get a OneDrive download link. With this option you need an OAuth access token to access the data file. Getting an access token requires user consent unless you have a refresh token. But because Scripts doesn't support UI components, you'll need to get consent another way. You can either write a simple app or use a web browser.

If you want to write a simple console app that you can reuse to get a refresh token, see the Code Grant Flow process outlined in [Authentication with OAuth](/bingads/guides/authentication-oauth). For an example of a simple console app that gets OAuth tokens, see [OAuth C# Example](../../hotel-service/code-example-oauth.md). Note that for the step that gets the grant code, set the &scope query parameter to 'file.read offline_access'.

Use your simple app to get the refresh token for a user that has permissions to access your data file. You will run your simple app just once to get the refresh token. After getting the refresh token, you'll use the refresh token in your script to get the access token. The refresh token is long lived but it can become invalid. If you receive an invalid_grant error, your refresh token is no longer valid and you'll need to run your app again to get consent and a new refresh token.

#### If writing a simple app isn't an option

If writing a simple app isn't an option but you know how to use [Fiddler](https://www.telerik.com/download/fiddler) or a comparable tool, follow these steps to get a refresh token.

1. Go to [https://apps.dev.microsoft.com](https://apps.dev.microsoft.com) and click **Add an app**.  
   
   1. Enter an app like Bing Ads Scripts app.  (Don't check Guided setup.)
   2. Click **Create** and note your application ID (client ID).  
   3. Click **Add Platform** and then **Native Application**.
   4. Under **Microsoft Graph delegated permissions**, click **Add** and select Files.Read and offline_access.  
   5. Click **Save**.  
   
2. Enter the following URL in a web browser. Replace {clientid} with the application ID you received when you registered your app. The browser opens an MSA window and asks for your user name and password. It then asks for consent to access your OneDrive resources, click Yes.  
  
   ```https://login.microsoftonline.com/common/oauth2/v2.0/authorize?client_id={clientid}&scope=files.read offline_access&response_type=code&redirect_uri=https://login.live.com/oauth20_desktop.srf```  

3. Capture the code that the response returns in the address bar (see ?code={copy this code}) to use in the next step.  

4. Open Fiddler or a comparable tool and execute the following HTTP POST request. Replace {clientid} with the client ID you received when you registered your app. Replace {grantcode} with the code you captured in the previous step.  
   
   ```
   POST https://login.microsoftonline.com/common/oauth2/v2.0/token
   Content-Type: application/x-www-form-urlencoded  
   
   client_id={clientid}&redirect_uri=https://login.live.com/oauth20_desktop.srf&code={grantcode}&grant_type=authorization_code
   ```  

5. Inspect the response and copy the refresh token to use in the script. You should treat the refresh token like you would a password; if someone gets hold of it, they have access to your OneDrive data.
   


#### Example that downloads a CSV file

After getting the refresh token, the following example shows how to 1) use the refresh token to get an access token, and 2) call Microsoft Graph to get a download URL that you use to download the CSV file. Replace {yourclientid} with your simple app's client ID, and replace {yourrefreshtoken} with your refresh token.

```javascript
function main() {
    var options = {
        'method' : 'post',
        'contentType' : 'application/x-www-form-urlencoded',
        'payload' : 'client_id={yourclientid}&redirect_uri=https://login.live.com/oauth20_desktop.srf&refresh_token={yourrefreshtoken}&grant_type=refresh_token'
    };
    
    // Use the refresh token to get the access token.

    var response = UrlFetchApp.fetch('https://login.microsoftonline.com/common/oauth2/v2.0/token', options);
 
    var tokens = JSON.parse(response.getContentText());

    Logger.log("access token: \n\n" + tokens['access_token']);
    Logger.log("\n\nrefresh token: \n\n" + tokens['refresh_token']);

    // Get the CSV file from OneDrive passing the access token in the Authorization header. 
    // Replace the path and file name (/me/drive/root/children/bids.csv) with your path and file name.

    response = UrlFetchApp.fetch('https://graph.microsoft.com/v1.0/me/drive/root/children/bids.csv', { headers: { Authorization: `Bearer ${tokens['access_token']}` } });    
 
    // Get the download URL from the response that you use to download the file.

    var downloadUrl = JSON.parse(response.getContentText())['@microsoft.graph.downloadUrl'];    
 
    // Download the file and parse the data. The parseCSV method is a placeholder for 
    // whichever method you provide to parse the file.

    response = UrlFetchApp.fetch(downloadUrl);
    var file = response.getContentText();
    var data = parseCSV(file);
}
```



### Parse the spreadsheet

There's no built-in CSV parsing tool, so you'll need to write your own or find one online. For example, a quick search online found [this](https://stackoverflow.com/a/14991797) one on Stack Overflow. If you find one online make sure it has no use restrictions. 
