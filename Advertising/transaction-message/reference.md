---
title: "Transaction Message Reference"
description: Describes the schema that defines a transaction message. 
ms.service: "hotel-ads-transaction-message"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
---

# Transaction Message reference

> [!NOTE]
> This beta release of Hotel Ads is available to select participants only. For information about participating in the beta release program, please contact your account manager.

If you create hotel ads in Bing, use transaction messages to provide Bing your itinerary data. This section describes the elements of a transaction message defined by the [Transaction XSD](https://bhacstatic.blob.core.windows.net/schemas/transaction.xsd). 

For information about creating a transaction message, see [Creating a Transaction Message](../transaction-message/create-transaction-message.md).

For information about sending a transaction message, see [Pusing a Transaction Message to Bing](../transaction-message/push-transaction-message.md) or [Having Bing Pull Transaction Messages](../transaction-message/pull-transaction-message.md).

> [!NOTE]
> Bing does not support all Transaction XSD elements. This topic includes only those elements and attributes that Bing supports. Bing ignores all other elements and attributes. 

> [!NOTE]
> The elements must be specified in the order defined by the Transaction XSD (and as listed in this topic).

----

 
<a name="transaction"></a> 

## Transaction

Defines the top-level element of a transaction message.

|Element|Description|Children
|-|-|-
|Transaction|The top-level element in a transaction message.<br /><br />The message must include the \<PropertyDataSet> element, \<Result> element, or both.<br /><br />Attributes:<ul><li>timestamp&mdash;Required. The UTC date and time that you sent the message. The time stamp format is: YYYY-MM-DDThh:mm:ss[+/-hh:mm]. The UTC offset is optional. For example, 2017-06-14T08:00:34 or 2017-06-14T01:00:34+07:00.<br /><br />The time stamp applies to each itinerary in the message. Bing processes an itinerary only if the time stamp is later than the time stamp of the same itinerary stored in Bing. For example, if Bing processes a message with time stamp 14:10 and then processes a message with time stamp 14:09, only those itineraries not included in the 14:10 message are processed.<br /><br />Messages with a time stamp older than 24 hours are not processed.<br /></li><li>id&mdash;Required. An opaque, user-defined ID that advertisers use to uniquely identify the message. The transaction status report includes this ID.</li></ul> |[Transaction Type](#transactiontype)

 
<a name="transactiontype"></a> 

## Transaction Type

Defines the transaction message.

|Element|Description|Children
|-|-|-
|PropertyDataSet|Optional.<br /><br />A container object that contains the metadata for room bundles and rate features. Use `RoomData` and `PackageData` in combination to provide details about room bundles and rate features. For individual rooms that aren't part of a package, use just `RoomData`.|[PropertyDataSet Type](#propertydatasettype)
|Result|Optional.<br /><br />Defines an itinerary (the combination of the `Checkin` and `Nights` elements identifies an itinerary). Specify one `Result` element for each itinerary that you define for a property. The number of itineraries that you may specify is limited by the size of the `Transaction` element, which must be less than 100 MB (or 10 MB compressed). |[Result Type](#resulttype)

 
<a name="propertydatasettype"></a> 

## PropertyDataSet Type

Defines s container object that contains the metadata for room bundles and rate features.


|Element|Description|Children
|-|-|-
|Property|Required.<br />Data type is string.<br /><br />The ID of the hotel property. This ID must match the ID of a hotel in your [hotel feed file](../hotel-feed/hotel-feed.md) that you submitted to Bing.|None
|RoomData|Describes a type of room. |[RoomData Type](#roomdatatype)
|PackageData|Describes a room bundle. Package data is similar to room data except it describes rate features (amenities) and terms that aren't part of the physical room description.|[PackageData Type](#packagedatatype)
 

<a name="resulttype"></a> 

## Result Type

Defines the itinerary.

|Element|Description|Children
|-|-|-
|Property|Required.<br />Data type is string.<br /><br />The ID of the hotel property. This ID must match the ID of a hotel in your hotel feed file that you submitted to Bing. |None
|Checkin|Required.<br />Data type is date.<br /><br />The check-in date in the form: YYYY-MM-DD.<br /><br />Notes:<ul><li>The date cannot be earlier that message's `timestamp` date.</li><li>The check-in date must be less than 90 days (the maximum advanced booking that you may specify) out from the time stamp date.</li><li>The combination of `Checkin` and `Nights` defines an itinerary. The itinerary must be unique for a `Property`.</li></ul> |None
|Nights|Required.<br />Data type is unsigned integer.<br /><br />The number of nights stay for this itinerary.|None
|Baserate|Required.<br />Data type is decimal.<br /><br />Use the room rate of the least expensive, private, double-occupancy room that's available. The base rate is the cost of the room for the entire stay&mdash;not the per night rate. For example, if the per night rate is 100.00 and the itinerary is for three nights, the base rate is 300.00. <br /><br />Attributes:<ul><!--<li>all_inclusive&mdash;Optional. If the base rate includes taxes and fees, set to **true**; otherwise, **false**. The default is **false**.<br /><br />If **true**, `Tax` and `OtherFees` must be set to 0.00.<br /><br />If the hotel is located in the US or Canada, you should not set this attribute to **true**. For information, see ???.</li>--><li>currency&mdash;Required. The three-character currency code that the rate is specified in. For example, USD for US Dollar. For a list of codes, see [ISO 4217](http://www.xe.com/iso4217.php).</li></ul>Notes:<ul><li>To remove the itinerary from inventory, set this element, `Tax`, and `OtherFees` to -1.00. You should remove the itinerary from inventory whenever there are no rooms available to satisfy the stay.</li><li>All currencies must use a decimal point (.) to separate the integer portion of the rate from the fractional portion (for example, 150.00).</li><li>Do not use a thousands separator in the integer portion of the rate. Instead of 1,150.00, use 1150.00</li></ul>|None
|Tax|Required.<br />Data type is decimal.<br /><br />The tax amount is based on `Baserate`.<br /><br />Attributes:<ul><li>currency&mdash;Required. The three-character currency code that the tax is specified in. For example, USD for US Dollar. For a list of codes, see [ISO 4217](http://www.xe.com/iso4217.php).</li></ul>Notes:<ul><li>All currencies must use a decimal point (.) to separate the integer portion of the tax from the fractional portion (for example, 50.00).</li><li>Do not use a thousands separator in the integer portion of the tax. Instead of 1,000.00, use 1000.00</li><!--<li>If the base rate's `all_inclusive` attribute is **true**, set this field to 0.00.</li>--><li>If `Baserate` is set to -1.00, this element must also be set to -1.00. </li></ul>|None
|OtherFees|Required.<br />Data type is decimal.<br /><br />Any fee not covered by base rate and taxes (for example, a parking fee or portable bed fee).<br /><br />Attributes:<ul><li>currency&mdash;Required. The three-character currency code that the fee is specified in. For example, USD for US Dollar. For a list of codes, see [ISO 4217](http://www.xe.com/iso4217.php).</li></ul>Notes:<ul><li>All currencies must use a decimal point (.) to separate the integer portion of the fee from the fractional portion (for example, 50.00).</li><li>Do not use a thousands separator in the integer portion of the fee. Instead of 1,000.00, use 1000.00</li><!--<li>If the base rate's `all_inclusive` attribute is **true**, set this element to 0.00.</li>--><li>If `Baserate` is set to -1.00, this element must also be set to -1.00.</ul>|None
|ExpirationTimestamp|Optional.<br />The UTC date and time that the price is considered expired. If the price is expired, the itinerary will not serve.<br /><br />The time stamp is in the form: YYYY-MM-DDThh:mm:ss[+/-hh:mm]. The UTC offset is optional. For example, 2017-06-14T08:00:34Z (no offset) or 2017-06-14T01:00:34+07:00.
|ChargeCurrency|Optional.<br />Data type is string.<br /><br />Defines when the user pays for a booking. The following are the possible case-insensitive values.<br /><br /><ul><li>Deposit&mdash;The user is charged a portion at booking and the remainder at a later point in time, typically when the user checks out of the hotel.</li><li>Hotel&mdash;The user is charged at check-in. If the payment must be made in the hotel's currency, use this option.</li><li>Web&mdash;The user is charged online at the time of booking. This is the default value.</li></ul>|None
|Custom1|Optional.<br />Data type is string.<br /><br />A user-defined string that Bing uses as a substitution value of a simarly named dynamic query parameter in a point of sale (POS) URL. For example, if the POS URL is https:\/\/www.partnerdomain.com?promo=(CUSTOM1) and `Custom1` is set to summer2017, the resulting POS URL is https:\/\/www.partnerdomain.com?promo=summer2017. For more information, see [Using Dynamic Query Parameters](../pos-feed/create-pos-feed.md#using-dynamic-query-parameters).|None
|Custom2|Optional.<br />Data type is string.<br /><br />A user-defined string that Bing uses as a substitution value of a simarly named dynamic query parameter in a point of sale (POS) URL. For example, if the POS URL is https:\/\/www.partnerdomain.com?promo=(CUSTOM2) and `Custom2` is set to summer2017, the resulting POS URL is https:\/\/www.partnerdomain.com?promo=summer2017. For more information, see [Using Dynamic Query Parameters](../pos-feed/create-pos-feed.md#using-dynamic-query-parameters).|None
|Custom3|Optional.<br />Data type is string.<br /><br />A user-defined string that Bing uses as a substitution value of a simarly named dynamic query parameter in a point of sale (POS) URL. For example, if the POS URL is https:\/\/www.partnerdomain.com?promo=(CUSTOM3) and `Custom3` is set to summer2017, the resulting POS URL is https:\/\/www.partnerdomain.com?promo=summer2017. For more information, see [Using Dynamic Query Parameters](../pos-feed/create-pos-feed.md#using-dynamic-query-parameters).|None
|Custom4|Optional.<br />Data type is string.<br /><br />A user-defined string that Bing uses as a substitution value of a simarly named dynamic query parameter in a point of sale (POS) URL. For example, if the POS URL is https:\/\/www.partnerdomain.com?promo=(CUSTOM4) and `Custom4` is set to summer2017, the resulting POS URL is https:\/\/www.partnerdomain.com?promo=summer2017. For more information, see [Using Dynamic Query Parameters](../pos-feed/create-pos-feed.md#using-dynamic-query-parameters).|None
|Custom5|Optional.<br />Data type is string.<br /><br />A user-defined string that Bing uses as a substitution value of a simarly named dynamic query parameter in a point of sale (POS) URL. For example, if the POS URL is https:\/\/www.partnerdomain.com?promo=(CUSTOM5) and `Custom5` is set to summer2017, the resulting POS URL is https:\/\/www.partnerdomain.com?promo=summer2017. For more information, see [Using Dynamic Query Parameters](../pos-feed/create-pos-feed.md#using-dynamic-query-parameters).|None
|AllowablePointsOfSale|Optional.<br /><br />A list of points of sale (POS) that identify websites where users can book the room. By default, the user can use any POS defined in your points of sale feed file. Specify this element only if you want to limit the points of sale for this specific itinerary. |Array of [allowablePointsOfSaleType](#allowablepointsofsaletype)


<a name="packagedatatype"></a> 

## PackageData Type

Defines a room bundle, which describes rate features (amenities) and terms that aren't part of the physical room description.

|Element|Description|Children
|-|-|-
|PackageId|Required.<br />Data type is string.<br /><br />An ID that uniquely identifies the package. Use this ID to match the package with a `Result` object in your pricing updates.|None
|Name|Required.<br /><br />A name that identifies the package. This should be the same name that you use to identify the room on your website. Specify a `Text` element for each language you support.|[Text Type](#texttype)
|Description|Optional.<br /><br />A description of the package. |[Text Type](#texttype)
|Capacity|Optional.<br />Data type is integer.<br /><br />The maximum number of guests that the room is capable of accommodating.<br /><br />**NOTES:**<ul><li>The value must be in the range 1 through 20.</li><li>The value must not be less than `Occupancy`.</li></ul> |None
|Occupancy|Optional.<br />Data type is integer.<br /><br />The maximum number of guests that the room is intended to accommodate. For example, although the room is physically capable of hosting 4 guests, it's intended for only 2 guests.<br /><br />**NOTES:**<ul><li>Although optional, you're strongly encouraged to always specify this element.</li><li>The value must be in the range 1 through 20.</li></ul>|None
|OccupancyDetails|Optional.<br /><br />A container object that contains details about occupancy. If you include `Occupancy`, you may also specify this element. |[OccupancyDetails](#occupancydetailstype)
|ChargeCurrency| |
|Refundable| |
|BreakfastIncluded|Optional.<br />Data type is Boolean.<br /><br />A value that determines whether the room bundle includes complimentary breakfast. |
|ParkingIncluded| |
|InternetIncluded| |
|RoomUpgradeIncluded| |
|MembershipBenefitsIncluded| |
|CarRentalIncluded| |
|MilesIncluded| |
|OnPropertyCredit| |
|EarlyCheckin| |
|LateCheckout| |


<a name="roomdatatype"></a> 

## RoomData Type

Defines a type of room.

|Element|Description|Children
|-|-|-
|RoomId|Required.<br />Data type is string.<br /><br />An ID that uniquely identifies the room. Use this ID to match the room data with a `Result` object in your pricing updates.|None
|Name|Required.<br /><br />A name that identifies the type of room. This should be the same name that you use to identify the room on your website. Specify a `Text` element for each language you support.|[Text Type](#texttype)
|Description|Optional.<br /><br />A description of the room. |[Text Type](#texttype)
|PhotoURL|Optional.<br /><br />A container object that contains the URL of an image of the room type. You may specify one or more photos. |[PhotoURL Type](#photourltype)
|Capacity|Optional.<br />Data type is integer.<br /><br />The maximum number of guests that the room is capable of accommodating.<br /><br />**NOTES:**<ul><li>The value must be in the range 1 through 20.</li><li>The value must not be less than `Occupancy`.</li></ul> |None
|Occupancy|Optional.<br />Data type is integer.<br /><br />The maximum number of guests that the room is intended to accommodate. For example, although the room is physically capable of hosting 4 guests, it's intended for only 2 guests.<br /><br />**NOTES:**<ul><li>Although optional, you're strongly encouraged to always specify this element.</li><li>The value must be in the range 1 through 20.</li><li>The value must not be greater than `Capacity`.</li></ul>|None
|OccupancyDetails|Optional.<br /><br />A container object that contains details about occupancy. If you include `Occupancy`, you may also specify this element. |[OccupancyDetails](#occupancydetailstype)


 
<a name="allowablepointsofsaletype"></a> 

## allowablePointsOfSaleType

Defines a point of sale (POS) where a user may book the room.

|Element|Description|Children
|-|-|-
|PointOfSale|<br /><br />Required.<br /><br />Attributes:<ul><li>id&mdash;Required. An opaque, user-defined ID that uniquely identifies a POS. This ID must match the ID of a POS defined in your pints of sale feed file.</li></ul> |None


 
<a name="texttype"></a> 

## Text Type

Defines a text string.

|Element|Description|Children
|-|-|-
|Text|Attributes:<ul><li>text&mdash;The text string.</li><li>language&mdash;The two-letter ISO 639-1 language code that identifies the language used by the text string. For example, 'en' for English.</li></ul> |None


 
<a name="occupancydetailstype"></a> 

## OccupancyDetails Type

Defines a container object that contains details about occupancy.

|Element|Description|Children
|-|-|-
|NumAdults|Required.<br />Data type is integer.<br /><br />The maximum number of adults the room is intended to accommodate.|None
|Children|Optional.<br /><br />A container object the identifies the ages of children the room is intended to accommodate.|[Children Type](#childrentype)


 
<a name="childrentype"></a> 

## Children Type

Defines a container object that identifies the ages of children the room is intended to accommodate.

|Element|Description|Children
|-|-|-
|Child|Attributes:<ul><li>age&mdash;The age of the child the room is intended to accommodate.</li></ul> |None

 
<a name="photourltype"></a> 

## PhotoUrl Type

Defines a container object that contains the URL of an image of the room type.

|Element|Description|Children
|-|-|-
|URL|Required.<br /><br />A URL to the image.|None
|Caption|Optional.<br /><br />A container object that contains a caption for the image.|[Text Type](#texttype)
