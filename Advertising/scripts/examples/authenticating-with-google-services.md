---
title: "Authenticating with Google services"
description: "Shows options for getting an access token to use with Google services."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bing-ads-scripts"
ms.topic: "article"
---

# Authenticating with Google services

If your script uses Google services, such as Google Drive, Sheets, and Mail, you'll need credentials to run them. 

For information about getting credentials, see the following Google documents:

- [Using OAuth 2.0 to Access Google APIs](https://developers.google.com/identity/protocols/OAuth2)
- [Setting up OAuth 2.0](https://support.google.com/cloud/answer/6158849?hl=en)


## <a name="option1"></a>Getting an access token from Google OAuth playground

> [!NOTE]
> The following steps may change as Google updates their user experience (UX). In the case that the steps no longer align with the UX, read the Google docs mentioned at the beginning of the topic to determine the new flow, or simply navigate the UX looking for similar steps.

If you just want to get a short-lived access token to run or test a script, follows these steps:

1. Go to [Google OAuth playground](https://developers.google.com/oauthplayground)
2. In **Input your own scopes**, paste https:\//www.googleapis.com/auth/drive https:\//www.googleapis.com/auth/gmail.send
3. Click **Authorize APIs** 
4. After the APIs are authorized, click **Exchange authorization code for tokens**
5. Copy the access_token's value from the response
6. In solutions like [Discovering disapproved ads](../solutions/get-disapproved-ads.md), which access Google services, set the credentials object's `accessToken` field to the access token copied in step 5.

> [!NOTE]
> Because the access token expires in 1 hour, you'll need to repeat these steps every hour.


## <a name="option2"></a>Getting a refresh token from Google OAuth playground

The longer-lived solution is to get a refresh token from the playground after defining a web client in Google Cloud Platform Console. See [Setting up OAuth 2.0](https://support.google.com/cloud/answer/6158849?hl=en). 

Additional information:

- To use the example [solutions](../solutions/index.md) in this document, you must enable APIs and services for Google Sheets API, Google Drive API, and Gmail API.  
  
- When asked to add scopes, select *../auth/drive* and *../auth/gmail.send*. **Selecting these scopes require that you submit your app for Google verification**. If you don't submit your app for Google verification, you'll get a warning message when trying to authorize the app.  
  
- When asked to specify the type of application, select Web application.  
  
- When asked to specify a redirect URI, use https://developers.google.com/oauthplayground.  
  
- After setting up your credentials and defining your client, copy the client ID and client secret to use in steps 4 and 5 below.

> [!NOTE]
> If you don't submit your app for Google verification and try authorizing it in the playground, Google displays a warning dialog that says, "This app isn't verified." To run the script anyway, click **Advanced** and then **Go to [app name] (unsafe)**.

> [!NOTE]
> The following steps may change as Google updates their user experience (UX). In the case that the steps no longer align with the UX, read the Google docs mentioned at the beginning of the topic to determine the new flow, or simply navigate the UX looking for similar steps.
 
1. Go to [Google OAuth playground](https://developers.google.com/oauthplayground)
2. Click the OAuth 2.0 Configuration icon (looks like a gear in upper right corner)
3. Check the **Use your own OAuth credentials** box
4. Paste your client ID into **OAuth Client ID**
5. Paste your client secret into **OAuth Client secret**
6. In **Input your own scopes**, paste https:\//www.googleapis.com/auth/drive https:\//www.googleapis.com/auth/gmail.send
7. Click **Authorize APIs** and follow the prompts to provide consent 
8. After the APIs are authorized, click **Exchange authorization code for tokens**
9. Copy the token from **Refresh token** to use in step 10 
10. In solutions like [Discovering disapproved ads](../solutions/get-disapproved-ads.md), which access Google services, set the credentials object's `clientId`, `clientSecret`, and `refreshToken` fields to the values from 4, 5, and 9. 

You only need to repeat this process if the refresh token becomes invalid.


## <a name="option3"></a>Getting a refresh token using a PowerShell script

Another longer-lived solution is to get a refresh token from the playground after defining a client in Google Cloud Platform Console. See [Setting up OAuth 2.0](https://support.google.com/cloud/answer/6158849?hl=en). 

Additional information:

- To use the example [solutions](../solutions/index.md) in this document, you must enable APIs and services for Google Sheets API, Google Drive API, and Gmail API.  
  
- When asked to add scopes, select *../auth/drive* and *../auth/gmail.send*. **Selecting these scopes require that you submit your app for Google verification**. If you don't submit your app for Google verification, you'll get a warning message when trying to authorizing the app.  
  
- When asked to specify the type of application, select Other.  
  
- After setting up your credentials and defining your client, copy the client ID and client secret to use in the PowerShell script below.

> [!NOTE]
> If you don't submit your app for Google verification and try authorizing it in the playground, Google displays a warning dialog that says, "This app isn't verified." To run the script anyway, click **Advanced** and then **Go to [app name] (unsafe)**.


### Create the following PowerShell script to get user consent and a refresh token. 


Getting an access token requires user consent unless you have a refresh token. But because Scripts doesn't support UI components, you'll need to get consent another way. This PowerShell provides an option for getting consent and a refresh token. You'll only need to rerun the PowerShell script if the refresh token becomes invalid.

Open Notepad or your favorite editor and copy the PowerShell script to the editor. Set `$clientId` and `$clientSecret` to the client ID and secret you received when you registered your app.  

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

When the PowerShell script successfully runs, it starts a browser session where you enter your Google credentials. After consenting, the webpage contains the grant code (see Please copy this code...).  

Copy the grant code and enter it in the console window at the prompt. The PowerShell script then returns a refresh token. Copy the refresh token. You should treat the refresh token like you would a password; if someone gets hold of it, they have access to your resources. 


In solutions like [Discovering disapproved ads](../solutions/get-disapproved-ads.md), which access Google services, set the credentials object's `clientId`, `clientSecret`, and `refreshToken` fields to the values you received performing the steps above.

