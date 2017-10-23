---
title: Process a Query message
description: Shows how to process a Query message that Bing Ads sends you requesting your hotel itinerary data. 
ms.service: "hotel-ads-query-message"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
ms.date: 11/1/2017
---

# Process a Query message

If you sign up for pull requests or pull with hints requests, Bing sends you a [Query](../Topic/Query%20Message.md) message that specifies the itinerary data that you need to send in your next [Transaction](../transaction-message/transaction-message.md) message.

## Using pull requests

If you use pull requests, the query is based on the setting you specify in your [QueryControl](../query-control-message/query-control-message.md) message. If your QueryControl message specifies a `MaxAdvancePurchase` value of 10 and a `MaxLengthOfStay` value of 3, and doesn't specify overrides, Bing sends you a request that's similar to the following Query message. 

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Query>
  <FirstDate>2017-10-20</FirstDate>
  <LastDate>2017-10-30</LastDate>
  <Nights>3</Nights>

  <PropertyList>
    <Property>223</Property>
    <Property>256</Property>
    <Property>289</Property>
  </PropertyList>
</Query>
``` 

Depending on the number of hotels you have, Bing may break the query up into several smaller queries with each query containing a subset of the hotels in the property list.

When you get the Query message, your response should contain a [Transaction](../transaction-message/transaction-message.md) message with the following \<Result\>.

```xml
  <Result>
    <Property>223</Property>
    <Checkin>2017-10-20</Checkin>
    <Nights>1</Nights>
    <!-- Pricing and other elements that changed -->
  </Result>
  <Result>
    <Property>223</Property>
    <Checkin>2017-10-20</Checkin>
    <Nights>2</Nights>
    <!-- Pricing and other elements that changed -->
  </Result>
  <Result>
    <Property>223</Property>
    <Checkin>2017-10-20</Checkin>
    <Nights>3</Nights>
    <!-- Pricing and other elements that changed -->
  </Result>
  
  . . .
  
  <Result>
    <Property>223</Property>
    <Checkin>2017-10-30</Checkin>
    <Nights>1</Nights>
    <!-- Pricing and other elements that changed -->
  </Result>
  <Result>
    <Property>223</Property>
    <Checkin>2017-10-30</Checkin>
    <Nights>2</Nights>
    <!-- Pricing and other elements that changed -->
  </Result>
  <Result>
    <Property>223</Property>
    <Checkin>2017-10-30</Checkin>
    <Nights>3</Nights>
    <!-- Pricing and other elements that changed -->
  </Result>
  
  . . .
  
  <Result>
    <Property>256</Property>
    <Checkin>2017-10-20</Checkin>
    <Nights>1</Nights>
    <!-- Pricing and other elements that changed -->
  </Result>
  <Result>
    <Property>256</Property>
    <Checkin>2017-10-20</Checkin>
    <Nights>2</Nights>
    <!-- Pricing and other elements that changed -->
  </Result>
  <Result>
    <Property>256</Property>
    <Checkin>2017-10-20</Checkin>
    <Nights>3</Nights>
    <!-- Pricing and other elements that changed -->
  </Result>

  . . .
    
```


## Using pull with hints requests

For examples that show the different types of Query messages that Bing sends if you use pull with hints request, see [Creating a Hint Message](../hint-message/create-hint-message.md).

 