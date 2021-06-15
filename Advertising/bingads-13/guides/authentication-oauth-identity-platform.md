---
title: "Get access and refresh tokens"
ms.service: "bing-ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Get access and refresh tokens using the Microsoft identity platform endpoint for developers.
---
# Get access and refresh tokens

[!INCLUDE[request-header](./includes/mfa-required.md)]

Once a user has granted consent for you to manage their Microsoft Advertising account, you can redeem the authorization ``code`` for an access token.  

> [!TIP]
> For troubleshooting help, see the [Common OAuth errors](handle-service-errors-exceptions.md#common-oauth-errors) guide.

## <a name="request-accesstoken"></a>Request an access token

You can redeem the `code` for an `access_token` to the desired resource. Do this by sending a `POST` request to the `/token` endpoint:

```https
// Line breaks for legibility only

POST /{tenant}/oauth2/v2.0/token HTTP/1.1
Host: https://login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

client_id=6731de76-14a6-49ae-97bc-6eba6914391e
&scope=https%3A%2F%2Fads.microsoft.com%2Fmsads.manage
&code=OAAABAAAAiL9Kn2Z27UubvWFPbm0gLWQJVzCTE9UkP3pSx1aXxUjq3n8b2JRLk4OxVXr...
&redirect_uri=http%3A%2F%2Flocalhost%2Fmyapp%2F
&grant_type=authorization_code
&client_secret=JqQX2PNo9bpM0uEihUPzyrh    // NOTE: Only applicable for web apps
```

The body of the request must include the request parameters and the Content-Type header must be set to *application/x-www-form-urlencoded*. Set the code parameter to the value of the authorization code retrieved in the previous step, and the grant type set to *authorization_code*. The *redirect_uri* must exactly match the redirect URI used to obtain the authorization code. Be sure to encode the redirect URL. If you registered a web application, include the *client_secret* parameter and set it to the value provisioned in [Register an application](authentication-oauth-register.md).

The following table includes parameters that Bing Ads API clients should include in the request. For additional details about optional parameters see the Microsoft identity platform [OAuth 2.0 authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-auth-code-flow) documentation. 

|Parameter|Required/Optional|Description|
|------------|-------------------|----------------|
|`client_id`|required|The application (client) ID that the [Azure portal - App registrations](https://go.microsoft.com/fwlink/?linkid=2083908) portal assigned your app.|
|`client_secret`|required for web apps|The application secret that you created in the app registration portal for your app. It should not be used in a native app, because client_secrets cannot be reliably stored on devices. It is required for web apps and web APIs, which have the ability to store the client_secret securely on the server side.  The client secret must be URL-encoded before being sent.|
|`code`|required|The authorization_code that you acquired as a result of [requesting user consent](#request-userconsent).|
|`code_verifier`|recommended|The same code_verifier that was used to obtain the authorization_code. Required if PKCE was used in the authorization code grant request. For more information, see the [PKCE RFC](https://tools.ietf.org/html/rfc7636).|
|`grant_type`|required|Must be `authorization_code` for the authorization code flow.|
|`redirect_uri`|required|The same redirect_uri value that was used to acquire the authorization_code.|
|`scope`|required|A space-separated list of scopes. The scopes requested in this leg must be equivalent to or a subset of the scopes included when you [requested user consent](#request-userconsent). If the scopes specified in this request span multiple resource servers, then the Microsoft identity platform endpoint will return a token for the resource specified in the first scope. For a more detailed explanation of scopes, refer to [permissions, consent, and scopes](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent).|
|`tenant`|required|The `{tenant}` value in the path of the request can be used to control who can sign into the application. To ensure that your application supports both MSA personal accounts and Azure AD work or school accounts, we suggest that you use `common` as the tenant for Bing Ads API authentication.<br/><br/>In case your application requires another tenant, see [Microsoft identity platform endpoints](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols#endpoints) for more information.|

## <a name="use-accesstoken"></a>Use the access token

Get the *access_token*, *refresh_token*, and *expires_in* values from the JSON response stream. Now that you've successfully acquired an `access_token`, you can [use](../authentication-oauth-quick-start.md) the token in requests to Bing Ads APIs by including it in the AuthenticationToken header. The value of *expires_in* represents the maximum time in seconds, until the access token will expire. Before the access token expires, you should request a new access token as discussed in the next step. 

## <a name="refresh-accesstoken"></a>Refresh the access token

Access tokens are short lived, and you must refresh them after they expire to continue accessing resources. You can do so by submitting another `POST` request to the `/token` endpoint, this time providing the `refresh_token` instead of the `code`.  Refresh tokens are valid for all permissions that your client has already received consent.  

Refresh tokens do not have specified lifetimes. Typically, the lifetimes of refresh tokens are relatively long. However, in some cases, refresh tokens expire, are revoked, or lack sufficient privileges for the desired action. Your application needs to expect and handle errors returned by the token issuance endpoint correctly. For more details about OAuth errors, please see [Common OAuth Errors](handle-service-errors-exceptions.md#common-oauth-errors) and [Authentication and authorization error codes](https://docs.microsoft.com/azure/active-directory/develop/reference-aadsts-error-codes). 

```https
// Line breaks for legibility only

POST /{tenant}/oauth2/v2.0/token HTTP/1.1
Host: https://login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

client_id=6731de76-14a6-49ae-97bc-6eba6914391e
&scope=https%3A%2F%2Fads.microsoft.com%2Fmsads.manage
&refresh_token=OAAABAAAAiL9Kn2Z27UubvWFPbm0gLWQJVzCTE9UkP3pSx1aXxUjq...
&grant_type=refresh_token
&client_secret=JqQX2PNo9bpM0uEihUPzyrh      // NOTE: Only applicable for web apps
```

The body of the request must include the request parameters and the Content-Type header must be set to *application/x-www-form-urlencoded*. Set the refresh token parameter to the value of the refresh token retrieved in the previous step, and the grant type set to *refresh_token*. If you registered a web application, include the *client_secret* parameter and set it to the value provisioned in [Register an application](authentication-oauth-register.md).

The following table includes parameters that Bing Ads API clients should include in the request. For additional details about optional parameters see the Microsoft identity platform [OAuth 2.0 authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-auth-code-flow) documentation. 

|Parameter|Required/Optional|Description|
|---------------|----------------|--------------------|
|`client_id`|required|The application (client) ID that the [Azure portal - App registrations](https://go.microsoft.com/fwlink/?linkid=2083908) portal assigned your app.|
|`client_secret`|required for web apps|The application secret that you created in the app registration portal for your app. It should not be used in a native  app, because client_secrets cannot be reliably stored on devices. It is required for web apps and web APIs, which have the ability to store the client_secret securely on the server side.|
|`grant_type`|required|Must be set to `refresh_token` for this leg of the authorization code flow.|
|`refresh_token`|required|The refresh_token that you acquired when you [requested an access token](#request-accesstoken).|
|`scope`|required|A space-separated list of scopes. The scopes requested in this leg must be equivalent to or a subset of the scopes included when you [requested user consent](#request-userconsent). If the scopes specified in this request span multiple resource servers, then the Microsoft identity platform endpoint will return a token for the resource specified in the first scope. For a more detailed explanation of scopes, refer to [permissions, consent, and scopes](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent).|
|`tenant`|required|The `{tenant}` value in the path of the request can be used to control who can sign into the application. To ensure that your application supports both MSA personal accounts and Azure AD work or school accounts, we suggest that you use `common` as the tenant for Bing Ads API authentication.<br/><br/>In case your application requires another tenant, see [Microsoft identity platform endpoints](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols#endpoints) for more information.|

Although refresh tokens are not revoked when used to acquire new access tokens, you are expected to discard the old refresh token. The [OAuth 2.0 spec](https://tools.ietf.org/html/rfc6749#section-6) says: "The authorization server MAY issue a new refresh token, in which case the client MUST discard the old refresh token and replace it with the new refresh token. The authorization server MAY revoke the old refresh token after issuing a new refresh token to the client."  

Refresh tokens are, and always will be, completely opaque to your application. They are long-lived e.g., 90 days for public clients, but the app should not be written to expect that a refresh token will last for any period of time. Refresh tokens can be invalidated at any moment, and the only way for an app to know if a refresh token is valid is to attempt to redeem it by making a token request. Even if you continuously refresh the token on the same device with the most recent refresh token, you should expect to start again and [request user consent](#request-userconsent) if for example, the Microsoft Advertising user changed their password, removed a device from their list of trusted devices, or removed permissions for your application to authenticate on their behalf. At any time without prior warning Microsoft may determine that user consent should again be granted. In that case, the authorization service would return an invalid grant error as shown in the following example.

```json
{"error":"invalid_grant","error_description":"The user could not be authenticated or the grant is expired. The user must first sign in and if needed grant the client application access to the requested scope."}
```

Please keep in mind that public refresh tokens are only bound to the granted device. For example if you registered a Native app and use `https://login.microsoftonline.com/common/oauth2/nativeclient` as the redirect URI, we only guarantee that it can be refreshed on the same device. Clients running apps on services that span regions and devices such as Microsoft Azure should register a Web app with client secret. The redirect URI can be localhost but cannot be `https://login.microsoftonline.com/common/oauth2/nativeclient`. If you use `https://login.microsoftonline.com/common/oauth2/nativeclient` with a client secret the following error would be returned.

```json
{"error":"invalid_request","error_description":"Public clients can't send a client secret."} Likewise for Web apps please note that refresh tokens can be invalidated at any moment.
```

You will encounter the same error if you try to request new access and refresh tokens using a refresh token that was provisioned without a client secret. For more details about OAuth errors, please see [Common OAuth Errors](handle-service-errors-exceptions.md#common-oauth-errors) and [Authentication and authorization error codes](https://docs.microsoft.com/azure/active-directory/develop/reference-aadsts-error-codes). 


## Next steps

> [!div class="nextstepaction"]
> [Make your first API call](../authentication-oauth-quick-start.md)

## See Also
[Get started](get-started.md)