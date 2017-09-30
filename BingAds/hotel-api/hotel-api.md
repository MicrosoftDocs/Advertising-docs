---
title: "Hotel API"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "scottwhi"
---
# Hotel API
> [!NOTE]
> Hotel Ads is under pilot and available to pilot participants only.  Please contact your account manager for details.
>
> The API and documentation are subject to change.

The Hotel API lets you manage your hotel ad campaigns and bidding.

<a name="thebasics"/>
## The basics...

When you get access to Hotel Ads, Bing sets up a default subaccount and hotel group that contains the hotels from your hotel feed. The subaccount provides the top-level logical organization of your hotel ads. You can think of it as a hotel campaign. Currently, you can have only one subaccount, and all hotels from the feed belong to it.

A subaccount specifies the campaign's daily budget, maximum bid allowed, and default bid and bid multipliers for ads that don't specify bids or multipliers.

Hotel groups provide another level for you to logically group hotel ads. A hotel group belongs to a single subaccount. The default hotel group that Bing creates for you is named, Ungrouped. It contains all hotels from the initial hotel feed and all new hotels going forward. 
 
A hotel group specifies the default bid and bid multipliers for ads that don't specify bids or multipliers. If you don't specify bids and multipliers, the group inherits them from the subaccount.

After you have your subaccount and hotel group set up, you can begin importing your hotel feed data. For information, see [Do you have your hotel feed set up?](../hotel-api/get-started.md#feeds)

Hotels belong to a single hotel group. Hotels specify the bid and bid multipliers to use for the hotel ad. If you don't specify bids and multipliers, the hotel inherits them from the hotel group or subaccount, in that order.

For information about moving the hotel to a different hotel group, see [Associating hotels with hotel groups](../hotel-api/manage-hotel-campaigns.md#associatinghotels).


## What needs in place before I start?

You'll need credentials and your hotel feeds set up. For information, see [Get Started](../transaction-message/get-started.md)


## How do I manage my resources?

The following sections show how to manage your subaccounts, hotel groups, and hotels. For information about the endpoints, header, query parameters, and resources, see [Hotel API Reference](../hotel-api/reference.md).

|Topic|Description
|-|-
|[Working with subaccounts](../hotel-api/manage-hotel-campaigns.md#workingwithsubaccounts)|Provides information about listing your subaccounts, getting a single subaccount, and updating a subaccount.
|[Working with hotel groups](../hotel-api/manage-hotel-campaigns.md#workingwithhotelgroups)|Provides information about listing a subaccount's hotel groups, getting a single hotel group, adding a hotel group, and updating a hotel group.
|[Working with hotels](../hotel-api/manage-hotel-campaigns.md#workingwithhotels)|Provides information about listing all hotels in the subaccount, listing hotels in a hotel group, getting a single hotel from a hotel group, and updating a hotel.
|[Associating a hotel with a hotel group](../hotel-api/manage-hotel-campaigns.md#associatinghotels)|Provides information about how to associate a hotel with a hotel group.

For code examples, see [Examples](../hotel-api/code-examples.md).


