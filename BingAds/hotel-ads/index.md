---
title: "Hotel Ads Overview"
ms.service: "bing-ads"
ms.topic: "article"
author: "swhite-msft"
ms.author: "scottwhi"
---
# Hotel Ads Overview
> [!NOTE]
> Hotel Ads is now under pilot and available to pilot participants only. Please contact your account manager for details.
>
> The Hotel Ads components and documentation are subject to change.

Hotel Ads enables advertisers to showcase their hotels on Bing.com across devices. Travelers can see hotel ads when they are actively looking to book a hotel.

To use Hotel Ads, you need to work with your account manager to import your hotel and points of sale data. For details about creating your hotel and points of sale feed files, see [Hotel Feed](../hotel-feed/hotel-feed.md) and [Points of Sale Feed](../pos-feed/pos-feed.md). 

The hotel feed is an XML document that describes the hotels that you want to advertise. The feed provides the hotel's name, address, telephone number, and geographical coordinates. The points of sale feed is an XML document that describes the sites that users use to book rooms. The feed provides a point of sale (POS) for each booking site you support. A POS describes the POS's display name, URL, and criteria for matching the user to a POS. 

After importing your hotel and points of sale feeds into Bing, you need to send Bing your pricing and availability data for your hotel properties. For details about sending this information, see [Transaction Message](../transaction-message/transaction-message.md).

Lastly, you need to specify create hotel ad campaigns and specifying bids for your hotel ads. For information, see [Hotel API](../hotel-service/hotel-api.md).
