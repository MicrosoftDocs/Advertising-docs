---
title: "Get Started with the Hotel API"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "scottwhi"
---
# Get Started with the Hotel API
<a name="doyouhavecredentials"/> 
## Do you have your Bing Ads credentials?
To use the Hotel API, you must have a Bing Ads account and a Microsoft account. To get a Bing Ads account, go to [http://bingads.microsoft.com](http://bingads.microsoft.com). If you're not signed in to your Microsoft account, you'll be redirected to sign in to your Microsoft account or sign up for a Microsoft account. After signing in, you'll have the option to **Sign up for a new Bing Ads account**. Select the sign up option and continue with the sign up process.

Unlike the other Bing Ads APIs, the Hotel API does not use a developer token. The API ignores it if you include it.

<a name="authenticatingcredentials"/> 
## Authenticating your credentials

The Hotel API uses the OAuth authentication scheme. For details about authenticating Microsoft account credentials using OAuth, see [Authentication with OAuth](~/guides/authentication-oauth.md). 

You *can* use the [Bing Ads SDK](~/guides/client-libraries.md) for .NET, Java, or Python to authenticate Microsoft account credentials. For details about how to get access and refresh tokens using the Bing Ads SDKs, see [Authentication With the SDKs](~/guides/sdk-authentication.md#oauth). 

If you choose not to use the Bing Ads SDK to get the tokens, see [OAuth C# Example](../hotel-api/code-example-oauth.md) for an example OAuth implementation.

> [!NOTE]
> You cannot use the Bing Ads SDK in the SI environment to get the access token. For SI, you can either clone the SDK Git repository and update the endpoints accordingly, or write your own AOuth implementation.
>
>For the SI environment, the following are the endpoints you must use to get Microsoft accounts and your application's client ID. Wherever you see endpoints mentioned in [Authentication with OAuth](~/guides/authentication-oauth.md), substitute them with the following SI endpoints.
>
> - si.bingads.microsoft.com&mdash;Endpoint for Bing Ads
> - account.microsoft-int.com&mdash;Endpoint for getting an SI Microsoft account 
> - outlook-int.com&mdash;Endpoint for SI email used when getting an SI Microsoft account
> - apps.dev.microsoft-int.com/#/appList&mdash;Endpoint for getting an SI client ID
> - login.live-int.com&mdash;Endpoint for OAuth requests

<a name="wheretousecredentials"/> 
## Where do you use your credentials?

After getting the user's OAuth access token, set the Authorization header to it.

```csharp
var headers = new WebHeaderCollection();
headers.Add(HttpRequestHeader.Authorization, "Bearer " + tokens.AccessToken);
```

For information about the Authorization header and other headers that the request and response may contain, see [headers](../hotel-api/reference.md#headers). 

> [!NOTE]
> The Hotel API uses the standard Authorization header; however, Bing Ads uses the AuthenticationToken header. If you use the Bing Ads SDK to get the OAuth tokens, you'll use the SDK to get the tokens and then set the Authorization header.

<a name="feeds"/>
## Do you have your hotel feed set up?

Before using the Hotel API, you should have your hotel feeds set up. For details, see:

- [Hotel Feed](../hotel-feed/hotel-feed.md)
- [Points of Sale Feed](../pos-feed/pos-feed.md) 
- [Transaction Message](../transaction-message/transaction-message.md) 




