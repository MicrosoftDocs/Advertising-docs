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
Any Bing Ads user with a developer token can begin using the Bing Ads API. For advertisers placing a large number of ads or developers building advertising tools, the Bing Ads API provides a programmatic interface to Bing Ads. You can write your Bing Ads application in any language that supports web services. To get started with a specific SDK, see Get Started in [C#](get-started-csharp.md) | [Java](get-started-java.md) | [PHP](get-started-php.md) | [Python](get-started-python.md). 

## <a name="quick-start"></a>Quick Start
If you just want to get something working right away, follow these steps to get your Bing Ads user information. You can follow the links for details and customization options. 

1. Sign up for [Bing Ads](https://secure.bingads.microsoft.com/) and use the same credentials get a [developer token](#get-developer-token). 

1. Register a native app via the [Application Registration Portal](https://apps.dev.microsoft.com/#/appList). For details see [Registering Your Application](authentication-oauth.md#registerapplication). 

1. Each Bing Ads user must grant consent for your application to access their accounts. In this quick start, effectively you will need to grant your own application permission to access your own Bing Ads account via the following `Get-Tokens.ps1` PowerShell script. Open Notepad or your favorite editor and copy the PowerShell script to the editor. Set `$clientId` to the Application Id of your registered app. 
   
    ```powershell
    $clientId = "YourApplicationIdGoesHere"

    Start-Process "https://login.live.com/oauth20_authorize.srf?client_id=$clientId&scope=bingads.manage&response_type=code&redirect_uri=https://login.live.com/oauth20_desktop.srf"
    
    $code = Read-Host "Grant consent in the browser, and then enter the code here (see ?code=UseThisCode&...)"
      
    $response = Invoke-WebRequest https://login.live.com/oauth20_token.srf -ContentType application/x-www-form-urlencoded -Method POST -Body "client_id=$clientId&scope=bingads.manage&code=$code&grant_type=authorization_code&redirect_uri=https%3A%2F%2Flogin.live.com%2Foauth20_desktop.srf"
    
    $oauthTokens = ($response.Content | ConvertFrom-Json)  
    Write-Output "Access token: " $oauthTokens.access_token  
    Write-Output "Access token expires in: " $oauthTokens.expires_in  
    Write-Output "Refresh token: " $oauthTokens.refresh_token 
    
    # The access token will expire e.g., after one hour. 
    # Use the refresh token to get a new access token. 
    
    $response = Invoke-WebRequest https://login.live.com/oauth20_token.srf -ContentType application/x-www-form-urlencoded -Method POST -Body "client_id=$clientId&scope=bingads.manage&code=$code&grant_type=refresh_token&redirect_uri=https%3A%2F%2Flogin.live.com%2Foauth20_desktop.srf&refresh_token=$($oauthTokens.refresh_token)"
    
    $oauthTokens = ($response.Content | ConvertFrom-Json)  
    Write-Output "Access token: " $oauthTokens.access_token  
    Write-Output "Access token expires in: " $oauthTokens.expires_in  
    Write-Output "Refresh token: " $oauthTokens.refresh_token 
    ```  

    Save the file and name it `Get-Tokens.ps1` (you can name it anything you want but the extension must be .ps1).

    To programatically manage a Bing Ads account, you must provide consent at least once through the web application consent flow. Thereafter you can use the latest refresh token to request new access and refresh tokens without any further user interaction. For more details see [authorization code grant flow](authentication-oauth.md#authorizationcode).
   
1. Now to run `Get-Tokens.ps1` open a console window. At the command prompt, navigate to the folder where you saved `Get-Tokens.ps1` and enter the following command:  
  
    ```console
    powershell.exe -File .\Get-Tokens.ps1
    ```  
      
    When the PowerShell script successfully runs, it starts a browser session where you enter your Bing Ads credentials. After consenting, the browser's address bar contains the grant code (see ?code=UseThisCode&...).  
      
    ```https
    https://login.live.com/oauth20_desktop.srf?code=M7ab570e5-a1c0-32e5-a946-e490c82954&lc=1033
    ```  
      
    Copy the grant code (your own code, not M7ab570e5-a1c0-32e5-a946-e490c82954) and enter it in the console window at the prompt. The PowerShell script then returns the access and refresh tokens. You should treat the refresh token like you would a password; if someone gets hold of it, they have access to your resources. The refresh token is long lived but it can become invalid. If you ever receive an invalid_grant error, your refresh token is no longer valid and you'll need to run the `Get-Tokens.ps1` PowerShell script again to get consent and a new refresh token.  
  
1. Create a new file and paste into it the following script. Set the `accessToken` to the value you received from `Get-Tokens.ps1` and set `$developerToken` to the developer token you received from Step 1 above. 
   
    ```powershell
    $accessToken = "AccessTokenGoesHere";
    $developerToken = "DeveloperTokenGoesHere";
    
    [xml]$getUserRequest = 
    '<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:v12="https://bingads.microsoft.com/Customer/v12">
    <soapenv:Header>
       <v12:DeveloperToken>{0}</v12:DeveloperToken>
       <v12:AuthenticationToken>{1}</v12:AuthenticationToken>
    </soapenv:Header>
    <soapenv:Body>
       <v12:GetUserRequest>
          <v12:UserId xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:nil="true"/>
       </v12:GetUserRequest>
    </soapenv:Body>
    </soapenv:Envelope>' -f $developerToken, $accessToken
    
    $headers = @{"SOAPAction" = "GetUser"}
    
    $uri = "https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc"
    $response = Invoke-WebRequest $uri -Method post -ContentType 'text/xml' -Body $getUserRequest -Headers $headers
    Write-Output $response.Content
    ```  

    Save the file and name it `Get-User.ps1` (you can name it anything you want but the extension must be .ps1).

1. Now to run `Get-User.ps1` open a console window. At the command prompt, navigate to the folder where you saved `Get-User.ps1` and enter the following command:  
  
    ```console
    powershell.exe -File .\Get-User.ps1
    ```  
      
    When the PowerShell script successfully runs it should print out the details of your Bing Ads user, including customer roles. For details see [GetUser](../customer-management-service/getuser.md). 

What's next? First, congratulations on making your first call to Bing Ads API! Here are a few concepts and ideas to explore further:
- The [GetUser](../customer-management-service/getuser.md) operation above returned the Bing Ads user ID and a list of user roles per customer ID. With the user ID, you can now call [SearchAccounts](../customer-management-service/searchaccounts.md) to get a list accounts the user can access i.e., via the UserId predicate. 
- If you use .NET, Java, PHP, or Python, you'll want to try the Bing Ads [SDKs](client-libraries.md). Some of the low level authorization details are abstracted, for example the [request header](#request-headers) elements are automatically set. For more details, see [Authentication With the SDKs](sdk-authentication.md). 
- You can register an application with any Microsoft account; you don't need to use a Bing Ads user for the application registration. 
- If your application will be used by multiple Bing Ads users, be sure to request a [universal developer token](#get-developer-token). 
- The Application Id (a.k.a. client_id) identifies your application for each Bing Ads user who grants consent; The Developer Token identifies your application for Bing Ads services. You could use multiple application IDs with the same developer token, or vice versa depending on your business requirements. 

## <a name="get-developer-token"></a>Get a Developer Token
To use Bing Ads APIs, you must have a developer token and valid user credentials.   
- If you do not yet have a Bing Ads account, you can sign up via the [Bing Ads web application](https://secure.bingads.microsoft.com/). 
- To get a developer token for production, you must login at the [Bing Ads Developer Portal](https://developers.bingads.microsoft.com/Account) as a Microsoft Account user with the Super Admin role. Then click on the **Request Token** button. The Super Admin may request API access for any user within their customer scope. 

> [!NOTE]
> The sandbox and production environments use separate credentials. You can sign up for a [Sandbox](sandbox.md) account [here](https://secure.sandbox.bingads.microsoft.com/). Everyone can use the universal sandbox developer token i.e., **BBD37VB98**.

There are two types of Bing Ads developer tokens. 
- Single-user developer token can be used to authenticate solely with one designated user. For example if you are a direct advertiser with one log in email address, then you will only need a single-user token.  
- Universal developer token can be used to authenticate with any valid user credentials. For example if you are developing an application that will be used by multiple Bing Ads users, then you will likely want to request a universal token instead of getting a single-user token for each user.

Regardless of the type, a developer token enables programmatic access to the accounts permitted for a user. Obtaining a developer token for API access does not grant additional permissions to any Bing Ads accounts. Each Bing Ads user is assigned a role e.g., Super Admin or Advertiser Campaign Manager for every customer they can access. With a developer token the same accounts available in the Bing Ads web application are available to the user programmatically through the API. 

## <a name="where-to-use"></a>Where to Use the API Credentials
When you call a service operation such as [GetCampaignsByAccountId](../campaign-management-service/getcampaignsbyaccountid.md), you must specify [request header](#request-headers) elements such as DeveloperToken, CustomerId, and CustomerAccountId.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetCampaignsByAccountId</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <GetCampaignsByAccountIdRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <AccountId>ValueHere</AccountId>
      <CampaignType>ValueHere</CampaignType>
    </GetCampaignsByAccountIdRequest>
  </s:Body>
</s:Envelope>
```

If you are using one of the Bing Ads [SDKs](client-libraries.md), the [request header](#request-headers) elements are set using *AuthorizationData*. For more details about the SDK authentication library see [Authentication With the SDKs](sdk-authentication.md). 

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

## <a name="get-ids"></a> Get Your Account and Customer Ids
To get a user's customer ID and account ID, you can sign in to the Bing Ads web application and click on the **Campaigns** tab. The URL will contain a *cid* key/value pair in the query string that identifies your customer ID, and an *aid* key/value pair that identifies your account ID. For example, *https://ui.bingads.microsoft.com/campaign/Campaigns.m?cid=FindCustomerIdHere&aid=FindAccountIdHere#/customer/FindCustomerIdHere/account/FindAccountIdHere/campaign*.

> [!TIP]
> Do not mistake the account number for the account identifier. The account number is the system generated account number that is used to identify the account in the Bing Ads web application. The account number has the form xxxxxxxx, where xxxxxxxx is a series of any eight alphanumeric characters. The API service requests only use the account identifier, and never use the account number.

With the Customer Management API you can get the customer and account identifiers for each authenticated user. 

Call [GetUser](../customer-management-service/getuser.md) with your Bing Ads credentials and DeveloperToken. Within the Body set the UserId nil. The response will include a [User](../customer-management-service/user.md) object that contains the UserId.

```xml
<?xml version="1.0" encoding="utf-8"?>
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <h:ApplicationToken i:nil="true" xmlns:h="https://bingads.microsoft.com/Customer/v12" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" />
    <h:AuthenticationToken xmlns:h="https://bingads.microsoft.com/Customer/v12">OAuthAccessTokenGoesHere</h:AuthenticationToken>
    <h:DeveloperToken xmlns:h="https://bingads.microsoft.com/Customer/v12">DeveloperTokenGoesHere</h:DeveloperToken>
  </s:Header>
  <s:Body>
    <GetUserRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <UserId i:nil="true" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" />
    </GetUserRequest>
  </s:Body>
</s:Envelope>
```

Then call [SearchAccounts](../customer-management-service/getuser.md) with the UserId returned via the previous step. The returned advertiser account (or accounts) will include account and customer identifiers.

```xml
<?xml version="1.0" encoding="utf-8"?>
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <h:ApplicationToken i:nil="true" xmlns:h="https://bingads.microsoft.com/Customer/v12" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" />
    <h:AuthenticationToken xmlns:h="https://bingads.microsoft.com/Customer/v12">OAuthAccessTokenGoesHere</h:AuthenticationToken>
    <h:DeveloperToken xmlns:h="https://bingads.microsoft.com/Customer/v12">DeveloperTokenGoesHere</h:DeveloperToken>
  </s:Header>
  <s:Body>
    <SearchAccountsRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <Predicates xmlns:a="https://bingads.microsoft.com/Customer/v12/Entities" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <a:Predicate>
          <a:Field>UserId</a:Field>
          <a:Operator>Equals</a:Operator>
          <a:Value>UserIdGoesHere</a:Value>
        </a:Predicate>
      </Predicates>
      <Ordering i:nil="true" xmlns:a="https://bingads.microsoft.com/Customer/v12/Entities" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" />
      <PageInfo xmlns:a="https://bingads.microsoft.com/Customer/v12/Entities" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
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
Bing Ads services use Simple Object Access Protocol (SOAP) to exchange the request and response messages with the service operation. For more information, see [Bing Ads Services Protocol](services-protocol.md).

Each SOAP request must include the following SOAP headers, which contain the user's credentials.

> [!NOTE]
> The CustomerAccountId and CustomerId elements are not applicable for the Customer Billing and Customer Management services. 

|Element|Description|Data Type|
|-----------|---------------|-------------|
|ApplicationToken|This header element is not used and should be ignored.|**string**|
|AuthenticationToken|The OAuth access token that represents a Microsoft Account user who has permissions to Bing Ads accounts. For more information, see [Authentication with OAuth](authentication-oauth.md).|**string**|
|CustomerAccountId|The identifier of the account that owns the entities in the request. This header element must have the same value as the AccountId body element when both are required. This element is required for most service operations, and as a best practice you should always set it.|**string**|
|CustomerId|The identifier of the customer that contains and owns the account. If you manage an account of another customer, you should use that customer ID instead of your own customer ID. This element is required for most service operations, and as a best practice you should always set it.|**string**|
|DeveloperToken|The developer token used to access the Bing Ads API.|**string**|
|Password|This element is reserved for internal use and will be removed from a future version of the API. You must use the AuthenticationToken element to set user credentials. |**string**|
|UserName|This element is reserved for internal use and will be removed from a future version of the API. You must use the AuthenticationToken element to set user credentials.|**string**|

## <a name="need-help"></a>Need Help?
For troubleshooting tips, see [Handling Service Errors and Exceptions](handle-service-errors-exceptions.md).

To get help with issues that you cannot resolve, consider posting in the [API Developer Forum](https://social.msdn.microsoft.com/forums/en-us/home?forum=BingAds) where an active Bing Ads product team or community member will try and help. If you do not find timely information via the developer forum, or if the investigation involves sensitive account or personal details, please contact [Bing Ads Support](https://advertise.bingads.microsoft.com/en-us/bing-ads-support).

## See Also
[Bing Ads Technical Guides](technical-guides.md)  
[Bing Ads API Reference](reference.md)  

