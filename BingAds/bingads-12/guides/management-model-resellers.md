---
title: "Management Model for Resellers"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: A reseller can programmatically create new customer accounts and gets billed by invoice for all advertising costs incurred by their customers.
---
# Management Model for Resellers
The reseller role is offered to a limited set of partners that offer search-marketing tools and services to a large number of advertisers. The reseller role allows partners to programmatically create new customer accounts. The reseller is billed by invoice for all advertising costs incurred by their customers. The advertiser does not sign up for Microsoft Advertising credentials, and may pay a fee to the reseller. The following sections describe the entity model and credentials for resellers.

## Reseller Entity Model
As described in [Entity Hierarchy and Limits](entity-hierarchy-limits.md) all advertising activity is organized by customer, which can have one or more accounts. Two or more customer entities play a role in the reseller model. The reseller customer is required, and then the reseller's aggregator user may programmatically create one or more managed customers with the [SignupCustomer](../customer-management-service/signupcustomer.md) service operation. The aggregator user role is required for [SignupCustomer](../customer-management-service/signupcustomer.md), and is provided solely to resellers.

> [!IMPORTANT] 
> If a super admin user is added to the reseller customer after your initial credentials are provisioned, by default the user can manage the data of all customers that the reseller manages. The user won't be able to call [SignupCustomer](../customer-management-service/signupcustomer.md), but will otherwise have read and write access to the campaign data.

Upon initial provisioning the reseller customer does not have any accounts to manage. There is an empty customer shell and an Aggregator user. Every time [SignupCustomer](../customer-management-service/signupcustomer.md) is called, the following entities are created outside of the reseller customer.
- A managed customer is created  
- An account is created within the managed customer  

When you call the [SignupCustomer](../customer-management-service/signupcustomer.md) operation, pass both [Customer](../customer-management-service/customer.md) and [AdvertiserAccount](../customer-management-service/advertiseraccount.md) objects. The customer object includes the customer's name, the address where the customer is located, the market in which the customer operates, and the industry in which the customer participates. Although it is possible to add multiple customers with the same details, you should use unique customer names so that users can easily distinguish between customers in a user interface.

The account object must specify the name of the account; the type of currency to use to settle the account; and the payment method identifier, which must be set to null. The operation generates an invoice account and sets the payment method identifier to the identifier associated with the reseller's invoice. You are invoiced for all charges incurred by the customers that you manage.

The following figure shows two child customers created and managed by a reseller. These are referred to as child customers because the billing rolls up to the reseller's payment instrument. The aggregator user can programmatically manage all accounts across multiple reseller-managed child customers.

![Management Model Direct Reseller](media/management-model-reseller.png "Management Model Direct Reseller")

## <a name="reseller_signup"></a>How to Get Reseller Credentials
To request reseller credentials, please contact your designated account management team for details about getting the Aggregator role for resellers. If you are not currently a reseller but would like to become one, go to the [Microsoft Advertising Partner Program](https://advertise.bingads.microsoft.com/en-us/bing-partners/welcome) welcome page. 

## See Also
[Customer Accounts](customer-accounts.md)  
[Get Started With the Bing Ads API](get-started.md)  

