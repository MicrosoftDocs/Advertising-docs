---
title: "Authenticating with Google services"
description: "Shows options for getting an access token to use with Google services."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Authenticating with Google services

If your script uses Google services, such as Google Drive, Sheets, and Mail, you need to get credentials. There are a few of options for getting the credentials:

- [Option 1](#option1) &mdash; Easy to follow and takes less time but you need to repeat it every hour when the access token expires.
- [Option 2](#option2) &mdash; A little more complicated but you only need to repeat it if the refresh token becomes invalid.
- [Option 3](#option3) &mdash; Also a little more complicated (uses the provided PowerShell script) but you only need to repeat it if the refresh token becomes invalid.

## <a name="option1"></a>Option 1 - Getting an access token from Google OAuth playground

1. Go to [Google OAuth playground](https://developers.google.com/oauthplayground)
2. In **Input your own scopes**, paste https://www.googleapis.com/auth/drive https://www.googleapis.com/auth/gmail.send
3. Click **Authorize APIs** 
4. After the APIs are authorized, click **Exchange authorization code for tokens**
5. Copy the access_token's value from the response
6. In solutions such as [Discovering disapproved ads](../solutions/get-disapproved-ads.md) that access Google services, set the credentials object's `accessToken` field to the access token copied in step 5.

> [!NOTE]
> Because the access token expires in 1 hour, you'll need to repeat these steps every hour.


## <a name="option2"></a>Option 2 - Getting a refresh token from Google OAuth playground that you use to get an access token


1. Go to Google developer console API [dashboard](https://console.developers.google.com/apis/dashboard)
2. Click **Create a project** to create a new project or select an existing project  
   1. If creating a new project, enter the name of your project in **Project Name**. For example, Bing Ads Scripts.
   2. Click **Create**
3. On **Dashboard**, click **ENABLE APIS AND SERVICES**
4. In the search box, enter *sheets* and click **Google Sheets API**. Then, click **ENABLE**
5. Go back to the dashboard (click **APIs & Services**) and repeat steps 3 and 4 for Google Drive API
6. Go back to the dashboard (click **APIs & Services**) and repeat steps 3 and 4 for Gmail API
7. On **Dashboard**, click **Credentials** in the left navigation pane and then click the **OAuth consent screen** tab
8. Enter the name of your application in the **Application name** field (for example, Bing Ads Scripts)
9. Click **Add scope**, select *../auth/drive* and *../auth/gmail.send*, and then click **ADD**
10. Click **Save**
11. On the **Credentials** page, click **Create credentials** and then select **Oauth client ID**
12. Select **Other** application type, enter a name (for example, Bing Ads Scripts Client), and click **Create**
13. Copy your client ID and client secret to use in steps 17, 18, and 23 and then click **OK**
14. Go to [Google OAuth playground](https://developers.google.com/oauthplayground)
15. Click the OAuth 2.0 Configuration icon (looks like a gear in upper right corner)
16. Check the **Use your own OAuth credentials** box
17. Paste your client ID into **OAuth Client ID**
18. Paste your client secret into **OAuth Client secret**
19. In **Input your own scopes**, paste https://www.googleapis.com/auth/drive https://www.googleapis.com/auth/gmail.send
20. Click **Authorize APIs** and follow the prompts to provide consent 
21. After the APIs are authorized, click **Exchange authorization code for tokens**
22. Copy the token from **Refresh token** to use in step 23 
23. In solutions such as [Discovering disapproved ads](../solutions/get-disapproved-ads.md) that access Google services, set the credentials object's `clientId`, `clientSecret`, and `refreshToken` fields to the values you received in steps 13 and 22. 



## <a name="option3"></a>Option 3 - Using a PowerShell script to get a refresh token that you use to get an access token

1. Go to Google developer console API [dashboard](https://console.developers.google.com/apis/dashboard)
2. Click **Create a project** to create a new project or select an existing project  
   1. If creating a new project, enter the name of your project in **Project Name**. For example, Bing Ads Scripts.
   2. Click **Create**
3. On **Dashboard**, click **ENABLE APIS AND SERVICES**
4. In the search box, enter *sheets* and click **Google Sheets API**. Then, click **ENABLE**
5. Go back to the dashboard (click **APIs & Services**) and repeat steps 3 and 4 for Google Drive API
6. Go back to the dashboard (click **APIs & Services**) and repeat steps 3 and 4 for Gmail API
7. On **Dashboard**, click **Credentials** in the left navigation pane and then click the **OAuth consent screen** tab
8. Enter the name of your application in the **Application name** field (for example, Bing Ads Scripts)
9. Click **Add scope**, select *../auth/drive* and *../auth/gmail.send*, and then click **ADD**
10. Click **Save**
11. On the **Credentials** page, click **Create credentials** and then select **Oauth client ID**
12. Select **Other** application type, enter a name (for example, Bing Ads Scripts Client), and click **Create**
13. Copy your client ID and client secret to use in steps 14 and 15 and then click **OK**
14. Create a PowerShell script to get user consent and a refresh token.  
   
  Getting an access token requires user consent unless you have a refresh token. But because Scripts doesn't support UI components, you'll need to get consent another way. This PowerShell provides an option for getting consent and a refresh token.  
   
  Open Notepad or your favorite editor and copy the PowerShell script to the editor. Set `$clientId` and `$clientSecret` to the client ID and secret you received when you registered your app (see step 13).  
   
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
  
15. In solutions such as [Discovering disapproved ads](../solutions/get-disapproved-ads.md) that access Google services, set the credentials object's `clientId`, `clientSecret`, and `refreshToken` fields to the values you received in steps 13 and 14. 

