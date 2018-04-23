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

## <a name="get-developer-token"></a>Get a Developer Token
To use Bing Ads APIs, you must have a developer token and valid user credentials. A developer token enables programmatic access to the accounts permitted for a user. Each provisioned user is assigned a role, for example Super Admin, and granted permissions to one or more accounts. The same accounts available in the Bing Ads web application are available to the corresponding user programmatically through the API. For more information see [Account Permissions and the Developer Token](customer-accounts.md#accountpermissions). 
-  If you do not yet have a Bing Ads account, you can sign up via the [Bing Ads web application](https://secure.bingads.microsoft.com/). 
-  To get a developer token for production, you must login at the [Bing Ads Developer Portal](https://developers.bingads.microsoft.com/Account) as a Microsoft Account user with the Super Admin role. Then click on the **Request Token** button. The Super Admin may request API access for any user within their customer scope. For more information, see [User Roles and Available Service Operations](customer-accounts.md#userroles).

The sandbox and production environments use separate credentials. You can sign up for a [Sandbox](sandbox.md) account [here](https://secure.sandbox.bingads.microsoft.com/). Everyone can use the universal sandbox developer token i.e., **BBD37VB98**.

## <a name="where-to-use"></a>Where to Use the API Credentials
When you call a service operation such as [GetCampaignsByAccountId](../campaign-management-service/getcampaignsbyaccountid.md), you must specify [request header](#request-headers) elements such as DeveloperToken, CustomerId, and CustomerAccountId.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetCampaignsByAccountId</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetCampaignsByAccountIdRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
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

With the Customer Management API you can get the customer and account identifiers for each authenticated user. 

Call [GetUser](../customer-management-service/getuser.md) with your Bing Ads credentials and DeveloperToken. Within the Body set the UserId nil. The response will include a [User](../customer-management-service/user.md) object that contains the UserId.

```xml
<?xml version="1.0" encoding="utf-8"?>
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
    <s:Header>
    <h:ApplicationToken i:nil="true" xmlns:h="https://bingads.microsoft.com/Customer/v11" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" />
    <h:AuthenticationToken xmlns:h="https://bingads.microsoft.com/Customer/v11">OAuthAccessTokenGoesHere</h:AuthenticationToken>
    <h:DeveloperToken xmlns:h="https://bingads.microsoft.com/Customer/v11">DeveloperTokenGoesHere</h:DeveloperToken>
    <h:Password i:nil="true" xmlns:h="https://bingads.microsoft.com/Customer/v11" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" />
    <h:UserName i:nil="true" xmlns:h="https://bingads.microsoft.com/Customer/v11" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" />
    </s:Header>
    <s:Body>
    <GetUserRequest xmlns="https://bingads.microsoft.com/Customer/v11">
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
    <h:ApplicationToken i:nil="true" xmlns:h="https://bingads.microsoft.com/Customer/v11" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" />
    <h:AuthenticationToken xmlns:h="https://bingads.microsoft.com/Customer/v11">OAuthAccessTokenGoesHere</h:AuthenticationToken>
    <h:DeveloperToken xmlns:h="https://bingads.microsoft.com/Customer/v11">DeveloperTokenGoesHere</h:DeveloperToken>
    <h:Password i:nil="true" xmlns:h="https://bingads.microsoft.com/Customer/v11" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" />
    <h:UserName i:nil="true" xmlns:h="https://bingads.microsoft.com/Customer/v11" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" />
    </s:Header>
    <s:Body>
    <SearchAccountsRequest xmlns="https://bingads.microsoft.com/Customer/v11">
        <Predicates xmlns:a="https://bingads.microsoft.com/Customer/v11/Entities" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <a:Predicate>
            <a:Field>UserId</a:Field>
            <a:Operator>Equals</a:Operator>
            <a:Value>UserIdGoesHere</a:Value>
        </a:Predicate>
        </Predicates>
        <Ordering i:nil="true" xmlns:a="https://bingads.microsoft.com/Customer/v11/Entities" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" />
        <PageInfo xmlns:a="https://bingads.microsoft.com/Customer/v11/Entities" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
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

|Element|Description|Data Type|
|-----------|---------------|-------------|
|ApplicationToken|This header element is not used and should be ignored.|**string**|
|AuthenticationToken|The OAuth access token that represents a Microsoft Account user who has permissions to Bing Ads accounts. For more information, see [Authentication with OAuth](authentication-oauth.md).|**string**|
|CustomerAccountId|The identifier of the account that owns the entities in the request. This header element must have the same value as the AccountId body element when both are required.|**string**|
|CustomerId|The identifier of the customer that contains and owns the account. If you manage an account of another customer, you should use that customer ID instead of your own customer ID.|**string**|
|DeveloperToken|The developer token used to access the Bing Ads API.|**string**|
|Password|This element is reserved for internal use and will be removed from a future version of the API. You must use the AuthenticationToken element to set user credentials. |**string**|
|UserName|This element is reserved for internal use and will be removed from a future version of the API. You must use the AuthenticationToken element to set user credentials.|**string**|

> [!TIP]
> Do not mistake the account number for the account identifier. The account number is the system generated account number that is used to identify the account in the Bing Ads web application. The account number has the form xxxxxxxx, where xxxxxxxx is a series of any eight alphanumeric characters. The API service requests only use the account identifier, and never use the account number.

> [!NOTE]
> With the exception of the Customer Billing and Customer Management services, the CustomerAccountId and CustomerId are required for most service operations. As a best practice you should always specify them in the request.  

## <a name="need-help"></a>Need Help?
For troubleshooting tips, see [Handling Service Errors and Exceptions](handle-service-errors-exceptions.md).

To get help with issues that you cannot resolve, consider posting in the [API Developer Forum](https://social.msdn.microsoft.com/forums/en-us/home?forum=BingAds) where an active Bing Ads product team or community member will try and help. If you do not find timely information via the developer forum, or if the investigation involves sensitive account or personal details, please contact [Bing Ads Support](https://advertise.bingads.microsoft.com/en-us/bing-ads-support).

## See Also
[Bing Ads Technical Guides](technical-guides.md)  
[Bing Ads API Reference](reference.md)  

