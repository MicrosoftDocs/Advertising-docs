---
title: "Authentication with OAuth"
ms.service: "bing-ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Authenticate for Bing Ads API using OAuth.
---
# Authentication with OAuth

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
> The new ```msads.manage``` scope **requires renewed consent from all users of your application**. You must prompt users for consent using the new ```msads.manage``` scope after they have turned on multi-factor authentication. We recommend that you inform and guide users of your application to [set up MFA](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time#who-decides-if-you-use-this-feature) right away.

Consider the user that you want to sign in e.g., example@contoso.com. The Bing Ads API will not accept the email address and password as plain text, rather when you call the Bing Ads API you need to set the AuthenticationToken header element that contains a user access token. 

How can you get an access token? Microsoft Advertising leverages the [Microsoft identity platform endpoint for developers](authentication-oauth-identity-platform.md) and the [OAuth 2.0](https://tools.ietf.org/html/rfc6749) protocol for Bing Ads API authentication. As an application developer you'll use a Microsoft authorization URL to prompt the Microsoft Advertising user for consent. Once a user provides consent, you can get an access token and act on behalf of the user. A developer token is also required for authentication. For more information, see the [Get Started](get-started.md) guide. 

> [!TIP]
> To get access and refresh tokens for your Microsoft Advertising user and make your first service call using the Bing Ads API, see the [Quick Start](get-started.md#quick-start).
> 
> For details about how to get access and refresh tokens using the Bing Ads SDKs, see [Authentication With the SDKs](sdk-authentication.md#oauth).  

## <a name="faq"></a>OAuth General FAQ

### Q. I want to run my application without user interaction. How can I authenticate without getting prompted for permission to use Microsoft Advertising credentials?
To programmatically manage a Microsoft Advertising account, you must provide consent at least once through the web application consent flow. For repeat or long term authentication, you should follow the authorization code grant flow for obtaining an access token and refresh token. Thereafter you can use the latest refresh token to request new access and refresh tokens without any further user interaction. You may need to request user consent again for example, if the user went through account recovery, changed their password, or otherwise removed permissions for your application to authenticate on their behalf. 

### Q. When do the access and refresh tokens expire?
The access token typically expires after one hour, although you should always check the expiration time each time you request a new token. 

Refresh tokens are, and always will be, completely opaque to your application. They are long-lived e.g., 90 days for public clients, but the app should not be written to expect that a refresh token will last for any period of time. Refresh tokens can be invalidated at any moment, and the only way for an app to know if a refresh token is valid is to attempt to redeem it by making a token request. Even if you continuously refresh the token on the same device with the most recent refresh token, you should expect to start again and request user consent if for example, you signed the user out, the Microsoft Advertising user changed their password, removed a device from their list of trusted devices, or removed permissions for your application to authenticate on their behalf. At any time without prior warning Microsoft may determine that user consent should again be granted. As a best practice you should always securely store the latest refresh token each time you request new access and refresh tokens. 

### Q. Why do I need an access token and developer token?
The access token represents the user credentials who has access to one or more Microsoft Advertising accounts. The application ID (a.k.a. client_id) identifies your application for each Microsoft Advertising user who grants consent. The developer token gives your application permission to use the Bing Ads API. 

## <a name="upgrade-identity-platform-faq"></a>Upgrade to the Microsoft identity platform endpoint FAQ

### Q. Why should I upgrade to the Microsoft identity platform endpoint? 

Microsoft Advertising customers in the Azure Active Directory credentials (AAD) pilot ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 567) can sign in with either work or school accounts from Azure AD or personal Microsoft accounts (MSA), such as hotmail.com, outlook.com, and msn.com. Only the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) (v2.0) allows you to obtain access tokens to authenticate both work and personal accounts via the Bing Ads API. To ensure that your application can support all users without friction or interruption of service, you should upgrade to the Microsoft identity platform endpoint in production.  

Even if the current users of your application do not have work or school accounts, please upgrade to the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) now, since the Live Connect endpoint is no longer the recommended approach for Microsoft Advertising users. The Bing Ads SDKs version 12.13.2 and later use the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) by default. For details see [Upgrade to the Microsoft identity platform endpoint FAQ](authentication-oauth.md#upgrade-identity-platform-faq) and [Authentication with the Microsoft identity platform endpoint](authentication-oauth-identity-platform.md).  

### Q. If I don't want to support work or school accounts, do I need to make any changes?

We recommend all clients upgrade to the new [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md). The Microsoft identity platform endpoint supports both work and personal accounts. The Bing Ads SDKs version 12.13.2 and later use the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) by default. 

