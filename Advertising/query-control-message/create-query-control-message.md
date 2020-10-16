---
title: Create a QueryControl message
description: Shows how to create a QueryControl message, which describes the default values and overrides for Query messages. 
ms.service: "bing-ads-hotel-service"
ms.topic: "article"
author: Matt-UX
ms.author: matrob
---

# Create a QueryControl message

If you sign up for pull requests or pull requests with hint, Bing sends a message once a day to the endpoint that you specify asking for changes to your default settings. The body of your response is a [QueryControl](../query-control-message/reference.md) message. 

The QueryControl message defines the default settings that you want Bing to use when it sends you pull requests for itinerary data. You can also use the message to override default values for specific hotel properties or to tell Bing not to request data for a set of hotels.

When you send a message, Bing overwrites the previous message's list of property overrides. For \<DefaultValue\> settings, Bing only overwrites the values that you specify; if you don't specify a setting, Bing retains the setting's previous value. The exception is the `State` setting, which Bing sets to enabled if you don't specify it.

## Using default settings

By default, Bing uses the `MaxAdvancePurchase` and `MaxLengthOfStay` values that you specified when you onboarded. The maximum value is 180 days advanced booking and 14 nights stay. If you don't want to change your default setting, the following shows an example of the QueryControl message that you'd return.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<QueryControl>
  <ItineraryCapabilities>
    <DefaultValue />
  </ItineraryCapabilities>
</QueryControl>
```

If your defaults contain the maximum allowed values, and you signed up for pull requests, the amount of itinerary data that you must return is 180 days \* 14 nights \* number of hotels.  

## Changing your default settings

If you want to reduce the amount of data that you send Bing, specify default values for the `MaxAdvancePurchase` and `MaxLengthOfStay` elements. For example, to only return itinerary data for 30 days advanced booking and 7 nights stay, return the following message:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<QueryControl>
  <ItineraryCapabilities>
    <DefaultValue>
      <MaxAdvancePurchase>30</MaxAdvancePurchase>
      <MaxLengthOfStay>7</MaxLengthOfStay>
    </DefaultValue>
  </ItineraryCapabilities>
</QueryControl>
```

Because Bing ignores the `MinAdvancePurchase` and `MinLengthOfStay` elements if the maximum settings have been set, there's no reason to include them.

## Overriding the default settings for specific hotels

If the default values work for some but not all of your properties, you can override the default values for specific properties. For example, to only return itinerary data for 10 days advanced booking and 3 nights stay for properties 123 and 456, return the following message:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<QueryControl>
  <ItineraryCapabilities>
    <DefaultValue>
      <MaxAdvancePurchase>30</MaxAdvancePurchase>
      <MaxLengthOfStay>7</MaxLengthOfStay>
    </DefaultValue>

    <PropertyOverride>
      <MaxAdvancePurchase>10</MaxAdvancePurchase>
      <MaxLengthOfStay>3</MaxLengthOfStay>
      <Property>123</Property>
      <Property>456</Property>
    </PropertyOverride>
  </ItineraryCapabilities>
</QueryControl>
```

## Enabling and disabling hotels

By default, if you signed up for pull requests, Bing requests data for all hotels in your Hotel Feed file. If you want to temporarily disable pull requests, return the following message with the `State` element set to disabled.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<QueryControl>
  <ItineraryCapabilities>
    <DefaultValue>
      <State>disabled</State>
    </DefaultValue>
  </ItineraryCapabilities>
</QueryControl>
```
If you decide later to enable pull requests, remove the `State` element in the next message.

You can also disable requests for specific hotels. For example, to prevent Bing from requesting itinerary data for hotels 123 and 456, return the following message.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<QueryControl>
  <ItineraryCapabilities>
    <DefaultValue>
      <MaxAdvancePurchase>30</MaxAdvancePurchase>
      <MaxLengthOfStay>7</MaxLengthOfStay>
    </DefaultValue>

    <PropertyOverride>
      <State>disabled</State>
      <Property>123</Property>
      <Property>456</Property>
    </PropertyOverride>
  </ItineraryCapabilities>
</QueryControl>
```

If you decide later to enable the hotels, remove the property override. If the override includes default values that you want to retain, remove the `State` element in the next message.

<a name="pullrequestexample"></a>

## Examples of pull requests based on Query Control settings

This example is based on the following QueryControl message:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<QueryControl>
  <ItineraryCapabilities>
    <DefaultValue>
      <MaxAdvancePurchase>10</MaxAdvancePurchase>
      <MaxLengthOfStay>5</MaxLengthOfStay>
    </DefaultValue>

    <PropertyOverride>
      <State>disabled</State>
      <Property>123</Property>
      <Property>456</Property>
    </PropertyOverride>

    <PropertyOverride>
      <MaxAdvancePurchase>5</MaxAdvancePurchase>
      <MaxLengthOfStay>2</MaxLengthOfStay>
      <Property>789</Property>
    </PropertyOverride>
  </ItineraryCapabilities>
</QueryControl>
```
 
If today's date is 2017-10-20, and the list of hotel properties is: 123, 456, 789, 223, 256, and 289, the following examples shows the separate pull request Query messages that Bing sends you.

**First message**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Query>
  <FirstDate>2017-10-20</FirstDate>
  <LastDate>2017-10-30</LastDate>
  <Nights>5</Nights>

  <PropertyList>
    <Property>223</Property>
    <Property>256</Property>
    <Property>289</Property>
  </PropertyList>
</Query>
``` 

**Second message**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Query>
  <FirstDate>2017-10-20</FirstDate>
  <LastDate>2017-10-25</LastDate>
  <Nights>2</Nights>

  <PropertyList>
    <Property>789</Property>
  </PropertyList>
</Query>
``` 

Depending on the number of hotel properties, Bing may break up the request into multiple Query requests. So, in the previous example, if there were 1,000 hotels, Bing might break up the first message into 100 separate messages.
