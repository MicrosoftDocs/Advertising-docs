---
title: "Get Started"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "scottwhi"
---
# Get Started
> [!NOTE]
> Hotel Ads is now under pilot and available to pilot participants only. Please contact your account manager for details.

If you create hotel ad campaigns in Bing Ads, use transaction messages to update your itinerary data (pricing and availability). 

## Getting permissions

Before you can send Bing transaction messages, you must contact your account manager to sign up. You must provide the IPv4 addresses (or address ranges in CIDR format) of all servers that you will use to send transaction messages.


## What's a transaction message 

A transaction message is an XML document that contains pricing and availability data for one or more hotel properties. For each hotel property, specify one `Result` element for each `Checkin` and `Nights` combination (also know as an itinerary) in your advanced booking window. If you allow five days advanced booking and stays of up to three-nights, your message would contain 15 `Result` elements. The following example shows one day's worth of itineraries.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Transaction timestamp="2017-05-25T20:44:56-04:00" id="de0be689-d094-406e-
8027-724309deb373">
  <Result>
    <Property>13579</Property>
    <Checkin>2017-05-26</Checkin>
    <Nights>1</Nights>
    <Baserate currency="USD">100.00</Baserate>
    <Tax currency="USD">10.00</Tax>
    <OtherFees currency="USD">4.00</OtherFees>
  </Result>
  <Result>
    <Property>13579</Property>
    <Checkin>2017-05-26</Checkin>
    <Nights>2</Nights>
    <Baserate currency="USD">200.00</Baserate>
    <Tax currency="USD">20.00</Tax>
    <OtherFees currency="USD">8.00</OtherFees>
  </Result>
  <Result>
    <Property>13579</Property>
    <Checkin>2017-05-26</Checkin>
    <Nights>3</Nights>
    <Baserate currency="USD">300.00</Baserate>
    <Tax currency="USD">30.00</Tax>
    <OtherFees currency="USD">12.00</OtherFees>
  </Result>
</Transaction>
```

You may specify up to 90 days advanced booking with stays of up to 14 nights. For example, if the message's `timestamp` is 2017-06-10, the last `Checkin` date that the message may specify is 2017-09-08.

The document must use UTF-8 encoding.

[Read more](../transaction-message/create-transaction-message.md).


## Validate the message before sending it

Before sending Bing the transaction message, use the [Transaction XSD](https://bhacstatic.blob.core.windows.net/schemas/transaction.xsd) to validate the message. This saves time and round trips by catching document syntax errors and constraints imposed by the XSD. 

The following example shows using xmllint to validate the message contained in SampleTransaction.xml.

```
xmllint.exe --schema transaction.xsd SampleTransaction.xml
```

> [!NOTE]
> There are constraints not defined by the XSD that may generate errors at the time Bing processes the message. Be sure that your message complies with all constraints defined in this document.

## Before sending your message...

Before sending transaction messages, provide your [hotel feed file](../hotel-feed/hotel-feed.md) and [points of sale file](../pos-feed/points-sale-feed.md) to your account manager. After they import the data into Bing, you may begin sending transaction messages. Transaction messages sent before the data is imported will fail.

## Where to send the message?

Send the transaction message in the body of an HTTPS POST request to:

`https://hotels.api.bingads.microsoft.com/api/customers/<customerId>/transactions`

Set \<customerId\> to the advertiser's customer ID.
  
The request must include the following header:

- Content-Type: `application/xml; charset=utf-8` 
  
If you compress the transaction message (recommended), include the following header:

- Content-Encoding: gzip

The following shows an example POST request.

```
POST https://hotels.api.bingads.microsoft.com/api/customers/abc123/transactions HTTP/1.1
Content-Type: application/xml; charset=utf-8
Host: hotels.api.bingads.microsoft.com

<?xml version="1.0" encoding="UTF-8"?>
<Transaction timestamp="2017-05-25T20:44:56-04:00" id="de0be689-d094-406e-
8027-724309deb373">
  <Result>
    <Property>13579</Property>
    <Checkin>2017-06-10</Checkin>
    <Nights>2</Nights>
    <Baserate currency="USD">159.99</Baserate>
    <Tax currency="USD">20.00</Tax>
    <OtherFees currency="USD">4.00</OtherFees>
    <AllowablePointsOfSale>
      <PointOfSale id="mobile"/>
      <PointOfSale id="desktop"/>
    </AllowablePointsOfSale>
  </Result>
</Transaction>
```

The POST request places the message in a queue to be processed and then returns. You may have a maximum of five requests queued or being processed at the same time. If you exceed the limit, the request fails with 429. 

To determine whether Bing successfully processed the message, see Hotel Ads Feed Status in the Bing Hotel Center of Bing Ads web application.

[Read more](../transaction-message/send-bing-transaction-messages.md).


## How often do I need to send messages

Send transaction messages whenever pricing and availability changes.
