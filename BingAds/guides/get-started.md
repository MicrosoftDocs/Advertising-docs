---
title: "Get Started With the Bing Ads API"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
---
# Get Started With the Bing Ads API
Any Bing Ads user with a developer token can begin using the Bing Ads Application Programming Interface (API). For advertisers placing a large number of ads or developers building advertising tools, the Bing Ads API provides a programmatic interface to Bing Ads. You can write your Bing Ads application in any language that supports web services. Code [examples](../guides/code-examples.md) are available in C# ([Get Started](../guides/get-started-csharp.md)), Java ([Get Started](../guides/get-started-java.md)), PHP ([Get Started](../guides/get-started-php.md)), and Python ([Get Started](../guides/get-started-python.md)). For more information about available services, see [Bing Ads API Overview](../guides/index.md).

## <a name="direct-signup"></a>Getting a Developer Token
To use Bing Ads APIs, you must have a developer token and valid user credentials. 
-  If you do not yet have a Bing Ads account, go to the [Bing Ads](https://bingads.microsoft.com/Default.aspx) web application, and click **Sign up**. 
-  To get a developer token for production, you must login at the [Bing Ads Developer Portal](https://developers.bingads.microsoft.com/Account) as a Microsoft Account user with the Super Admin role. Then click on the **Request Token** button. The Super Admin may request API access for any user within their customer scope. For more information, see [User Roles and Available Service Operations](customer-accounts.md#userroles).

The sandbox and production environments use separate credentials. For information about getting immediate access to the sandbox, see [Sandbox](sandbox.md).

## <a name="where-to-use"></a>Where to Use the API Credentials
Bing Ads services use Simple Object Access Protocol (SOAP) to exchange the request and response messages with the service operation. For more information, see [Bing Ads Services Protocol](../guides/services-protocol.md).

Each SOAP request must include the following SOAP headers, which contain the user's credentials.

|Element|Description|Data Type|Required|
|-----------|---------------|-------------|------------|
|*ApplicationToken*|The application-access token.|*string*|No. This header element is not used and should be null.|
|*AuthenticationToken*|The OAuth access token used to manage Bing Ads accounts linked to a Microsoft Account. For more information, see [Authentication with OAuth](../guides/authentication-oauth.md).|*string*|Required if the *UserName* and *Password* elements are not specified.|
|*CustomerAccountId*|The identifier of the account that owns the entities in the request. This header element must have the same value as the *AccountId* body element when both are required.|*string*|Required for service operations related to ad extensions and bid estimations. As a best practice you should always specify this element for operations limited in scope to a single account per service call.|
|*CustomerId*|The identifier of the customer that contains and owns the account. If you manage an account of another customer, you should use that customer ID instead of your own customer ID.|*string*|Required for service operations related to targeting and editorial. As a best practice you should always specify this element.|
|*DeveloperToken*|The client application's developer access token.|*string*|Yes.|
|*Password*|The Bing Ads user's sign-in password.<br/><br/>**Note:** New customers are required to sign up for Bing Ads with a Microsoft Account, and to manage those accounts you must use OAuth. Existing users with legacy Bing Ads managed credentials may continue to specify the  *UserName* and *Password* header elements. In future versions of the API, Bing Ads will transition exclusively to Microsoft Account authentication. For more information, see [Authentication with OAuth](../guides/authentication-oauth.md).|*string*|Required if the *AuthenticationToken* element is not specified.|
|*UserName*|The Bing Ads user's sign-in user name. You may not set this element to a Microsoft account.<br/><br/>**Note:** New customers are required to sign up for Bing Ads with a Microsoft Account, and to manage those accounts you must use OAuth. Existing users with legacy Bing Ads managed credentials may continue to specify the  *UserName* and *Password* header elements. In future versions of the API, Bing Ads will transition exclusively to Microsoft Account authentication. For more information, see [Authentication with OAuth](../guides/authentication-oauth.md).|*string*|Required if the *AuthenticationToken* element is not specified.|
## <a name="accountcustomerid"></a>Account and Customer Identifiers
Many Bing Ads service operations require an account ID and some require a customer ID. The following sections describe the account and customer identifiers, and provides information on retrieving the identifiers.

### <a name="accountid"></a>Account Identifier
The *account identifier* is a numeric identifier that identifies an account.

Many of the campaign management operations require that you specify the account identifier in the body of the request message. For example, the [GetCampaignsByAccountId](~/campaign-management/getcampaignsbyaccountid.md) operation returns all of the campaigns for the account that you specify in the body of the request message.

Do not confuse the *account identifier* with the *account number*. The account number is the system generated account number that is used to identify the account in the Bing Ads web application. The account number has the form xxxxxxxx, where xxxxxxxx is a series of any eight alphanumeric characters.
The API uses only the account identifier, never the account number.

### <a name="customeraccountid"></a>Customer Account Identifier
The *customer account identifier* is the same as the account identifier. You specify the account identifier in the *CustomerAccountId* SOAP request header element.

As a best practice you should always specify the identifier of the account being accessed in the *CustomerAccountId* header element. Some of the campaign management operations require that you specify the account ID in the request message, and most of them require that you specify the account ID in the *CustomerAccountId* header element.

### <a name="customerid"></a>Customer Identifier
The *customer identifier* is the numeric identifier that identifies a customer. You specify the customer identifier in the *CustomerId* SOAP request header element.

As a best practice you should always specify the identifier of the customer that owns the account in the *CustomerId* header element. Only operations that store data in the customer library for example targets, require you to set the *CustomerId* header element. Operations that require you to specify the customer ID will state this in the corresponding service operation topic.

### Getting Your Account ID and Customer ID
To get a user's customer ID and account ID, you can sign in to the Bing Ads web application and click on the **Campaigns** tab. The URL will contain a *cid* key/value pair in the query string that identifies your customer ID, and an *aid* key/value pair that identifies your account ID. For example, *https://ui.bingads.microsoft.com/campaign/Campaigns.m?cid=FindCustomerIdHere&aid=FindAccountIdHere#/customer/FindCustomerIdHere/account/FindAccountIdHere/campaign*.

## <a name="need-help"></a>Need Help?
For troubleshooting tips, see [Handling Service Errors and Exceptions](../guides/handle-service-errors-exceptions.md).

To get help with issues that you cannot resolve, consider posting in the [API Developer Forum](https://social.msdn.microsoft.com/forums/en-us/home?forum=BingAds) where an active Bing Ads product team or community member will try and help. If you do not find timely information via the developer forum, or if the investigation involves sensitive account or personal details, please contact [Bing Ads Support](https://advertise.bingads.microsoft.com/en-us/bing-ads-support).

## See Also
[Bing Ads Technical Guides](../guides/technical-guides.md)  
[Bing Ads API Reference](../guides/reference.md)  

