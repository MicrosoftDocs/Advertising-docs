---
title: QueryControl message reference
description: Describes the schema elements that you use to create a QueryControl message.
ms.service: "bing-ads-hotel-service"
ms.topic: "article"
author: Matt-UX
ms.author: mattrob
---

# QueryControl message reference

> [!NOTE]
> This beta release of Hotel Ads is available to select participants only. For information about participating in the beta release program, please contact your account manager.

If you update your hotels' itinerary data using the Pull or Pull with Hints method, you use the QueryControl message to specify the amount of data that Bing should ask for in its pull requests. This topic describes the elements of the QueryControl message defined by the [QueryControl XSD](https://bhacstatic.blob.core.windows.net/schemas/query_control.xsd). 

For information about creating a QueryControl message, see [Creating a QueryControl Message](../query-control-message/create-query-control-message.md).

> [!NOTE]
> Bing does not support all QueryControl XSD elements. This topic includes only those elements and attributes that Bing supports. Bing ignores all other elements and attributes. 


> [!NOTE]
> The elements must be specified in the order defined by the QueryControl XSD (and as listed in this topic).

----

 
## QueryControl

Defines the root element of a QueryControl message.

|Element|Description|Children
|-|-|-
|QueryControl|The root element in a QueryControl message.|[QueryControl Type](#querycontrol-type)


## QueryControl Type

Defines a QueryControl message. 

|Element|Description|Children
|-|-|-
|ItineraryCapabilities|The parent object that contains the default settings and overrides for pull requests. |[ItineraryCapabilities Type](#itinerarycapabilities-type)


## ItineraryCapabilities Type

Defines the object that contains the default settings and overrides for pull requests. 

|Element|Description|Children
|-|-|-
|DefaultValue|Contains the default pull request settings, which specifies the amount of data that Bing should request. |[defaultItineraryCapability Type](#defaultitinerarycapability-type)
|PropertyOverride|Optional.<br /><br />Defines the pull request settings that override the default settings for the specified hotels. You can also use this element to identify hotels that you don't want Bing to request updates for.|[propertyCapabilityOverride Type](#propertycapabilityoverride-type)


## defaultItineraryCapability Type

Defines the default settings for pull requests. 

|Element|Description|Children
|-|-|-
|MinAdvancePurchase|Optional.<br /><br />The minimum number of days in advance of check-in that Bing may request itinerary data for. Bing ignores this value and uses `MaxAdvancePurchase` if `MaxAdvancePurchase` is specified, or has been previously specified.<br /><br />You set the default value for this setting at the time you onboard. If you subsequently specify this setting in a QueryControl message, the value must be less than or equal to `MaxAdvancePurchase`. |PositiveInteger
|MaxAdvancePurchase|Optional.<br /><br />The maximum number of days in advance of check-in that Bing may request itinerary data for. <br /><br />You set the default value for this setting at the time you onboard. If you subsequently specify this setting in a QueryControl message, the value may not exceeed 180 days.<br /><br />Bing uses this value to calculate the `LastDate` value in a pull request [Query](../query-message/query-message.md) message (Bing does not use this value for pull with hints requests). |PositiveInteger
|MinLengthOfStay|Optional.<br /><br />The minimum length of stay that Bing may request itinerary data for. Bing ignores this value if `MaxLengthOfStay` is specified, or has been previously specified.<br /><br />You set the default value for this setting at the time you onboard. If you subsequently specify this setting in a QueryControl message, the value must be less than or equal to `MaxLengthOfStay`.  |PositiveInteger
|MaxLengthOfStay|Optional.<br /><br />The maximum length of stay that Bing may request itinerary data for. <br /><br />You set the default value for this setting at the time you onboard. If you subsequently specify this setting in a QueryControl message, the value may not exceeed 14 days.<br /><br />Bing uses this value to specify the `Nights` value in pull requests and pull with hints requests that specify data ranges. If your hints specify `StaysIncludingRange`, this value is used to specify the `AffectedNights` value.  |PositiveInteger
|State|Optional.<br /><br />Determines whether to include or exclude all properties from pull requests. To enable pull requests, set to "enabled" (default). To disable pull requests, set to "disabled". |String


## propertyCapabilityOverride Type

Defines the pull request settings that override the default settings for one or more hotels. 

|Element|Description|Children
|-|-|-
|MinAdvancePurchase|Optional.<br /><br />The minimum number of days in advance of check-in that Bing may request itinerary data for. Bing ignores this value and uses `MaxAdvancePurchase` if `MaxAdvancePurchase` is specified, or has been previously specified.<br /><br />You set the default value for this setting at the time you onboard. If you subsequently specify this setting in a QueryControl message, the value must be less than or equal to `MaxAdvancePurchase`. |PositiveInteger
|MaxAdvancePurchase|Optional.<br /><br />The maximum number of days in advance of check-in that Bing may request itinerary data for. <br /><br />You set the default value for this setting at the time you onboard. If you subsequently specify this setting in a QueryControl message, the value may not exceeed 180 days.<br /><br />Bing uses this value to calculate the `LastDate` value in a pull request [Query](../query-message/query-message.md) message (Bing does not use this value for pull with hints requests).  |PositiveInteger
|MinLengthOfStay|Optional.<br /><br />The minimum length of stay that Bing may request itinerary data for. Bing ignores this value if `MaxLengthOfStay` is specified, or has been previously specified.<br /><br />You set the default value for this setting at the time you onboard. If you subsequently specify this setting in a QueryControl message, the value must be less than or equal to `MaxLengthOfStay`.  |PositiveInteger
|MaxLengthOfStay|Optional.<br /><br />The maximum length of stay that Bing may request itinerary data for. <br /><br />You set the default value for this setting at the time you onboard. If you subsequently specify this setting in a QueryControl message, the value may not exceeed 14 days.<br /><br />Bing uses this value to specify the `Nights` value in pull requests and pull with hints requests that specify data ranges. If your hints specify `StaysIncludingRange`, this value is used to specify the `AffectedNights` value.  |PositiveInteger
|State|Optional.<br /><br />Determines whether to include or exclude the specified hotels from pull requests (see the \<Property\> element). To enable pull requests for the specified hotels, set to "enabled" (default). To disable pull requests for the specified hotels, set to "disabled". |String
|Property|Required.<br /><br />An ID that identifies the hotel that the settings apply to. The ID must match the ID of a hotel in your Hotel Feed file. You may specify one or more \<Property\> elements, but a property may appear in only one \<PropertyOverride\>. |String



