---
title: "Having Bing Ads pull Transaction Messages"
description: Provides the details for having Bing Ads pull transaction messages.
ms.service: "hotel-ads-transaction-message"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
---

# Having Bing Ads pull Transaction Messages

Bing offers two pull modes. The first option is pull mode. With this option, Bing sends you requests and you send back all of your itinerary data. The second option is pull with hints. With this option, instead of returning all of your itinerary data, you return only the itineraries that you identified as having changed.

For both modes, you work with your TAM to specify:

- The endpoint that Bing sends requests to
- The frequency that Bing sends requests
- Default values for maximum advanced booking and night stays.

Once a day Bing sends a request to an endpoint that you specify asking for updates to your maximum advanced booking and night stays default values. You respond to the request with a [QueryControl](../query-control-message/query-control-message.md) message. In addition to specifying the default values, you can use the message to override the default values for specific properties or disable specific properties so Bing doesn't collect data for them. For more information, see [Creating a QueryControl Message](../query-control-message/create-query-control-message.md).


> [!NOTE]
> Before sending messages to Bing:
>
>- Validate the message to ensure that it's compliant with the message's XSD. This will save you round trips and time having to fix errors.
>  
>- Ensure that the message contains less than 100 MB of uncompressed data or 10 MB of compressed data (using GZip compression). To reduce network traffic, you should always send compressed data.


## Pull mode

With pull mode, Bing sends you a [Query](../query-message/query-message.md) message that identifies the itineraries that you should send back in the response using a [Transaction](../transaction-message/create-transaction-message.md) message. The request identifies all itineraries. Depending on the values that you specified for maximum advanced booking and nights stay, and the number of properties in your hotel feed, Bing may break the request into multiple requests. For information about processing the query message, see [Processing a Query Message](../query-message/process-query-message.md).


## Pull with hints mode

With pull with hints, Bing first sends you a hint request, which contains a time stamp of the last time you sent Bing updates. You respond to the hint request with a [Hint](../hint-message/hint-message.md) message that identifies the itineraries that have changed since the last successful update. You can identify individual itineraries or a range of itineraries using a range of check-in dates. For more information, see [Creating a Hint Message](../hint-message/create-hint-message.md).

Bing uses the hints to generate and send one or more [Query](../query-message/query-message.md) messages that specify only the itineraries that you said changed. Your response should be a [Transaction](../transaction-message/create-transaction-message.md) message that contains the requested data. For information about processing the query message, see [Processing a Query Message](../query-message/process-query-message.md).