### Q. What changes are required for my application to support work or school accounts via the API?

There are one or more steps depending on your current app registration: 
- Use the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) for access and refresh token requests. The Microsoft identity platform endpoint supports both work and personal accounts.  
- If you have an older application ID (aka Client ID) that is formatted as a hexadecimal value e.g., 0000000012345A67, then you must register a new application. Valid Microsoft identity platform application IDs are formatted as a GUID with dashes e.g., ab01c23d-4e56-7f8a-90bc-1d23efabc45d. If you don't see an existing app in the [Azure portal - App registrations](https://go.microsoft.com/fwlink/?linkid=2083908), that's an indication that you should replace it with a new app. If you use a new application ID, then you must prompt users again for consent to manage their accounts. To continue using the older application ID with Bing Ads SDKs version 12.13.2 and later, you'll need to set the "require live connect" property of each OAuth object. 
- Handle [operation error codes](operation-error-codes.md) 122 through 125 to help users of your application select the correct credentials i.e., work versus personal account.  

### Q. Does a user need to grant consent after my app upgrades to the Microsoft identity platform endpoint?

Yes. Even if the user had a Microsoft account when you obtained their access and refresh token, and has not switched to a work or school account, each user who you want to authenticate via the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) will need to grant consent again for your app to access and update their Microsoft Advertising info.

If you use a new application ID (aka Client ID), then you must prompt users again for consent to manage their accounts. That is the case for any new application ID, whether or not you are switching endpoints. Even if you use the same application ID and if you have a valid refresh token for the user, renewed consent is required because the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) requires scope set to `https://ads.microsoft.com/ads.manage` and the [Live Connect](authentication-oauth-live-connect.md) endpoint requires scope set to `bingads.manage`. Since user consent is tied to the scope, you'll need to get user consent before you can obtain their access token with the new endpoint.  

### Q. What is the user experience after my app upgrades to the Microsoft identity platform endpoint?

When you prompt the user for consent using the common tenant within the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) i.e., `https://sign in.microsoftonline.com/common/oauth2/v2.0/authorize` the user sign in experience will vary depending on the underlying identity behind their credentials.  
- A person who only has an MSA identity will be directed to the MSA sign in page.  
- A person who only has an Azure AD identity will be directed to their organizational sign in page.  
- A person whose credentials are valid in both the MSA and the Azure AD domains will encounter a disambiguation page that asks them to choose between their personal and their work or school identity. This disambiguation will always be present so long as this user has two identities tied to the same email address. The user can stop seeing this by [changing the email address of their personal Microsoft account](https://support.microsoft.com/help/11545/microsoft-account-change-personal-email-address). For more information see [https://cloudblogs.microsoft.com/enterprisemobility/2016/09/15/cleaning-up-the-azure-ad-and-microsoft-account-overlap/](https://cloudblogs.microsoft.com/enterprisemobility/2016/09/15/cleaning-up-the-azure-ad-and-microsoft-account-overlap/).  

### Q. When a user switches from using their personal account to their work or school account in Microsoft Advertising, what happens to their refresh token?

If the user no longer has an MSA personal account identity, then Bing Ads API will no longer accept their existing access token. Likewise, the refresh token can no longer be used to request a new access token, so you'll need to request user consent again for your application to manage their Microsoft Advertising accounts. You should discard the previous refresh token.  

### Q. Are work or school accounts only supported with Bing Ads API Version 13?

Work or school accounts are not tied to a specific Bing Ads API version. A Microsoft Advertising user access tokens obtained using the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) can be used in production with all supported versions of the Bing Ads API. 

### Q. Will the Bing Ads SDKs support the Microsoft identity platform endpoint?  

The Bing Ads SDKs version 12.13.2 and later use the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) by default. To continue using an older application ID (aka Client ID) that is formatted as a hexadecimal value e.g., 0000000012345A67 via the [Live Connect endpoint](authentication-oauth-live-connect.md), you'll need to set the "require live connect" property of each OAuth object. 

### Q. Will sandbox support work or school accounts?

No. Work or school accounts are only supported in production with the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md). The [Live Connect endpoint](authentication-oauth-live-connect.md) is supported for personal accounts in sandbox.  

## See Also
[Authentication With the SDKs](sdk-authentication.md)
