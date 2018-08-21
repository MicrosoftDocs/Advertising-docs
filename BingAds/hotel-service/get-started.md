---
title: "Get Started with the Hotel API"
description: Provides details about getting credentials and authenticating users.
ms.service: "hotel-ads-hotel-service"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
---

# Get started with the Hotel API

<a name="doyouhavecredentials"/>

## Do you have your Bing Ads credentials?

To use the Hotel API, you must have a Bing Ads account and a Microsoft account. To get a Bing Ads account, go to <a href="http://bingads.microsoft.com" data-raw-source="[http://bingads.microsoft.com](http://bingads.microsoft.com)">http://bingads.microsoft.com</a>. If you're not signed in to your Microsoft account, you'll be redirected to sign in to your Microsoft account or sign up for a Microsoft account. After signing in, you'll have the option to **Sign up for a new Bing Ads account**. Select the sign-up option and continue with the sign-up process.

Unlike the other Bing Ads APIs, the Hotel API does not use a developer token. The API ignores it if you include it.

## Enable your account for Hotel Ads

Your account manager needs to enable your account before you can use Hotel Ads or the API. Please confirm with your account manager that your account is enabled in both the production and sandbox environments.


<a name="authenticatingcredentials"/>

## Authenticating your credentials

The Hotel API uses the OAuth authentication scheme. For details about authenticating Microsoft account credentials using OAuth, see [Authentication with OAuth](/bingads/guides/authentication-oauth). 

