---
title: "Multi-factor authentication requirement"
ms.service: "bing-ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Details about the multi-factor authentication requirement for Bing Ads API.
dev_langs:
  - csharp
  - java
  - php
  - python
---
# Multi-factor authentication requirement

We already require multi-factor authentication in Microsoft Advertising online. Multi-factor authentication is a security process that requires you to verify your identity in two different ways.  

> [!IMPORTANT]
> Starting March 1st, 2022 we will require [multi-factor authentication](authentication-oauth-mfa.md) for all users who sign in through a third-party application that uses the Bing Ads API, Content API, and Hotel APIs.
>
> You must update your application to [get user consent](authentication-oauth-consent.md) using the new ```msads.manage``` scope. All application developers must take action to use the new scope.

The new ```msads.manage``` scope **requires renewed consent from all users of your application**. You must prompt users for consent using the new ```msads.manage``` scope whether or not they have turned on multi-factor authentication. This ensures that they provide a second form of identification or proof when granting consent to your application.  

## Action required

You must update your application and prompt users for consent using  ```msads.manage ``` scope via the Microsoft identity platform endpoint. All Microsoft Advertising developers must take action to use the new scope.  

With each API request we will check the access token to ensure the user granted consent via the new  ```msads.manage ``` scope. Upon enforcement of multi-factor authentication, any access token provisioned otherwise won’t be accepted.  

We recommend that you make the necessary changes as soon as possible.  

We also recommend that you inform and guide users of your application to [set up MFA](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time#who-decides-if-you-use-this-feature) so that a second proof will be required when they grant permissions for any application. For the Microsoft Advertising requirement, it isn't enough for them to turn on MFA. Either way you must get user consent by prompting with the ```msads.manage ``` scope. 

## After enforcement

Upon enforcement of MFA, we will only authenticate access tokens on behalf of a user who granted consent to your application via the ```msads.manage``` scope on the **Microsoft identity platform endpoint**.

- Prior to MFA enforcement the **Microsoft identity platform endpoint** supports the ```ads.manage``` scope. Access tokens that you acquire for users via the ads.manage scope will no longer be accepted.

- Prior to MFA enforcement the Live Connect endpoint supports the ```bingads.manage``` scope. The **Live Connect** endpoint is already deprecated and will no longer be supported. Access tokens that you acquire for users via the ```bingads.manage``` scope will no longer be accepted.


## SDK support 

Support for the new  ```msads.manage scope ``` is available starting with version 13.0.10 of  Bing Ads SDKs (.NET, Java, Python, and PHP).  

The new  ```msads.manage ``` scope is used by default. For backwards compatibility, until the enforcement date you can use the ```ads.manage ``` or  ```bingads.manage ``` scopes with a short workaround.  

```csharp
var oAuthDesktopMobileAuthCodeGrant = new OAuthDesktopMobileAuthCodeGrant(
    Settings.Default["ClientId"].ToString(),
    apiEnvironment,
    OAuthScope.ADS_MANAGE // temporary workaround; remove or use MSADS_MANAGE instead
);
```
```java
OAuthDesktopMobileAuthCodeGrant oAuthDesktopMobileAuthCodeGrant = new OAuthDesktopMobileAuthCodeGrant(
    ClientId, 
    ApiEnvironment,
    OAuthScope.ADS_MANAGE // temporary workaround; remove or use MSADS_MANAGE instead
);
```
```php
$authentication = (new OAuthDesktopMobileAuthCodeGrant())
    ->withClientId(ClientId)
    ->withEnvironment(ApiEnvironment)
    ->withOAuthScope(OAuthScope::ADS_MANAGE); // temporary workaround; remove or use MSADS_MANAGE instead
```
```python
oauth_web_auth_code_grant = OAuthDesktopMobileAuthCodeGrant(
    client_id=CLIENT_ID,
    env=ENVIRONMENT,
    oauth_scope="ads.manage" # temporary workaround; remove or use "msads.manage" instead
)
```

## See Also

[OAuth FAQ](faq.md#oauth)
[Request user consent](authentication-oauth-consent.md)
