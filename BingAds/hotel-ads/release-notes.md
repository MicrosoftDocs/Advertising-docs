---
title: "Release notes"
description: Identifies the changes made to Hotel Ads for each release.
ms.service: "hotel-ads"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
ms.date: 11/1/2017
---

# Release notes

For information about changes that were included with each release, see the following sections.

## October 15, 2017

Released the Beta version of Hotel Ads.

### Nonbreaking changes

- Added the following ways to send Bing your transaction messages.  
  - Pull requests  
  If you sign up for pull requests, Bing sends the endpoint that you specify a [Query](../query-message/query-message.md) message that specifies the itinerary data that you should send back in a [Transaction](../transaction-message/transaction-message.md) message. With this option, you provide Bing all of your itinerary data.  
  - Pull with hints requests  
  If you sign up for pull with hints requests, Bing sends the endpoint that you specify a Query message that specifies the itinerary data that you should send back in a Transaction message. However, the query message specifies only the itinerary data that you said changed in your [Hint](../hint-message/hint-message.md) message. 
  
- Added the following messages to support the two types of pull requests.  
  - [QueryControl](../query-control-message/query-control-message.md) message  
  - [Hint](../hint/hint-message.md) message
  - [Query](../query-message/query-message.md) message  
  
- Increased the number of days prior to check in that users can book (advanced booking window) from 90 days to 180 days. 

## September 28, 2017

### Hotel API

#### Breaking changes

- Set default and maximum limits for the [$top](../hotel-service/reference.md#top-param) query parameter. The default value is 1,000 and the maximum value that you may specify is 5,000.  


## September 27, 2017

### Hotel API

#### Nonbreaking changes

- Added the `BidMultiplierSource` field to the [Hotel](../hotel-service/reference.md#Hotel) and  [HotelGroup](../hotel-service/reference.md#HotelGroup) objects. The source field indicates whether the object inherits or defines the bid multiplers. For example, if hotel object inherits the multipliers from the subaccount, `BidMultiplierSource` is SubAccount.  
  
- Added support for the [$select](../hotel-service/reference.md#select-param) OData query parameter. You can use the parameter to select the fields that you want the response to include.  
  
- Added the steps for getting a Microsoft account to use in the sandbox environment. See [Getting SI (sandbox) credentials](../hotel-service/get-started.md#getsicredentials).



## September 8, 2017

### Hotel API

#### Breaking changes

- Limited the list of hotel associations that you may specify in a single request to 500. For information, see the [/Associate](../hotel-service/reference.md#associate) template.  
  
- Removed the `@odata.context` field from response objects. For example, the [AddResponse](../hotel-service/reference.md#AddResponse) and [CollectionResponse](../hotel-service/reference.md#CollectionResponse) objects no longer include the `@odata.context` field.

## August 16, 2017

Released the Alpha version of Hotel Ads. 