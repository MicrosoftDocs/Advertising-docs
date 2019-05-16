---
title: "Authentication with OAuth"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Authenticate for Bing Ads API using OAuth.
---
# Authentication with OAuth
Consider the user that you want to sign in e.g., example@contoso.com. The Bing Ads API will not accept the email address and password as plain text, rather when you call the Bing Ads API you need to set the AuthenticationToken header element that contains a user access token. How can you get an access token? Microsoft Advertising leverages the Microsoft identity platform for developers and the [OAuth 2.0](http://tools.ietf.org/html/rfc6749) protocol for Bing Ads API authentication. As an application developer you'll use a Microsoft authorization URL to prompt the Microsoft Advertising user for consent, or to prompt yourself for consent if you are developing an application for your own accounts. Once the user provides consent, you can then obtain an access token and act on behalf of the user. 

> [!NOTE]
> A developer token is also required for authentication. Customer and account identifiers are also required for most service operations. For more information, see [Get Started With the Bing Ads API](get-started.md). 
> 
> To authenticate a Microsoft Advertising user in sandbox, see [Get Sandbox Access](sandbox.md#access) and [Live Connect endpoint](authentication-oauth-live-connect.md).   

During calendar year 2019 Microsoft Advertising will begin to allow login via Azure Active Directory credentials (AAD) as an alternative to Microsoft Account credentials (MSA) login. The AAD credentials function much the same way as MSA credentials, but they are governed by organizations. For example, all @microsoft.com email addresses are controlled by Microsoft IT admins, so that they can set individual user permissions and can control the way users log into various platforms (e.g. require Two-Factor Authentication). 

Here are some of the reasons that either you or users of your application might sign in with Azure AD credentials: 
- Additional control over whether past employees can access Microsoft Advertising accounts. If a person leaves a company their Microsoft Advertising access can be removed by the Azure AD admin. As before the user could be manually deleted from Microsoft Advertising.   
- Auditing and agency-wide policies over who has access to customer's accounts. Some companies have corporate authentication mandates, where they discourage or even forbid their employees from accessing company information using personal accounts. External auditors sometimes rule the use of personal accounts to access company information as non-compliant.  
- Avoid confusion and unexpected conflicts between work, school, and personal accounts. Without an explicit Azure AD option some users might create personal accounts without realizing this is what they are doing, leading to confusion between their accounts down the road.  
- Users who have an email address in the Azure AD domain will not be able to use Microsoft Advertising with a personal identity.  

Only the Microsoft identity platform endpoint (v2.0) allows both work or school accounts from Azure AD and personal Microsoft accounts (MSA), such as hotmail.com, outlook.com, and msn.com. To ensure that your application can support all users, you should use the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) in production.

> [!IMPORTANT]
> The Bing Ads SDKs version 12.13.2 and later use the [Microsoft identity platform endpoint](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-overview) by default. Even if your users do not have work or school accounts, and even if you do not use the Bing Ads SDKs we encourage you to update the authorization URL during calendar year 2019, since the [Live Connnect endpoint](authentication-oauth-live-connect.md) is no longer the recommended approach for Microsoft Advertising users. For details see [Upgrade to the Microsoft identity platform endpoint FAQ](#upgrade-identity-platform-faq) and [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md).  

> [!TIP]
> To get access and refresh tokens for your Microsoft Advertising user and make your first service call using the Bing Ads API, see the [Quick Start](get-started.md#quick-start) sample.
> 
> For details about how to get access and refresh tokens using the Bing Ads SDKs, see [Authentication With the SDKs](sdk-authentication.md#oauth).  

## <a name="faq"></a>OAuth General FAQ

### Q. I want to run my application without user interaction. How can I authenticate without getting prompted for permission to use Microsoft Advertising credentials?
To programatically manage a Microsoft Advertising account, you must provide consent at least once through the web application consent flow. For repeat or long term authentication, you should follow the authorization code grant flow for obtaining an access token and refresh token. Thereafter you can use the latest refresh token to request new access and refresh tokens without any further user interaction. You may need to request user consent again for example, if the user went through account recovery, changed their password, or otherwise removed permissions for your application to authenticate on their behalf. 

### Q. When do the access and refresh tokens expire?
The access token typically expires after one hour, although you should always check the expiration time each time you request a new token. 

Refresh tokens are, and always will be, completely opaque to your application. They are long-lived e.g., 90 days for public clients, but the app should not be written to expect that a refresh token will last for any period of time. Refresh tokens can be invalidated at any moment, and the only way for an app to know if a refresh token is valid is to attempt to redeem it by making a token request. Even if you continuously refresh the token on the same device with the most recent refresh token, you should expect to start again and request user consent if for example, you signed the user out, the Microsoft Advertising user changed their password, removed a device from their list of trusted devices, or removed permissions for your application to authenticate on their behalf. At any time without prior warning Microsoft may determine that user consent should again be granted. As a best practice you should always securely store the latest refresh token each time you request new access and refresh tokens. 

### Q. Why do I need an access token and developer token?
The access token represents the user credentials who has access to one or more Microsoft Advertising accounts. The application ID (a.k.a. client_id) identifies your application for each Microsoft Advertising user who grants consent. The developer token gives your application permission to use the Bing Ads API. 

## <a name="upgrade-identity-platform-faq"></a>Upgrade to the Microsoft identity platform endpoint FAQ

### Q. Why should I upgrade to the Microsoft identity platform endpoint? 
Only the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) (v2.0) allows work or school accounts from Azure AD and personal Microsoft accounts (MSA), such as hotmail.com, outlook.com, and msn.com.  

### Q. If I don't want to support work or school accounts, do I need to make any changes?

We recommend all clients upgrade to the new [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) during calendar year 2019. The Microsoft identity platform endpoint supports both work and personal accounts. The Bing Ads SDKs version 12.13.2 and later use the [Microsoft identity platform endpoint](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-overview) by default. 

### Q. What changes are required for my application to support work or school accounts via the API?

There are one or more steps depending on your current app registration: 
- Use the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) for access and refresh token requests. The Microsoft identity platform endpoint supports both work and personal accounts.  
- If you have an older application ID (aka Client ID) that is formatted as a hexadecimal value e.g., 0000000012345A67, then you must register a new application. Valid Microsoft identity platform application IDs are formatted as a GUID with dashes e.g., ab01c23d-4e56-7f8a-90bc-1d23efabc45d. If you don't see an existing app in the [Azure portal - App registrations](https://go.microsoft.com/fwlink/?linkid=2083908), that's an indication that you should replace it with a new app. If you use a new application ID, then you must prompt users again for consent to manage their accounts. To continue using the older application ID with Bing Ads SDKs version 12.13.2 and later, you'll need to set the "require live connect" property of each OAuth object. 
- Handle [operation error codes](operation-error-codes.md) 122 through 125 to help users of your application select the correct credentials i.e., work versus personal account.  

### Q. Does a user need to grant consent after my app upgrades to the Microsoft identity platform endpoint?

Yes. Even if the user had a Microsoft account when you obtained their access and refresh token, and has not switched to a work or school account, each user who you want to authenticate via the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) will need to grant consent again for your app to access and update their Microsoft Advertising info.

If you use a new application ID (aka Client ID), then you must prompt users again for consent to manage their accounts. That is the case for any new application ID, whether or not you are switching endpoints. Even if you use the same application ID and if you have a valid refresh token for the user, renewed consent is required because the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) requires scope set to `https://ads.microsoft.com/ads.manage` and the [Live Connect](authentication-oauth-live-connect.md) endpoint requires scope set to `bingads.manage`. Since user consent is tied to the scope, you'll need to get user consent before you can obtain their access token with the new endpoint.  

