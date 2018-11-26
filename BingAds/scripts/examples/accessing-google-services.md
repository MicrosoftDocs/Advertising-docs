---
title: "Using UrlFetchApp to access Google services"
description: "How to use UrlFetchApp to access Google services."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Using UrlFetchApp to access Google services

The [example script](#example-script) in this topic shows you how to use [UrlFetchApp](../reference/UrlFetchApp.md) to:

- Read a file from Google Drive, which contains a single bid multiplier value;
- Read a spreadsheet containing keyword IDs, use the IDs to get the keywords, and multiply the keywords' bids by the bid multiplier;
- Write the new and old bid values back to the spreadsheet.

Before you can run the script, you need to get credentials for accessing your Google resources. There are a couple of options for getting the credentials:

- Option 1 &mdash; Easy to follow and takes less time but you need to repeat it every hour when the access token expires.
- Option 2 &mdash; A little more complicated but doesn't need to be repeated every hour when the access token expires.

## Option 1 - Getting an access token from Google OAuth playground

1. Go to [Google OAuth playground](https://developers.google.com/oauthplayground)
2. In **Input your own scopes**, paste https://www.googleapis.com/auth/drive https://www.googleapis.com/auth/gmail.send
3. Click **Authorize APIs** 
4. After the APIs are authorized, click **Exchange authorization code for tokens**
5. Copy the access_token's value from the response
6. In the [example script](#example-script), set the credentials object's `accessToken` field to the access token copied in step 5.

> [!NOTE]
> Because the access token expires in 1 hour, you'll need to repeat these steps every hour.

## Option 2 - Using a refresh token to get an access token

1. Go to Google developer console API [dashboard](https://console.developers.google.com/apis/dashboard)
2. Click **Select a project** and create a new project (for example, Bing Ads Scripts) or choose an existing project
3. On the project dashboard page, click **ENABLE APIS AND SERVICES**
4. Search for *Sheets* and click **Google Sheets API → Enable**
5. Repeat steps 3 and 4 for Google Drive API
6. Repeat steps 3 and 4 for Gmail API
7. On the project dashboard page, click **Credentials → OAuth** consent screen
8. Enter an Application name (for example, Bing Ads Scripts)
9. Click **Add scope**, select *../auth/drive* and *../auth/gmail.send* and click **ADD**
10. Click **Save**
11. On the Credentials page, click **Create credentials → Oauth Client ID**
12. Choose **Other** application type, enter a name (for example, Bing Ads Scripts Client), and click **Create**
13. Copy your client ID and client secret to use in steps 14 and 15.
14. Create a PowerShell script to get user consent and a refresh token.  
   
  Getting an access token requires user consent unless you have a refresh token. But because Scripts doesn't support UI components, you'll need to get consent another way. This PowerShell provides an option for getting consent and a refresh token.  
   
  Open Notepad or your favorite editor and copy the PowerShell script to the editor. Set `$clientId` and `$clientSecret` to the client ID and secret you received when you registered your app (see step 12).  
   
  ```powershell
  $clientId = "your-client-id"
  $clientSecret = "your-client-secret"
  
  $scopes = "https://www.googleapis.com/auth/drive", "https://www.googleapis.com/auth/gmail.send"
  
  Start-Process "https://accounts.google.com/o/oauth2/v2/auth?client_id=$clientId&scope=$([string]::Join("%20", $scopes))&access_type=offline&response_type=code&redirect_uri=urn:ietf:wg:oauth:2.0:oob"    
   
  $code = Read-Host "Please enter the code"
     
  $response = Invoke-WebRequest https://www.googleapis.com/oauth2/v4/token -ContentType application/x-www-form-urlencoded -Method POST -Body "client_id=$clientid&client_secret=$clientSecret&redirect_uri=urn:ietf:wg:oauth:2.0:oob&code=$code&grant_type=authorization_code"
    
  Write-Output "Refresh token: " ($response.Content | ConvertFrom-Json).refresh_token 
  ```  
   
  Save the file and name it GetTokens.ps1 (you can name it anything you want but the extension must be .ps1).  
   
  Now open a console window. To open a console window on Microsoft Windows, enter the following Windows Run command (\<Windows button>+r):  
   
  ```
  cmd.exe
  ```  
   
  At the command prompt, navigate to the folder where you saved GetTokens.ps1 and enter the following command:  
   
  ```
  powershell.exe -File .\GetTokens.ps1
  ```  
   
  When the PowerShell script successfully runs, it starts a browser session where you enter your Google credentials. After consenting, the browser's address bar contains the grant code (see ?code={copy this code}).  
   
  ```
  https://login.live.com/oauth20_desktop.srf?code=M7ab570e5-a1c0-32e5-a946-e4490c822954&lc=1033
  ```  
   
  Copy the grant code (M7ab570e5-a1c0-32e5-a946-e4490c822954) and enter it in the console window at the prompt. The PowerShell script then returns a refresh token. In the [example script](#example-script), set `refreshToken` to the refresh token that the PowerShell script returned. You should treat the refresh token like you would a password; if someone gets hold of it, they have access to your resources.  
   
  The refresh token is long lived but it can become invalid. If you receive an invalid_grant error, your refresh token is no longer valid and you'll need to run the PowerShell script again to get consent and a new refresh token.  
  
15. In the [example script](#example-script), set the credentials object's `clientId`, `clientSecret`, and `refreshToken` fields to the values you received in steps 12 and 14.


## Example script

```javascript
function main() {

  // Set these fields based on the option you chose for getting an access token.
  const credentials = {
    accessToken: '',
    clientId: 'your-client-id',
    clientSecret: 'your-client-secret',
    refreshToken: 'your-refresh-token'
  };
 
  // To get a fileId or spreadsheetId, please see
  // https://developers.google.com/sheets/api/guides/concepts#spreadsheet_id.
 
  // The file must contain a single bid multipler value (for example,1.1),
  // which is used to update keyword bids.
  const fileId = 'your-file-id';
 
  // The spreadsheet must contain 3 valid keyword IDs in cells A2, A3, and A4.
  const spreadsheetId = 'your-spreadsheet-id';

  // The email address to send a notification email to at the end of the script.
  const notificationEmail = 'your-notification-email';
 
  var driveApi = GoogleApis.createDriveService(credentials);
 
  // Read bid multiplier from the file.
  // Reference: https://developers.google.com/drive/api/v3/reference/files/export
  var bidMultiplier = driveApi.files.export({ fileId: fileId, mimeType: 'text/plain' }).body;
 
  Logger.log(`read bid multiplier ${bidMultiplier}`);
 
  var sheetsApi = GoogleApis.createSheetsService(credentials);
 
  // Read keyword IDs from the spreadsheet.
  // Reference: https://developers.google.com/sheets/api/reference/rest/v4/spreadsheets.values/get
  // A1 notation documentation: https://developers.google.com/sheets/api/guides/concepts#a1_notation
  var keywordIds = sheetsApi.spreadsheets.values.get({
    spreadsheetId: spreadsheetId,
    range: 'A2:A4'
  }).result.values.map(x => x[0]);
 
  Logger.log(`read ${keywordIds.length} keyword ids`);
 
  // Fetch keywords by IDs.
  var keywords = BingAdsApp.keywords().withIds(keywordIds).get();
 
  var oldBids = [];
  var newBids = [];
 
  // Update keyword bids, save the old and new bid values into arrays.
  while (keywords.hasNext()) {
    var kw = keywords.next();
 
    var oldBid = kw.bidding().getCpc();
 
    var newBid = oldBid * bidMultiplier;
 
    oldBids.push(oldBid);
    newBids.push(newBid);
 
    kw.bidding().setCpc(newBid);
  }
 
  // Write the old and new bid values back to the spreadsheet.
  // Reference: https://developers.google.com/sheets/api/reference/rest/v4/spreadsheets.values/batchUpdate
  var updateResponse = sheetsApi.spreadsheets.values.batchUpdate({ spreadsheetId: spreadsheetId }, {
    data: [
      { range: 'B2:B4', values: oldBids.map(x => [x]) },
      { range: 'C2:C4', values: newBids.map(x => [x]) }
    ],
    valueInputOption: 'USER_ENTERED'
  });
 
  Logger.log(`updated ${updateResponse.result.totalUpdatedCells} cells`);
 
  var gmailApi = GoogleApis.createGmailService(credentials);  
 
  var email = [
    `To: ${notificationEmail}`,
    'Subject: Google Services script',
    '',
    `You script ran successfully ✓ and updated ${updateResponse.result.totalUpdatedCells} cells.`
  ].join('\n');
 
  // Send the notification email.
  // Reference: https://developers.google.com/gmail/api/v1/reference/users/messages/send
  var sendResponse = gmailApi.users.messages.send({ userId: 'me' }, { raw: Base64.encode(email) });
 
  Logger.log(`sent email thread ${sendResponse.result.threadId}`);
}
 
var GoogleApis;
(function (GoogleApis) {
  function createSheetsService(credentials) {
    return createService("https://sheets.googleapis.com/$discovery/rest?version=v4", credentials);
  }
  GoogleApis.createSheetsService = createSheetsService;
 
  function createDriveService(credentials) {
    return createService("https://www.googleapis.com/discovery/v1/apis/drive/v3/rest", credentials);
  }
  GoogleApis.createDriveService = createDriveService;
 
  function createGmailService(credentials) {
    return createService("https://www.googleapis.com/discovery/v1/apis/gmail/v1/rest", credentials);
  }
  GoogleApis.createGmailService = createGmailService;
 
  //Creation logic based on https://developers.google.com/discovery/v1/using#usage-simple
  function createService(url, credentials) {
    var content = UrlFetchApp.fetch(url).getContentText();
    var discovery = JSON.parse(content);
    var baseUrl = discovery['rootUrl'] + discovery['servicePath'];
    var accessToken = getAccessToken(credentials);
    var service = build(discovery, {}, baseUrl, accessToken);
    return service;
  }
 
  function createNewMethod(method, baseUrl, accessToken) {
    return (urlParams, body) => {
      var urlPath = method.path;
      var queryArguments = [];
      for (var name in urlParams) {
        var paramConfg = method.parameters[name];
        if (!paramConfg) {
          throw `Unexpected url parameter ${name}`;
        }
        switch (paramConfg.location) {
          case 'path':
            urlPath = urlPath.replace('{' + name + '}', urlParams[name]);
            break;
          case 'query':
            queryArguments.push(`${name}=${urlParams[name]}`);
            break;
          default:
            throw `Unknown location ${paramConfg.location} for url parameter ${name}`;
        }
      }
      var url = baseUrl + urlPath;
      if (queryArguments.length > 0) {
        url += '?' + queryArguments.join('&');
      }
      var httpResponse = UrlFetchApp.fetch(url, { contentType: 'application/json', method: method.httpMethod, payload: JSON.stringify(body), headers: { Authorization: `Bearer ${accessToken}` }, muteHttpExceptions: true });
      var responseContent = httpResponse.getContentText();
      var responseCode = httpResponse.getResponseCode();
      var parsedResult;
      try {
        parsedResult = JSON.parse(responseContent);
      } catch (e) {
        parsedResult = false;
      }
      var response = new Response(parsedResult, responseContent, responseCode);
      if (responseCode >= 200 && responseCode <= 299) {
        return response;
      }
      throw response;
    }
  }
 
  function Response(result, body, status) {
    this.result = result;
    this.body = body;
    this.status = status;
  }
  Response.prototype.toString = function () {
    return this.body;
  }
 
  function build(discovery, collection, baseUrl, accessToken) {
    for (var name in discovery.resources) {
      var resource = discovery.resources[name];
      collection[name] = build(resource, {}, baseUrl, accessToken);
    }
    for (var name in discovery.methods) {
      var method = discovery.methods[name];
      collection[name] = createNewMethod(method, baseUrl, accessToken);
    }
    return collection;
  }
 
  function getAccessToken(credentials) {
    if (credentials.accessToken) {
      return credentials.accessToken;
    }
    var tokenResponse = UrlFetchApp.fetch('https://www.googleapis.com/oauth2/v4/token', { method: 'post', contentType: 'application/x-www-form-urlencoded', payload: { client_id: credentials.clientId, client_secret: credentials.clientSecret, refresh_token: credentials.refreshToken, grant_type: 'refresh_token' } });
    var accessToken = JSON.parse(tokenResponse.getContentText())['access_token'];
    return accessToken;
  }
})(GoogleApis || (GoogleApis = {}));
 
// Base64 implementation from https://github.com/AzureAD/microsoft-authentication-library-for-js/blob/master/lib/msal-core/src/Utils.ts
class Base64 {
  static encode(input) {
    const keyStr = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/=";
    let output = "";
    let chr1, chr2, chr3, enc1, enc2, enc3, enc4;
    var i = 0;
    input = this.utf8Encode(input);
    while (i < input.length) {
      chr1 = input.charCodeAt(i++);
      chr2 = input.charCodeAt(i++);
      chr3 = input.charCodeAt(i++);
      enc1 = chr1 >> 2;
      enc2 = ((chr1 & 3) << 4) | (chr2 >> 4);
      enc3 = ((chr2 & 15) << 2) | (chr3 >> 6);
      enc4 = chr3 & 63;
      if (isNaN(chr2)) {
        enc3 = enc4 = 64;
      }
      else if (isNaN(chr3)) {
        enc4 = 64;
      }
      output = output + keyStr.charAt(enc1) + keyStr.charAt(enc2) + keyStr.charAt(enc3) + keyStr.charAt(enc4);
    }
    return output.replace(/\+/g, "-").replace(/\//g, "_").replace(/=+$/, "");
  }
  static utf8Encode(input) {
    input = input.replace(/\r\n/g, "\n");
    var utftext = "";
    for (var n = 0; n < input.length; n++) {
      var c = input.charCodeAt(n);
      if (c < 128) {
        utftext += String.fromCharCode(c);
      }
      else if ((c > 127) && (c < 2048)) {
        utftext += String.fromCharCode((c >> 6) | 192);
        utftext += String.fromCharCode((c & 63) | 128);
      }
      else {
        utftext += String.fromCharCode((c >> 12) | 224);
        utftext += String.fromCharCode(((c >> 6) & 63) | 128);
        utftext += String.fromCharCode((c & 63) | 128);
      }
    }
    return utftext;
  }
}
```