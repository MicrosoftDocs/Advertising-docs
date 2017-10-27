---
title: "Management Model for Tool Providers"
ms.service: "bing-ads"
ms.topic: "article"
ms.date: 11/01/2017
author: "eric-urban"
ms.author: "eur"
description: A tool provider builds a Bing Ads application for other companies to manage their advertising campaigns.
---
# Management Model for Tool Providers
A tool provider builds a Bing Ads application for other companies to manage their advertising campaigns, and is not necessarily billed by Bing Ads. The advertiser user owns the accounts, is billed directly by Microsoft for valid ad clicks, and may pay a fee to the tool provider. The following sections describe the entity model and credentials for tool providers.

## Tool Provider Entity Model
The following figure shows multiple customers using the same third-party tool.

![Management Model Tool Provider](../guides/media/management-model-tool-provider.png "Management Model Tool Provider")

Third-party tools may be used to manage some or all aspects of an advertiser account. Your users may also manage their respective account through the Bing Ads web application or another third-party tool. You should design your application to be flexible and robust considering that data may have changed state since the last time a client used your application.

## See Also
[Customer Accounts](../guides/customer-accounts.md)  
[Get Started With the Bing Ads API](../guides/get-started.md)  

