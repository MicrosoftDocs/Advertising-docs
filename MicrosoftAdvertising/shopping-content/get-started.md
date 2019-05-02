---
title: "Get Started with the Content API"
description: "Learn how to get started using the Content API."
author: "swhite-msft"
manager: "ehansen"

ms.service: "shopping-content-api"
ms.topic: "article"
ms.author: "scottwhi"
---

# Get Started with the Content API

<a name="credentials"/>
To use the Content API, you must have a Microsoft Advertising account and use a Microsoft account to access Microsoft Advertising. 

To get a Microsoft Advertising account, go to [http://ads.microsoft.com](http://ads.microsoft.com). If you're not signed in to your Microsoft account, you're redirected to sign in to your Microsoft account or sign up for a Microsoft account. After signing in, you'll have the option to **Sign up for a new Microsoft Advertising account**. Select the sign up option and **Continue** with the sign up process.

Next, you'll need a developer token. To get a token to use in the production environment, see [Microsoft Advertising Developer Portal](https://developers.ads.microsoft.com/account). Click **Request Token** and provide the requested information. If you use the API to manage your own account, you'll receive your token immediately; however, if you're managing accounts for others, it may take up to five business days to get a token.

## <a name="authentication"/> Authenticating your credentials

Content API uses the same authentication schemes as Bing Ads API. For details about authenticating Microsoft account credentials with OAuth, see [Authentication with OAuth](/bingads/guides/authentication-oauth). You *can* use the [Bing Ads SDK](/bingads/guides/client-libraries) for .NET, Java, or Python to authenticate Microsoft account credentials (but only for authentication; the Bing Ads SDK does not provide interfaces for the Content API).

For an example that shows how to use OAuth to authenticate Microsoft account credentials, see [Authenticating Microsoft Account Credentials in C#](../shopping-content/code-example-authentication-oauth.md).

## Where to use your credentials and developer tokens?

All calls must specify:

- The DeveloperToken header and set it to the developer token that you were given.
- The AuthenticationToken header and set it to your access token.

If you manage catalogs on behalf of other customers, you must set the `CustomerId` header to the customer ID of the customer whose store you're managing, and the `CustomerAccountId` header to the account ID of any of the customer's accounts that you manage (it doesn't matter which managed account). 

For information about these and other headers that the request and response may contain, see [Headers](../shopping-content/products-resource.md#headers). 

## <a name="configurebmc"/> Configuring Microsoft Merchant Center to use the API

For an overview of Microsoft Merchant Center (MMC), see [What is Microsoft Merchant Center?](http://help.ads.microsoft.com/#apex/3/en/51083/1) The topic includes links to all the Merchant Center topics and related videos.

You must complete the following steps if you haven't already done so.

1. [Verify and claim your Website's URL](http://help.ads.microsoft.com/#apex/3/en/50888/1)
  To get the webmaster tools mentioned in Verify and claim your Website's URL, see [Bing Webmaster Tools](http://www.bing.com/toolbox/webmaster). Sign in with the same Microsoft account that you use for Microsoft Advertising. For more information about using the tool, see [Verify Ownership of Your Website](http://www.bing.com/webmaster/help/how-to-verify-ownership-of-your-site-afcfefc6). 
2. [Create a Microsoft Merchant Center store](http://help.ads.microsoft.com/#apex/3/en/51085/1)
3. [Add a catalog](http://help.ads.microsoft.com/#apex/3/en/51105/1)

When you create a MMC store, the process creates a default catalog for you. The store and all catalogs that you create are automatically enabled for API management. The store contains a default catalog that all product gets, inserts, updates, and deletes apply to unless you specify the [bmc-catalog-id](../shopping-content/products-resource.md#bmccatalogid) query parameter in the resource URL. 

The **Store Setting** tab contains the Tenant URL, which you use as the base URI of your resource URL.

As an alternative to adding and enabling catalogs using the MMC web application, you may use the [Catalogs](../shopping-content/catalogs-resource.md) resource. For information, see [Managing your Catalogs](../shopping-content/manage-catalogs.md).

> [!NOTE] 
> In certain circumstances, you can use the API with FTP to update a catalog feed. For information about using the API with FTP, see [Can I Use the API and FTP?](../shopping-content/can-use-api-ftp.md) 


## Next Steps
Now that you're ready to start using the API, see the following sections.

- [Testing your Code in sandbox](../shopping-content/test-code-sandbox.md)
- [Managing your Catalogs](../shopping-content/manage-catalogs.md)
- [Managing your Products](../shopping-content/manage-products.md) 
