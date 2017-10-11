---
title: "Management Model for Resellers"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: A reseller can programmatically create new customer accounts and gets billed by invoice for all advertising costs incurred by their customers.
---
# Management Model for Resellers
The reseller role is offered to a limited set of partners that offer search-marketing tools and services to a large number of advertisers. The reseller role allows partners to programmatically create new customer accounts. The reseller is billed by invoice for all advertising costs incurred by their customers. The advertiser does not sign up for Bing Ads credentials, and may pay a fee to the reseller. The following sections describe the entity model and credentials for resellers.

## Reseller Entity Model
As described in [Entity Hierarchy and Limits](../guides/entity-hierarchy-limits.md) all advertising activity is organized by customer, which can have one or more accounts. Two or more customer entities play a role in the reseller model. The reseller customer is required, and then the reseller's aggregator user may programmatically create one or more managed customers with the [SignupCustomer](~/customer-management-service/signupcustomer.md) service operation. The aggregator user role is required for [SignupCustomer](~/customer-management-service/signupcustomer.md), and is provided solely to resellers.

Upon initial provisioning the reseller customer does not have any accounts to manage. There is an empty customer shell and an Aggregator user. Every time [SignupCustomer](~/customer-management-service/signupcustomer.md) is called, the following entities are created outside of the reseller customer.
-   A managed customer is created  
-   An account is created within the managed customer  

For more information about creating reseller managed customers, see [Adding Customers](../guides/customer-accounts.md#createcustomer).

The following figure shows two child customers created and managed by a reseller. These are referred to as child customers because the billing rolls up to the reseller's payment instrument. The aggregator user can programmatically manage all accounts across multiple reseller-managed child customers.

![Management Model Direct Reseller](../guides/media/management-model-reseller.png "Management Model Direct Reseller")

## Credentials and Account Access
The following are the header elements and the corresponding identifiers that a reseller would use.

> [!NOTE]
> If you use the *AuthenticationToken*, the *UserName* and *Password* elements are ignored. For more information, see [Authentication with OAuth](../guides/authentication-oauth.md).

|Header Element|Owner|
|------------------|---------|
|AuthenticationToken|The OAuth access token corresponding to the aggregator's linked Microsoft Account.|
|UserName|The reseller's aggregator sign-in user name.<br /><br />**Note:** As a best practice the reseller's aggregator user should always be used. If a unique business requirement is flagged, it is possible to create new users within the managed customers and join them with a multi-user token in calls to some service operations. For more information see [Account Permissions and the Developer Token](../guides/customer-accounts.md#accountpermissions) and [User Roles and Available Service Operations](../guides/customer-accounts.md#userroles) within [Customer Accounts](../guides/customer-accounts.md).|
|Password|The sign-in password of the user specified in UserName.|
|DeveloperToken|The reseller's token.<br /><br />**Note:** A single-user (SU) developer token is sufficient to authenticate with the corresponding user. For more information on token types, see [Account Permissions and the Developer Token](../guides/customer-accounts.md#accountpermissions).|
|CustomerId|The identifier of the customer that contains and owns the account. If you manage an account of another customer e.g. child customer created via [SignupCustomer](~/customer-management-service/signupcustomer.md), you should use that customer ID instead of your own customer ID. |
|CustomerAccountId|A managed customer's account ID.|
For more information about customer and account identifiers, see [Get Started With the Bing Ads API](../guides/get-started.md).

## <a name="reseller_signup"></a>How to Get Reseller API Credentials
To request reseller API credentials, please contact your designated account management team for details about getting the API Reseller role. If you are not currently a reseller but would like to become one, see [Become a Microsoft Advertising Authorized Reseller](https://advertise.bingads.microsoft.com/en-us/bing-partners/welcome).

## See Also
[Customer Accounts](../guides/customer-accounts.md)  
[Get Started With the Bing Ads API](../guides/get-started.md)  