### Q. What is the user experience after my app upgrades to the Microsoft identity platform endpoint?

When you prompt the user for consent using the common tenant within the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) i.e., `https://login.microsoftonline.com/common/oauth2/v2.0/authorize` the user sign in experience will vary depending on the underlying identity behind their credentials.  
- A person who only has an MSA identity will be directed to the MSA sign in page.  
- A person who only has an Azure AD identity will be directed to their organizational sign in page.  
- A person whose credentials are valid in both the MSA and the Azure AD domains will encounter a disambiguation page that asks them to choose between their personal and their work or school identity. This disambiguation will always be present so long as this user has two identities tied to the same email address. The user can stop seeing this by [changing the email address of their personal Microsoft account](https://support.microsoft.com/en-us/help/11545/microsoft-account-change-personal-email-address). For more information see [https://cloudblogs.microsoft.com/enterprisemobility/2016/09/15/cleaning-up-the-azure-ad-and-microsoft-account-overlap/](https://cloudblogs.microsoft.com/enterprisemobility/2016/09/15/cleaning-up-the-azure-ad-and-microsoft-account-overlap/).  

### Q. When a user switches from using their personal account to their work or school account in Microsoft Advertising, what happens to their refresh token?

If the user no longer has an MSA personal account identity, then Bing Ads API will no longer accept their existing access token. Likewise, the refresh token can no longer be used to request a new access token, so you'll need to request user consent again for your application to manage their Microsoft Advertising accounts. You should discard the previous refresh token.  

### Q. Are work or school accounts only supported with Bing Ads API Version 13?

Work or school accounts are not tied to any Bing Ads API version. A Microsoft Advertising user access tokens obtained using the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) can be used in production with all supported versions of the Bing Ads API.

### Q. Once I have upgraded to Bing Ads API Version 13, does my application automatically support work or school accounts?

Work or school account access is not enabled simply by upgrading to Bing Ads API Version 13. You'll also need to use the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) for access and refresh token requests.

### Q. Will the Bing Ads SDKs support the Microsoft identity platform endpoint?  

The Bing Ads SDKs version 12.13.2 and later use the [Microsoft identity platform endpoint](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-overview) by default. To continue using an older application ID (aka Client ID) that is formatted as a hexadecimal value e.g., 0000000012345A67 via the [Live Connnect endpoint](authentication-oauth-live-connect.md), you'll need to set the "require live connect" property of each OAuth object. 

### Q. Will sandbox support work or school accounts?

No. Work or school accounts are only supported in production with the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md). The [Live Connnect endpoint](authentication-oauth-live-connect.md) is supported for personal accounts in sandbox.  

## See Also
[Authentication With the SDKs](sdk-authentication.md)
