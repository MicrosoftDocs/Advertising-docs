---
title: "Get Started With the Bing Ads API"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Get a developer token and learn about authentication with the Bing Ads API.
dev_langs:
  - csharp
  - java
  - php
  - python
---
# Get Started With the Bing Ads API
Any Microsoft Advertising user with a developer token can begin using the Bing Ads API. For advertisers placing a large number of ads or developers building advertising tools, the Bing Ads API provides a programmatic interface to Microsoft Advertising. You can write your Bing Ads API application in any language that supports web services. To get started with a specific SDK, see Get Started in [C#](get-started-csharp.md) | [Java](get-started-java.md) | [PHP](get-started-php.md) | [Python](get-started-python.md). 

## <a name="quick-start"></a>Quick Start
If you just want to get something working right away, follow these steps to get your Microsoft Advertising user information. You can follow the links below for more details and customization options. For more details about registering an application and the authorization code grant flow, see [Authentication with OAuth](authentication-oauth.md). 

### <a name="quick-start-production"></a>Production Quick Start
To authenticate in the production environment, you can follow either the [Live Connect](authentication-oauth-live-connect.md) or [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) guides. We'll use the Microsoft identity platform endpoint since the Live Connect endpoint is no longer the recommended approach for Microsoft Advertising users.  

1. Sign up for a [Microsoft Advertising](https://ads.microsoft.com/) production account and with the same credentials get a [developer token](#get-developer-token). 

1. Register a native app in the [Azure portal - App registrations](https://go.microsoft.com/fwlink/?linkid=2083908) page. You can login using either a personal Microsoft Account or a Work or School Account. For details see [Register Your Application](authentication-oauth-identity-platform.md#registerapplication).  

1. Each Microsoft Advertising user must grant consent for your application to access their accounts. In this quick start, effectively you will need to grant your own application permission to access your own Microsoft Advertising account via the following `Get-Tokens-Production.ps1` PowerShell script. Open Notepad or your favorite editor and copy the PowerShell script to the editor. Set `$clientId` to the Application Id of your registered app. If you registered a web application with client secret, then you'll also need to include `$client_secret=YourWebAppClientSecret` when requesting the access tokens. 

    ```powershell
    # Replace the Tutorial Sample App ID with your registered application ID. 
    $clientId = "6731de76-14a6-49ae-97bc-6eba6914391e"

    Start-Process "https://login.microsoftonline.com/common/oauth2/v2.0/authorize?client_id=$clientId&scope=openid%20profile%20https://ads.microsoft.com/ads.manage%20offline_access&response_type=code&redirect_uri=https://login.microsoftonline.com/common/oauth2/nativeclient&state=ClientStateGoesHere&prompt=login"

    $code = Read-Host "Grant consent in the browser, and then enter the code here (see ?code=UseThisCode&...)"

    # Get the initial access and refresh tokens. 
    
    $response = Invoke-WebRequest https://login.microsoftonline.com/common/oauth2/v2.0/token -ContentType application/x-www-form-urlencoded -Method POST -Body "client_id=$clientId&scope=https://ads.microsoft.com/ads.manage%20offline_access&code=$code&grant_type=authorization_code&redirect_uri=https%3A%2F%2Flogin.microsoftonline.com%2Fcommon%2Foauth2%2Fnativeclient"

    $oauthTokens = ($response.Content | ConvertFrom-Json)  
    Write-Output "Access token: " $oauthTokens.access_token  
    Write-Output "Access token expires in: " $oauthTokens.expires_in  
    Write-Output "Refresh token: " $oauthTokens.refresh_token 

    # The access token will expire e.g., after one hour. 
    # Use the refresh token to get new access and refresh tokens. 

    $response = Invoke-WebRequest https://login.microsoftonline.com/common/oauth2/v2.0/token -ContentType application/x-www-form-urlencoded -Method POST -Body "client_id=$clientId&scope=https://ads.microsoft.com/ads.manage%20offline_access&code=$code&grant_type=refresh_token&refresh_token=$($oauthTokens.refresh_token)"

    $oauthTokens = ($response.Content | ConvertFrom-Json)  
    Write-Output "Access token: " $oauthTokens.access_token  
    Write-Output "Access token expires in: " $oauthTokens.expires_in  
    Write-Output "Refresh token: " $oauthTokens.refresh_token 
    ```

    Save the file and name it `Get-Tokens-Production.ps1` (you can name it anything you want but the extension must be .ps1).

    To programmatically manage a Microsoft Advertising account, you must provide consent at least once through the web application consent flow. Thereafter you can use the latest refresh token to request new access and refresh tokens without any further user interaction. 
   
1. Now to run `Get-Tokens-Production.ps1` open a console window. At the command prompt, navigate to the folder where you saved `Get-Tokens-Production.ps1` and enter the following command:  
  
    ```console
    powershell.exe -File .\Get-Tokens-Production.ps1
    ```  
      
    When the PowerShell script successfully runs, it starts a browser session where you enter your Microsoft Advertising credentials. After consenting, the browser's address bar contains the grant code (see ?code=UseThisCode&...).  
      
    ```https
    https://login.microsoftonline.com/common/oauth2/nativeclient?code=M7ab570e5-a1c0-32e5-a946-e490c82954
    ```  
      
    Copy the grant code (your own code, not M7ab570e5-a1c0-32e5-a946-e490c82954) and enter it in the console window at the prompt. The PowerShell script then returns the access and refresh tokens. (The script makes a second call to Invoke-WebRequest as an example of how to refresh the tokens.) You should treat the refresh token like you would a password; if someone gets hold of it, they have access to your resources. The refresh token is long lived but it can become invalid. If you ever receive an invalid_grant error, your refresh token is no longer valid and you'll need to run the `Get-Tokens-Production.ps1` PowerShell script again to get user consent and a new refresh token. 
  
1. Create a new file and paste into it the following script. Set the `accessToken` to the value you received from `Get-Tokens-Production.ps1` and set `$developerToken` to the developer token you received from Step 1 above. 
   
    ```powershell
    $accessToken = "AccessTokenGoesHere";
    $developerToken = "DeveloperTokenGoesHere";
    
    [xml]$getUserRequest = 
    '<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:v13="https://bingads.microsoft.com/Customer/v13">
    <soapenv:Header>
       <v13:DeveloperToken>{0}</v13:DeveloperToken>
       <v13:AuthenticationToken>{1}</v13:AuthenticationToken>
    </soapenv:Header>
    <soapenv:Body>
       <v13:GetUserRequest>
          <v13:UserId xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:nil="true"/>
       </v13:GetUserRequest>
    </soapenv:Body>
    </soapenv:Envelope>' -f $developerToken, $accessToken
    
    $headers = @{"SOAPAction" = "GetUser"}
    
    $uri = "https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc"
    $response = Invoke-WebRequest $uri -Method post -ContentType 'text/xml' -Body $getUserRequest -Headers $headers
    Write-Output $response.Content
    ```  

    Save the file and name it `Get-User.ps1` (you can name it anything you want but the extension must be .ps1).

1. Now to run `Get-User.ps1` open a console window. At the command prompt, navigate to the folder where you saved `Get-User.ps1` and enter the following command:  
  
    ```console
    powershell.exe -File .\Get-User.ps1
    ```  
      
    When the PowerShell script successfully runs it should print out the details of your Microsoft Advertising user, including customer roles. For details see [GetUser](../customer-management-service/getuser.md). 

### <a name="quick-start-sandbox"></a>Sandbox Quick Start
To authenticate in the sandbox environment only the [Live Connect](authentication-oauth-live-connect.md) endpoint (with '-int' suffix) is supported.  

1. Sign up for a [Microsoft Advertising](https://sandbox.bingads.microsoft.com/) sandbox account. The Microsoft account (MSA) email address must be outlook**-int**.com (for example, someone@outlook-int.com). For more details see [Sandbox](sandbox.md#initial-sign-up).  

1. Each Microsoft Advertising user must grant consent for your application to access their accounts. In this quick start, effectively you will need to grant your own application permission to access your own Microsoft Advertising account via the following `Get-Tokens-Sandbox.ps1` PowerShell script. Open Notepad or your favorite editor and copy the PowerShell script to the editor.  

    > [!NOTE]
    > Although in production you must use your own application ID (a.k.a. client ID), all Microsoft Advertising customers can use the public "Sandbox Tutorial App" client ID in sandbox i.e., **db41b09d-6e50-4f4a-90ac-5a99caefb52f**. For more information, please see [Sandbox](sandbox.md#access). 
   
    ```powershell
    $clientId = "db41b09d-6e50-4f4a-90ac-5a99caefb52f"

    Start-Process "https://login.live-int.com/oauth20_authorize.srf?client_id=$clientId&scope=bingads.manage&response_type=code&redirect_uri=https://login.live-int.com/oauth20_desktop.srf&prompt=login%20consent"
    
    $code = Read-Host "Grant consent in the browser, and then enter the code here (see ?code=UseThisCode&...)"
    
    # Get the initial access and refresh tokens. 

    $response = Invoke-WebRequest https://login.live-int.com/oauth20_token.srf -ContentType application/x-www-form-urlencoded -Method POST -Body "client_id=$clientId&scope=bingads.manage&code=$code&grant_type=authorization_code&redirect_uri=https%3A%2F%2Flogin.live-int.com%2Foauth20_desktop.srf"
    
    $oauthTokens = ($response.Content | ConvertFrom-Json)  
    Write-Output "Access token: " $oauthTokens.access_token  
    Write-Output "Access token expires in: " $oauthTokens.expires_in  
    Write-Output "Refresh token: " $oauthTokens.refresh_token 
    
    # The access token will expire e.g., after one hour. 
    # Use the refresh token to get new access and refresh tokens. 
    
    $response = Invoke-WebRequest https://login.live-int.com/oauth20_token.srf -ContentType application/x-www-form-urlencoded -Method POST -Body "client_id=$clientId&scope=bingads.manage&code=$code&grant_type=refresh_token&refresh_token=$($oauthTokens.refresh_token)"
    
    $oauthTokens = ($response.Content | ConvertFrom-Json)  
    Write-Output "Access token: " $oauthTokens.access_token  
    Write-Output "Access token expires in: " $oauthTokens.expires_in  
    Write-Output "Refresh token: " $oauthTokens.refresh_token 
    ```  

    Save the file and name it `Get-Tokens-Sandbox.ps1` (you can name it anything you want but the extension must be .ps1).

    To programmatically manage a Microsoft Advertising account, you must provide consent at least once through the web application consent flow. Thereafter you can use the latest refresh token to request new access and refresh tokens without any further user interaction. 
   
1. Now to run `Get-Tokens-Sandbox.ps1` open a console window. At the command prompt, navigate to the folder where you saved `Get-Tokens-Sandbox.ps1` and enter the following command:  
  
    ```console
    powershell.exe -File .\Get-Tokens-Sandbox.ps1
    ```  
      
    When the PowerShell script successfully runs, it starts a browser session where you enter your Microsoft Advertising credentials. After consenting, the browser's address bar contains the grant code (see ?code=UseThisCode&...).  
      
    ```https
    https://login.live-int.com/oauth20_desktop.srf?code=M7ab570e5-a1c0-32e5-a946-e490c82954&lc=1033
    ```  
      
    Copy the grant code (your own code, not M7ab570e5-a1c0-32e5-a946-e490c82954) and enter it in the console window at the prompt. The PowerShell script then returns the access and refresh tokens. (The script makes a second call to Invoke-WebRequest as an example of how to refresh the tokens.) You should treat the refresh token like you would a password; if someone gets hold of it, they have access to your resources. The refresh token is long lived but it can become invalid. If you ever receive an invalid_grant error, your refresh token is no longer valid and you'll need to run the `Get-Tokens-Sandbox.ps1` PowerShell script again to get user consent and a new refresh token.  
  
1. Create a new file and paste into it the following script. Set the `accessToken` to the value you received from `Get-Tokens-Sandbox.ps1`. 
   
    ```powershell
    $accessToken = "AccessTokenGoesHere";
    $developerToken = "BBD37VB98";
    
    [xml]$getUserRequest = 
    '<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:v13="https://bingads.microsoft.com/Customer/v13">
    <soapenv:Header>
       <v13:DeveloperToken>{0}</v13:DeveloperToken>
       <v13:AuthenticationToken>{1}</v13:AuthenticationToken>
    </soapenv:Header>
    <soapenv:Body>
       <v13:GetUserRequest>
          <v13:UserId xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:nil="true"/>
       </v13:GetUserRequest>
    </soapenv:Body>
    </soapenv:Envelope>' -f $developerToken, $accessToken
    
    $headers = @{"SOAPAction" = "GetUser"}
    
    $uri = "https://clientcenter.api.sandbox.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc"
    $response = Invoke-WebRequest $uri -Method post -ContentType 'text/xml' -Body $getUserRequest -Headers $headers
    Write-Output $response.Content
    ```  

    Save the file and name it `Get-User.ps1` (you can name it anything you want but the extension must be .ps1).

1. Now to run `Get-User.ps1` open a console window. At the command prompt, navigate to the folder where you saved `Get-User.ps1` and enter the following command:  
  
    ```console
    powershell.exe -File .\Get-User.ps1
    ```  
      
    When the PowerShell script successfully runs it should print out the details of your Microsoft Advertising user, including customer roles. For details see [GetUser](../customer-management-service/getuser.md). 

What's next? First, congratulations on making your first call to Bing Ads API! Here are a few concepts and ideas to explore further:
- The [GetUser](../customer-management-service/getuser.md) operation above returned the Microsoft Advertising user ID and a list of user roles per customer ID. With the user ID, you can now call [SearchAccounts](../customer-management-service/searchaccounts.md) to get a list accounts the user can access i.e., via the UserId predicate. 
- If you use .NET, Java, PHP, or Python, you'll want to try the Microsoft Advertising [SDKs](client-libraries.md). Some of the low level authorization details are abstracted, for example the [request header](#request-headers) elements are automatically set. For more details, see [Authentication With the SDKs](sdk-authentication.md). 
- You can register an application with any Microsoft account or Azure AD credentials; you don't need to use a Microsoft Advertising user for the application registration. 
- If your application will be used by multiple Microsoft Advertising users, be sure that you have a [universal developer token](#get-developer-token). 
- The access token represents the user credentials who has access to one or more Microsoft Advertising accounts. The application ID (a.k.a. client_id) identifies your application for each Microsoft Advertising user who grants consent. The developer token gives your application permission to use the Bing Ads API. 

## <a name="get-developer-token"></a>Get a Developer Token
To use Bing Ads APIs, you must have a developer token and valid user credentials. If you do not yet have a Microsoft Advertising account, you can sign up via the [Microsoft Advertising web application](https://ads.microsoft.com/). 

> [!NOTE]
> The sandbox and production environments use separate credentials. You can sign up for a [Sandbox](sandbox.md) account [here](https://secure.sandbox.bingads.microsoft.com/). Everyone can use the universal sandbox developer token i.e., **BBD37VB98**. 

You can follow these steps to get a developer token for production.

1. Sign in with [Super Admin](account-hierarchy-permissions.md#user-roles-permissions) credentials at the [Microsoft Advertising Developer Portal](https://developers.ads.microsoft.com/Account) account tab. 
1. Choose the user that you want associated with the developer token. Typically an application only needs one universal token regardless how many users will be supported. 
1. Click on the **Request Token** button.    

The universal developer token can be used to authenticate with any valid user credentials. You can use the same universal developer token whether your application will be used by one or multiple Microsoft Advertising users. As of July 2019, this is the default token type.    

The single-user developer token can only be used to authenticate one user for access to one customer. This token type has been deprecated in favor of the universal token. If you still see that a single user token is assigned to one of your users, you can click "Upgrade to Universal" as shown here. 

![Upgrade to Universal Developer Token](media/upgrade-token-single-universal.png "Upgrade to Universal Developer Token")  

A developer token enables programmatic access to the accounts permitted for a user. Obtaining a developer token for API access does not grant additional permissions to any Microsoft Advertising accounts. Each Microsoft Advertising user is assigned a [role](account-hierarchy-permissions.md#user-roles-permissions) e.g., Super Admin or Advertiser Campaign Manager for every customer they can access. With a developer token the same accounts available in the Microsoft Advertising web application are available to the user programmatically through the API. 

## <a name="where-to-use"></a>Where to Use the API Credentials
When you call a service operation such as [GetCampaignsByAccountId](../campaign-management-service/getcampaignsbyaccountid.md), you must specify [request header](#request-headers) elements such as DeveloperToken, CustomerId, and CustomerAccountId.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <Action mustUnderstand="1">GetCampaignsByAccountId</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <GetCampaignsByAccountIdRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <AccountId>ValueHere</AccountId>
      <CampaignType>ValueHere</CampaignType>
    </GetCampaignsByAccountIdRequest>
  </s:Body>
</s:Envelope>
```

If you are using one of the Microsoft Advertising [SDKs](client-libraries.md), the [request header](#request-headers) elements are set using *AuthorizationData*. For more details about the SDK authentication library see [Authentication With the SDKs](sdk-authentication.md). 

```csharp
var authorizationData = new AuthorizationData
{
    Authentication = <AuthenticationGoesHere>, 
    CustomerId = <CustomerIdGoesHere>,
    AccountId = <AccountIdGoesHere>,
    DeveloperToken = "<DeveloperTokenGoesHere>"
};
```
```java
static AuthorizationData authorizationData = new AuthorizationData();
authorizationData.setAuthentication(<AuthenticationGoesHere>);
authorizationData.setCustomerId("<CustomerIdGoesHere>");
authorizationData.setAccountId("<AccountIdGoesHere>");
authorizationData.setDeveloperToken("<DeveloperTokenGoesHere>");
```
```php
$authorizationData = (new AuthorizationData())
    ->withAuthentication($AuthenticationGoesHere)
    ->withCustomerId($CustomerIdGoesHere)
    ->withAccountId($AccountIdGoesHere)
    ->withDeveloperToken($DeveloperTokenGoesHere);
```
```python
authorization_data = AuthorizationData(
    authentication = <AuthenticationGoesHere>,
    customer_id = <CustomerIdGoesHere>,
    account_id = <AccountIdGoesHere>,
    developer_token = '<DeveloperTokenGoesHere>'
)
```

## <a name="get-ids"></a>Get Your Account and Customer IDs
To get a user's customer ID and account ID, you can sign in to the Microsoft Advertising web application and click on the **Campaigns** tab. The URL will contain a *cid* key/value pair in the query string that identifies your customer ID, and an *aid* key/value pair that identifies your account ID. For example, *https://ui.ads.microsoft.com/campaign/Campaigns.m?cid=FindCustomerIdHere&aid=FindAccountIdHere#/customer/FindCustomerIdHere/account/FindAccountIdHere/campaign*.

> [!TIP]
> Do not mistake the account number for the account identifier. The account number is the system-generated account number that is used to identify the account in the Microsoft Advertising web application. The account number has the form xxxxxxxx, where xxxxxxxx is a series of any eight alphanumeric characters. The API service requests only use the account identifier, and never use the account number.

With the Customer Management API you can get the customer and account identifiers for each authenticated user. 

Call [GetUser](../customer-management-service/getuser.md) with your Microsoft Advertising credentials and DeveloperToken. Within the Body set the UserId nil. The response will include a [User](../customer-management-service/user.md) object that contains the UserId.

```xml
<?xml version="1.0" encoding="utf-8"?>
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <h:ApplicationToken i:nil="true" xmlns:h="https://bingads.microsoft.com/Customer/v13" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" />
    <h:AuthenticationToken xmlns:h="https://bingads.microsoft.com/Customer/v13">OAuthAccessTokenGoesHere</h:AuthenticationToken>
    <h:DeveloperToken xmlns:h="https://bingads.microsoft.com/Customer/v13">DeveloperTokenGoesHere</h:DeveloperToken>
  </s:Header>
  <s:Body>
    <GetUserRequest xmlns="https://bingads.microsoft.com/Customer/v13">
      <UserId i:nil="true" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" />
    </GetUserRequest>
  </s:Body>
</s:Envelope>
```

Then call [SearchAccounts](../customer-management-service/searchaccounts.md) with the UserId returned via the previous step. The returned advertiser account (or accounts) will include account and customer identifiers.

```xml
<?xml version="1.0" encoding="utf-8"?>
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <h:ApplicationToken i:nil="true" xmlns:h="https://bingads.microsoft.com/Customer/v13" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" />
    <h:AuthenticationToken xmlns:h="https://bingads.microsoft.com/Customer/v13">OAuthAccessTokenGoesHere</h:AuthenticationToken>
    <h:DeveloperToken xmlns:h="https://bingads.microsoft.com/Customer/v13">DeveloperTokenGoesHere</h:DeveloperToken>
  </s:Header>
  <s:Body>
    <SearchAccountsRequest xmlns="https://bingads.microsoft.com/Customer/v13">
      <Predicates xmlns:a="https://bingads.microsoft.com/Customer/v13/Entities" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <a:Predicate>
          <a:Field>UserId</a:Field>
          <a:Operator>Equals</a:Operator>
          <a:Value>UserIdGoesHere</a:Value>
        </a:Predicate>
      </Predicates>
      <Ordering i:nil="true" xmlns:a="https://bingads.microsoft.com/Customer/v13/Entities" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" />
      <PageInfo xmlns:a="https://bingads.microsoft.com/Customer/v13/Entities" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <a:Index>0</a:Index>
        <a:Size>10</a:Size>
      </PageInfo>
    </SearchAccountsRequest>
  </s:Body>
</s:Envelope>
```

> [!TIP]
> See [Search User Accounts Code Example](code-example-search-user-accounts.md) for a code example that returns accounts for the current authenticated user.

## <a name="request-headers"></a>Request Header Elements
Bing Ads API service operations use Simple Object Access Protocol (SOAP) to exchange the request and response messages with the service operation. For more information, see [Bing Ads API Services Protocol](services-protocol.md).

Each SOAP request must include the following SOAP headers, which contain the user's credentials.

> [!NOTE]
> The CustomerAccountId and CustomerId elements are not applicable for the Customer Billing and Customer Management services. 

|Element|Description|Data Type|
|-----------|---------------|-------------|
|ApplicationToken|This header element is not used and should be ignored.|**string**|
|AuthenticationToken|The OAuth access token that represents a Microsoft Account user who has permissions to Microsoft Advertising accounts. For more information, see [Authentication with OAuth](authentication-oauth.md).|**string**|
|CustomerAccountId|The identifier of the account that owns the entities in the request. This header element must have the same value as the AccountId body element when both are required. This element is required for most service operations, and as a best practice you should always set it.|**string**|
|CustomerId|The identifier of the customer that contains and owns the account. If you manage an account of another customer, you should use that customer ID instead of your own customer ID. This element is required for most service operations, and as a best practice you should always set it.|**string**|
|DeveloperToken|The developer token used to access the Bing Ads API.|**string**|
|Password|This element is reserved for internal use and will be removed from a future version of the API. You must use the AuthenticationToken element to set user credentials. |**string**|
|UserName|This element is reserved for internal use and will be removed from a future version of the API. You must use the AuthenticationToken element to set user credentials.|**string**|

## <a name="need-help"></a>Need Help?
For troubleshooting tips, see [Handling Service Errors and Exceptions](handle-service-errors-exceptions.md).

The [Microsoft Q&A](https://docs.microsoft.com/answers/topics/advertising-api.html) forum is available for the developer community to ask and answer questions about the Bing Ads APIs and Microsoft Advertising Scripts. Microsoft monitors the forums and replies to questions that the community has not yet answered.

> [!IMPORTANT]
> To make sure that we see your question, tag it with 'advertising-api'.  

If the investigation involves sensitive account or personal details, or if you are not finding the information you need to solve your problem via [Microsoft Q&A](https://docs.microsoft.com/answers/topics/advertising-api.html), please contact [Microsoft Advertising Support](https://about.ads.microsoft.com/en-us/microsoft-advertising-support). To resolve the issue efficiently, please provide support with the details requested in [Engaging Support](handle-service-errors-exceptions.md#contact-support). 

## See Also
[Bing Ads API Technical Guides](technical-guides.md)  
[Bing Ads API Reference](reference.md)  