You *can* use the [Bing Ads SDK](/bingads/guides/client-libraries) for .NET, Java, or Python to authenticate Microsoft account credentials. For details about using the SDK to get the access token, see [C#](/bingads/guides/get-started-csharp) | [Java](/bingads/guides/get-started-java) | [Python](/bingads/guides/get-started-python). (You should only use the SDK to get the access token if you're using the SDK for Bing Ads campaigns, too. Otherwise, it may not be worth the overhead of installing the SDK.)

If you choose not to use the Bing Ads SDK to get the tokens, see [OAuth C# Example](../hotel-service/code-example-oauth.md) for an example OAuth implementation.

> [!NOTE]
> If you use the API from a service, you must write a simple app to get the refresh token for a user that has permissions to access the hotel data. You will call the app you write once just to get the refresh token. After getting the refresh token, store it in secure storage that's accessible by your service. 
>
> Follow the steps outlined in [Authentication with OAuth](/bingads/guides/authentication-oauth) for getting the client ID for your app and for implementing the code grant flow. For an example of a simple console app that you use to get the tokens, see [OAuth C# Example](../hotel-service/code-example-oauth.md).
>
> After getting the initial refresh token, the following shows the basic calling sequence that you'll make to get the access token that you set the Authorization header to.
>
> - Get the refresh token from secured storage
> - Send an HTTP POST request to `https://login.live.com/oauth20_token.srf`  
>   - The following shows the body of the POST (the parameters are separated for readability):  
>     client_id=\<yourclientid>  
&grant_type=refresh_token  
&redirect_uri=https%3A%2F%2Flogin.live.com%2Foauth20_desktop.srf  
&refresh_token=\<yourrefreshtoken>` 
> - Get the access token, refresh token, and access token expiration from the response
> - Set a timer that expires just before the access token expires
> - Set the Authorization header to the access token
> - Store the new refresh token in secured storage
> - When the expiration timer expires, repeat the process
>
> You should only get a new access token just before the current token expires. Do not get a new access token for each call.
>
> If you receive an invalid_grant error, your refresh token is no longer valid. You will need to run your app again to provide consent and get a new refresh token.

### Authenticating your credentials in sandbox

For the sandbox environment, the following are the endpoints you must use to get Microsoft accounts and your application's client ID. Wherever you see endpoints mentioned in [Authentication with OAuth](/bingads/guides/authentication-oauth), substitute them with the following sandbox endpoints.

 - partner.api.sandbox.bingads.microsoft.com&mdash;Endpoint for Bing Ads sandbox
 - account.microsoft-int.com&mdash;Endpoint for getting a sandbox Microsoft account 
 - outlook-int.com&mdash;Endpoint for sandbox email used when getting a sandbox Microsoft account
 - apps.dev.microsoft-int.com/#/appList&mdash;Endpoint for getting a sandbox client ID
 - login.live-int.com&mdash;Endpoint for OAuth requests


<a name="getsicredentials"/>

## Getting sandbox credentials

### Get a sandbox account if you don't already have one

You use the sandbox environment to test your application before putting it in production. Use the following steps to get a sandbox account.

1.	Open a browser and navigate to https:\//sandbox.bingads.microsoft.com.
2.	Click **Sign up for Bing Ads** or **Sign up now**.
3.	Fill out the **Create Account** form.  
  
  - Choose the **Create a new email address** option.
  - Enter an MSA email address. The email server must be outlook<strong>-int</strong>.com (for example, someone@outlook-int.com).  
  
    > [!IMPORTANT]  
    > Sandbox supports MSAs created using an @outlook<strong>-int</strong>.com email account only. You may not use an @outlook.com email account. Also, you may not use an email account from another email service (for example, @gmail.com) even if the account is linked to an @outlook.com or @outlook<strong>-int</strong>.com email account.  
  
  - Finish the work flow by specifying the rest of your user information.  

4.	For **Import/Create Campaign**, click **Skip campaign creation**
5.	For **Go Live**, click **Skip payment information**


After creating your sandbox account and getting your MSA, let your account manager know so they can enable it for Hotel Ads. You won't be able to use Hotel Ads or the API in sandbox until it's enabled.

> [!NOTE]
> The MSA signup process returns you to the SI Bing Ads user interface (ui.si.bingads.microsoft.com). After completing the MSA process, sign out of the SI interface. To access Hotel Ads using the Bing Ads user interface in sandbox, go to <a href="https://ui.sandbox.bingads.microsoft.com" data-raw-source="[https://ui.sandbox.bingads.microsoft.com](https://ui.sandbox.bingads.microsoft.com)">https://ui.sandbox.bingads.microsoft.com</a> and sign in using your new MSA email address.


<!--
THIS IS THE PROCESS REQUIRED BEFORE MSA - BACK WHEN THERE WERE LEGACY CREDS

### Send an invite so you can create an MSA (**read step 5 carefully**)

The above steps create a Bing Ads legacy account. To use Hotel Ads API, you need a sandbox Microsoft account (MSA). To get an MSA that you can use in sandbox, you need to invite a user to work on your account. The following steps show how to invite a user to work on your account.

1.	In Bing Ads, click your user name (upper right corner)
2.	Click **Accounts & Billing**
3.	Click **Users**
4.	Click **Invite user**
5.	Enter the email address of the user to invite. The email address must use @outlook.com (for example, someone@outlook.com).  
  
  > [!IMPORTANT]  
  > You may send invites to @outlook.com email accounts only. You may not send invites to any other domain, even if the account is linked to an @outlook.com email account. If you try to send an invite to another domain (for example, someone@gmail.com), the BingAds UI will show the invite as pending indefinitely (the invite is never sent).  
  
6.	Click **Send**

### Create an MSA to use with Hotel Ads API (**read steps 3 and 5 carefully**)

Bing Ads sends an email invite to the user. If the invite doesn’t show up in the inbox, check the Junk Email folder. It may take a couple of minutes to receive the invite. The following steps show how to accept the invitation.

1.	Open the email from Bing Ads with subject line, Invitation to Bing Ads
2.	Click the embedded link
3.	Select **Create a new email address** to create an MSA. You must create a new MSA; you may not use an existing MSA.
4.	Click **Next**
5.	Enter an MSA email address. The email server must be outlook<strong>-int</strong>.com (for example, someone@outlook-int.com).  
  
  > [!IMPORTANT]  
  > Sandbox supports MSAs created using an @outlook<strong>-int</strong>.com email account only. You may not use an @outlook.com email account. Also, you may not use an email account from another email service (for example, @gmail.com) even if the account is linked to an @outlook.com or @outlook<strong>-int</strong>.com email account.  
  
6.	Finish the work flow by specifying the rest of your user information
7.  Exit Bing Ads after completing the MSA process.


After Bing creates the account, you may use the MSA with the Hotel Ads API to create hotel ad campaigns.

> [!NOTE]
> The MSA signup process returns you to the SI Bing Ads user interface (ui.si.bingads.microsoft.com). After completing the MSA process, sign out of the SI interface. To access your Hotel Ads Campaigns using the Bing Ads user interface in sandbox, go to <a href="https://ui.sandbox.bingads.microsoft.com" data-raw-source="[https://ui.sandbox.bingads.microsoft.com](https://ui.sandbox.bingads.microsoft.com)">https://ui.sandbox.bingads.microsoft.com</a> and sign in using your new MSA email address.

-->

<a name="wheretousecredentials"/>

## Where do you use your credentials?

After getting the user's OAuth access token, set the Authorization header to it.

```c#
var headers = new WebHeaderCollection();
headers.Add(HttpRequestHeader.Authorization, "Bearer " + tokens.AccessToken);
```

For information about the Authorization header and other headers that the request and response may contain, see [Headers](../hotel-service/reference.md#headers). 

> [!NOTE]
> The Hotel API uses the standard Authorization header. If you use the Bing Ads SDK to get the OAuth tokens, you'll use the SDK to get the tokens and then set the Authorization header.

<a name="feeds"/>

## Do you have your hotel feed set up?

Before using the Hotel API, you should have your hotel feeds set up. For details, see:

- [Hotel Feed](../hotel-feed/hotel-feed.md)
- [Points of Sale Feed](../pos-feed/pos-feed.md) 
- [Transaction Message](../transaction-message/transaction-message.md) 




