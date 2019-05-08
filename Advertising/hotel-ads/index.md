---
title: "Hotel Ads"
description: Hotel Ads enables advertisers to showcase their hotels on Bing.com across devices.
ms.service: "hotel-ads"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
---

# Hotel Ads

> [!NOTE]
> This beta release of Hotel Ads is available to select participants only. For information about participating in the beta release program, please contact your account manager.
>
> The Hotel Ads feeds, API, and documentation are subject to change.

Hotel Ads enables advertisers to showcase their hotels on Bing.com across devices. Travelers can see hotel ads when they are actively looking to book a hotel.

To use Hotel Ads, you need to sign up with your account manager. As part of the sign-up process, you decide how you want to send your itinerary data to Bing. Your options are pushing changes to Bing, having Bing send you requests for all itinerary data, or having Bing send you requests for itinerary data that you identify as having changed. 

You also work with your account manager to import your hotel and points of sale data. The hotel feed is an XML document that describes the hotels that you want to advertise. The feed provides the hotel's name, address, telephone number, and geographical coordinates. For details about creating your hotel feed, see [Hotel Feed](../hotel-feed/hotel-feed.md).

The points of sale feed is an XML document that describes the sites that users use to book rooms. The feed provides a point of sale (POS) for each booking site you support. A POS describes the POS's display name, URL, and criteria for matching the user to a POS. For details about creating your points of sale feed, see [Points of Sale Feed](../pos-feed/pos-feed.md). 

After importing your hotel and points of sale feeds into Bing, you can begin sending Bing your itinerary data for your hotel properties. To specify the itineraries, use [Transaction](../transaction-message/transaction-message.md) messages. How you send the messages to Bing depends on the mode you chose when you signed up. If you chose the push mode, see [Pushing Transaction Messages to Bing](../transaction-message/push-transaction-message.md). If you chose one of the pull modes, see [Having Bing Pull Transaction Messages](../transaction-message/pull-transaction-message.md).

Also, don't forget to provide your account manager a 32x32 favicon to display next to your ads. The favicon may be a .ico, .jpg, or .png file.

To create hotel ad campaigns and specify bids, see [Hotel API](../hotel-service/hotel-api.md).
