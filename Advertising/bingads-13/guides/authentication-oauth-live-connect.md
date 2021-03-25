---
title: "Authentication with the Live Connect endpoint"
ms.service: "bing-ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Authenticate for Bing Ads API using the Live Connect endpoint.
---
# Authentication with the Live Connect endpoint

> [!IMPORTANT]
> Starting August 1st, 2021 we will require multi-factor authentication for all users who sign in through a third-party application that uses the Bing Ads API, Content API, and Hotel APIs.
> You must update your application to use the new ```msads.manage``` scope via the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md). All application developers must take action to use the new scope.
> 
> Prior to MFA enforcement the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) supports the ```ads.manage``` scope. Access tokens that you acquire for users via the ads.manage scope will no longer be authenticated.
> 
> Prior to MFA enforcement the [Live Connect](authentication-oauth-live-connect.md) endpoint supports the ```bingads.manage``` scope. The Live Connect endpoint is already deprecated and will no longer be supported. Access tokens that you acquire for users via the bingads.manage scope will no longer be authenticated.
> 
> Upon enforcement of the MFA requirement, we will only authenticate access tokens on behalf of a user who passed through MFA via the new ```msads.manage``` scope on the Microsoft Identity endpoint.
> 
> The new ```msads.manage``` scope **requires renewed consent from all users of your application**. You must prompt users for consent using the new ```msads.manage``` scope after they have turned on multi-factor authentication. We recommend that you inform and guide users of your application to [set up MFA](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time#who-decides-if-you-use-this-feature) MFA right away.

Consider the user that you want to sign in e.g., example@contoso.com. The Bing Ads API will not accept the email address and password as plain text, rather when you call the Bing Ads API you need to set the AuthenticationToken header element that contains a user access token. 

How can you get an access token? Microsoft Advertising follows the [OAuth 2.0](https://tools.ietf.org/html/rfc6749) protocol for Bing Ads API authentication. As an application developer you'll use a Microsoft authorization URL to prompt the Microsoft Advertising user for consent. Once a user provides consent, you can get an access token and act on behalf of the user. A developer token is also required for authentication. For more information, see the [Get Started](get-started.md) guide. 

> [!TIP]
> To get access and refresh tokens for your Microsoft Advertising user and make your first service call using the Bing Ads API, see the [Quick Start](get-started.md#quick-start).  
> 
> If you are using one of the Bing Ads SDKs the tokens will be refreshed automatically. For details about how to get access and refresh tokens using the Bing Ads SDKs, see [Authentication With the SDKs](sdk-authentication.md#oauth).  

1. [Register](#registerapplication) your application.

1. [Request user consent](#request-userconsent) for your application to manage their Microsoft Advertising accounts.  

1. [Request an access token](#request-accesstoken)  

1. [Use the access token](#use-accesstoken) in calls to the Bing Ads API.  

1. [Refresh the access token](#refresh-accesstoken)   

## <a name="registerapplication"></a>Register Your Application
Before you can manage authentication for users of your Bing Ads API application, you must register your application and get the corresponding client ID and client secret.  

1. Navigate to the Microsoft identity platform for developers in the [Azure portal - App registrations](https://go.microsoft.com/fwlink/?linkid=2083908) page. You can login using either a personal Microsoft Account or a Work or School Account.

   > [!NOTE]
   > Live SDK application IDs with the short hexadecimal format e.g., 0000000012345A67 are not supported with the Microsoft identity platform endpoint. Although [Live Connect](authentication-oauth-live-connect.md) integration (login.live.com) is no longer the recommended approach, you can still view and manage Live SDK applications at [https://apps.dev.microsoft.com/](https://apps.dev.microsoft.com/). If you don't see an existing app in the Azure portal, that's an indication that you should replace it with a new app. 

1. Select **New registration**. 
1. When the **Register an application page** appears, enter your application's registration information: 
    - In the **Name** section, enter a meaningful application name that will be displayed to users of the app, for example `My browserless client`. 
    - In the **Supported account types** section, select **Accounts in any organizational directory and personal Microsoft accounts**. 

    ![Supported account types](media/supported-account-types.png "Supported account types")  

    > [!IMPORTANT]
    > You must select **Accounts in any organizational directory and personal Microsoft accounts** during the initial app registration. This setting cannot be updated later in the portal unless you modify the [application manifest](https://docs.microsoft.com/azure/active-directory/develop/reference-app-manifest) e.g., ```"signInAudience": "AzureADandPersonalMicrosoftAccount"```.  

1. Select **Register** to create the application. 
1. On the app **Overview** page, find the **Application (client) ID** value and record it for later. You will use it as the `client_id` when [requesting access tokens](#request-accesstoken).  
1. Select the **Add a Redirect URI** link and then you should see the **Redirect URIs** page. 
   - For web applications, provide the base URL of your application. For example, http://localhost:31544 might be the URL for a web application running on your local machine. Users would use this URL to sign into a web client application.  
   - For public applications, locate the **Suggested Redirect URIs for public clients (mobile, desktop)** section. Select the **https://login.live.com/oauth20_desktop.srf** URI. 
   
    > [!IMPORTANT]
    > Clients running apps on services that span regions and devices such as Microsoft Azure should register a web application with client secret. You can get a refresh token on one device and refresh it on another so long as you have the same client ID and client secret. If you register a public application without a client secret, then you cannot use a refresh token across devices. A confidential token is bound to the client secret. 

1. For web applications, select **Certificates & secrets** under **Manage**. Select the **New client secret** button. Enter a value in **Description**, select any option for **Expires** and choose **Add**. Copy the client secret value before leaving the page. You will use it as the `client_secret` when [requesting access tokens](#request-accesstoken). 

## <a name="request-userconsent"></a>Request User Consent
Each user must be prompted and provide consent through a web browser control at least once for your application to manage their Microsoft Advertising accounts. 

For repeat or long term authentication, you should follow the authorization code grant flow for obtaining an access token. This is a standard OAuth 2.0 flow and is defined in detail in the [Authorization Code Grant section of the OAuth 2.0 spec](https://tools.ietf.org/html/rfc6749#section-4.1). The authorization code flow begins with the client directing the user to the `/authorize` endpoint. In this request, the client indicates the permissions it needs to acquire from the user:

```https
https://login.live.com/oauth20_authorize.srf?client_id=CLIENT_ID&scope=bingads.manage&response_type=code&redirect_uri=REDIRECTURI&state=ClientStateGoesHere
```

> [!IMPORTANT]
> For apps that target the [sandbox](sandbox.md) environment, use *login.live-int.com* instead of *login.live.com*.  

The following table describes parameters that you should include in the request. 

|Parameter|Required/Optional|Description|
|--------------|-------------|--------------|
|`client_id`|required|The application (client) ID that the [Azure portal - App registrations](https://go.microsoft.com/fwlink/?linkid=2083908) portal (or [https://apps.dev.microsoft.com/](https://apps.dev.microsoft.com/) for Live SDK) assigned your app.|
|`display`|optional|The display type to be used for the authorization page. Valid values are "popup", "touch", "page", or "none".|  
|`response_type`|required|Must include `code` for the authorization code flow.|
|`redirect_uri`|required|The redirect_uri of your app, where authentication responses can be sent and received by your app. It must exactly match one of the redirect_uris you [registered](#registerapplication) in the portal, except it must be url encoded. For native & mobile apps, you should use the default value of `https://login.live.com/oauth20_desktop.srf`.|
|`scope`|required|A space-separated list of scopes that you want the user to consent to. Be sure to include `bingads.manage` to prompt the user for Microsoft Advertising access.|
|`state`|recommended|A value included in the request that will also be returned in the token response. It can be a string of any content that you wish. A randomly generated unique value is typically used for [preventing cross-site request forgery attacks](https://tools.ietf.org/html/rfc6749#section-10.12). The value can also encode information about the user's state in the app before the authentication request occurred, such as the page or view they were on.|

At this point, the user will be asked to enter their credentials and complete the authentication. The authorization endpoint will also ensure that the user has consented to the permissions indicated in the `scope` query parameter. If the user has not consented to any of those permissions, it will ask the user to consent to the required permissions. 

Once the user authenticates and grants consent, the authorization endpoint will return a response to your app at the indicated `redirect_uri`, using the method specified in the `response_mode` parameter. For example the callback URI includes an authorization code as follows if the user granted permissions for your application to manage their Microsoft Advertising accounts: *https://login.live.com/oauth20_desktop.srf?code=CodeGoesHere&state=ClientStateGoesHere*. Users can revoke your application's access to their accounts at [https://account.live.com/consent/Manage](https://account.live.com/consent/Manage).

If the user granted your application permissions to manage their Microsoft Advertising accounts, you should use the code right away in the next step. The short duration of the authorization code, approximately 5 minutes, is subject to change. If the user denied your application permissions to manage their Microsoft Advertising accounts, the callback URI includes an error and error description field as follows: *REDIRECTURI?error=access_denied&error_description=ERROR_DESCRIPTION&state=ClientStateGoesHere*.

## <a name="request-accesstoken"></a>Request an access token

Now that you've acquired an authorization_code and have been granted permission by the user, you can redeem the `code` for an `access_token` to the desired resource. Do this by sending a `POST` request to the `/oauth20_token.srf` endpoint:

```https
POST https://login.live.com/oauth20_token.srf HTTP/1.1
Accept: application/json
Content-Type: application/x-www-form-urlencoded
Host: login.live.com
Content-Length: ContentLengthGoesHere

client_id=ClientIdGoesHere&scope=bingads.manage&code=CodeGoesHere&grant_type=authorization_code&redirect_uri=https%3A%2F%2Flogin.live.com%2Foauth20_desktop.srf
```

The body of the request must include the request parameters and the Content-Type header must be set to *application/x-www-form-urlencoded*. Set the code parameter to the value of the authorization code retrieved in the previous step, and the grant type set to *authorization_code*. The *redirect_uri* must exactly match the redirect URI used to obtain the authorization code. Be sure to encode the redirect URL. If you registered a web application, include the *client_secret* parameter and set it to the value provisioned in [Register Your Application](#registerapplication).

> [!IMPORTANT]
> For apps that target the [sandbox](sandbox.md) environment, use *login.live-int.com* instead of *login.live.com*.  

The following table describes parameters that you should include in the request. 

|Parameter|Required/Optional|Description|
|------------|-------------------|----------------|
|`client_id`|required|The application (client) ID that the [Azure portal - App registrations](https://go.microsoft.com/fwlink/?linkid=2083908) portal (or [https://apps.dev.microsoft.com/](https://apps.dev.microsoft.com/) for Live SDK) assigned your app.|
|`grant_type`|required|Must be `authorization_code` for the authorization code flow.|
|`scope`|required|A space-separated list of scopes. The scopes requested in this leg must be equivalent to or a subset of the scopes included when you [requested user consent](#request-userconsent). If the scopes specified in this request span multiple resource servers, then the authorization endpoint will return a token for the resource specified in the first scope.|
|`code`|required|The authorization_code that you acquired as a result of [requesting user consent](#request-userconsent).|
|`redirect_uri`|required|The same redirect_uri value that was used to acquire the authorization_code.|
|`client_secret`|required for web apps|The application secret that you created in the app registration portal for your app. It should not be used in a native app, because client_secrets cannot be reliably stored on devices. It is required for web apps and web APIs, which have the ability to store the client_secret securely on the server side. The client secret must be URL-encoded before being sent.|   

The following table describes response parameters. 

|Parameter|Description|  
|---------|---------|
|`access_token`|Equivalent to the *access_token* parameter that is described in the [OAuth 2.0 spec](https://tools.ietf.org/html/rfc6749#appendix-A.12). To authenticate with Bing Ads API you will send the access token via the AuthenticationToken header element.| 
|`authentication_token`|The registered application's authentication token.|
|`code`|Equivalent to the *code* parameter that is described in the [OAuth 2.0 spec](https://tools.ietf.org/html/rfc6749#appendix-A.11).|
|`error`|Error code identifying the error that occurred.|
|`error_description`|A description of the error.|
|`expires_in`|Equivalent to the *expires_in* parameter that is described in the [OAuth 2.0 spec](https://tools.ietf.org/html/rfc6749#appendix-A.14).|
|`id_token`|An unsigned JSON Web Token (JWT). The app can base64Url decode the segments of this token to request information about the user who signed in. The app can cache the values and display them, but it should not rely on them for any authorization or security boundaries.|  
|`refresh_token`|Equivalent to the *refresh_token* parameter that is described in the [OAuth 2.0 spec](https://tools.ietf.org/html/rfc6749#appendix-A.17).| 
|`scope`|Equivalent to the *scope* parameter that is described in the [OAuth 2.0 spec](https://tools.ietf.org/html/rfc6749#appendix-A.4).|
|`state`|Equivalent to the *state* parameter that is described in the [OAuth 2.0 spec](https://tools.ietf.org/html/rfc6749#appendix-A.5). When you request an authorization code this value is passed through from the *state* request parameter, and you should receive the same value unchanged in the response.|
|`token_type`|The type of data to be returned in the response from the authorization server.| 

## <a name="use-accesstoken"></a> Use the access token

Get the *access_token*, *refresh_token*, and *expires_in* values from the JSON response stream. Now that you've successfully acquired an `access_token`, you can [use](get-started.md#quick-start) the token in requests to Bing Ads APIs by including it in the AuthenticationToken header. The value of *expires_in* represents the maximum time in seconds, until the access token will expire. Before the access token expires, you should request a new access token as discussed in the next step. 

## <a name="refresh-accesstoken"></a> Refresh the access token

Access_tokens are short lived, and you must refresh them after they expire to continue accessing resources. You can do so by submitting another `POST` request to the `/oauth20_token.srf` endpoint, this time providing the `refresh_token` instead of the `code`.  Refresh tokens are valid for all permissions that your client has already received consent.    

Refresh tokens do not have specified lifetimes. Typically, the lifetimes of refresh tokens are relatively long. However, in some cases, refresh tokens expire, are revoked, or lack sufficient privileges for the desired action. Your application needs to expect and handle errors returned by the token issuance endpoint correctly. 

```https
POST https://login.live.com/oauth20_token.srf HTTP/1.1
Accept: application/json
Content-Type: application/x-www-form-urlencoded
Host: login.live.com
Content-Length: ContentLengthGoesHere

client_id=ClientIdGoesHere&scope=bingads.manage&grant_type=refresh_token&refresh_token=RefreshTokenGoesHere
```

The body of the request must include the request parameters and the Content-Type header must be set to *application/x-www-form-urlencoded*. Set the refresh token parameter to the value of the refresh token retrieved in the previous step, and the grant type set to *refresh_token*. If you registered a web application, include the *client_secret* parameter and set it to the value provisioned in [Register Your Application](#registerapplication).

> [!IMPORTANT]
> For apps that target the [sandbox](sandbox.md) environment, use *login.live-int.com* instead of *login.live.com*.  

The following table describes parameters that you should include in the request. 

|Parameter|Required/Optional|Description|
|---------------|----------------|--------------------|
|`client_id`|required|The application (client) ID that the [Azure portal - App registrations](https://go.microsoft.com/fwlink/?linkid=2083908) portal (or [https://apps.dev.microsoft.com/](https://apps.dev.microsoft.com/) for Live SDK) assigned your app.|
|`grant_type`|required|Must be `refresh_token` for this leg of the authorization code flow.|
|`scope`|required|A space-separated list of scopes. The scopes requested in this leg must be equivalent to or a subset of the scopes included when you [requested user consent](#request-userconsent). If the scopes specified in this request span multiple resource servers, then the authorization endpoint will return a token for the resource specified in the first scope.|
|`refresh_token`|required|The refresh_token that you acquired in the second leg of the flow.|
|`client_secret`|required for web apps|The application secret that you created in the app registration portal for your app. It should not be used in a native  app, because client_secrets cannot be reliably stored on devices. It is required for web apps and web APIs, which have the ability to store the client_secret securely on the server side.        

Although refresh tokens are not revoked when used to acquire new access tokens, you are expected to discard the old refresh token. The [OAuth 2.0 spec](https://tools.ietf.org/html/rfc6749#section-6) says: "The authorization server MAY issue a new refresh token, in which case the client MUST discard the old refresh token and replace it with the new refresh token. The authorization server MAY revoke the old refresh token after issuing a new refresh token to the client."  

Refresh tokens are, and always will be, completely opaque to your application. They are long-lived e.g., 90 days for public clients, but the app should not be written to expect that a refresh token will last for any period of time. Refresh tokens can be invalidated at any moment, and the only way for an app to know if a refresh token is valid is to attempt to redeem it by making a token request. Even if you continuously refresh the token on the same device with the most recent refresh token, you should expect to start again and [request user consent](#request-userconsent) if for example, the Microsoft Advertising user changed their password, removed a device from their list of trusted devices, or removed permissions for your application to authenticate on their behalf. At any time without prior warning Microsoft may determine that user consent should again be granted. In that case, the authorization service would return an invalid grant error as shown in the following example.

```json
{"error":"invalid_grant","error_description":"The user could not be authenticated or the grant is expired. The user must first sign in and if needed grant the client application access to the requested scope."}
```

Please keep in mind that public refresh tokens are only bound to the granted device. For example if you registered a Native app and use https://login.live.com/oauth20_desktop.srf as the redirect URI, we only guarantee that it can be refreshed on the same device. Clients running apps on services that span regions and devices such as Microsoft Azure should register a Web app with client secret. The redirect URI can be localhost but cannot be https://login.live.com/oauth20_desktop.srf. If you use https://login.live.com/oauth20_desktop.srf with a client secret the following error would be returned.

```json
{"error":"invalid_request","error_description":"Public clients can't send a client secret."} Likewise for Web apps please note that refresh tokens can be invalidated at any moment.
```

You will encounter the same error if you try to request new access and refresh tokens using a refresh token that was provisioned without a client secret. 

## See Also
[Bing Ads API Web Service Addresses](web-service-addresses.md)

