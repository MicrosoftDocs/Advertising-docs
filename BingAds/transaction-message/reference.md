---
title: "Transaction Message Reference"
ms.service: "bing-ads"
ms.topic: "article"
author: "swhite-msft"
ms.author: "scottwhi"
description: 
---
# Transaction Message Reference
> [!NOTE]
> Hotel Ads is now under pilot and available to pilot participants only.  Please contact your account manager for details.

If you create hotel ads in Bing, you use transaction messages to provide Bing your itinerary data. This section describes the elements of a transaction message defined by the [Transaction XSD](https://bhacstatic.blob.core.windows.net/schemas/transaction.xsd). 

For information about creating a transaction message, see [Creating a Transaction Message](../transaction-message/create-transaction-message.md).

For information about sending a transaction message, see [Sending a Transaction Message](../transaction-message/send-bing-transaction-messages.md).

> [!NOTE]
> Bing does not support all Transaction XSD elements. This topic includes only those elements and attributes that Bing supports. Bing ignores all other elements and attributes. 

> [!NOTE]
> The elements must be specified in the order defined by the Transaction XSD (and as listed in this topic).

----

 
<a name="transaction" /> 
## Transaction
Defines the top-level element of a transaction message.

|Element|Description|Children
|-|-|-
|Transaction|The top-level element in a transaction message.<br /><br />Attributes:<ul><li>timestamp&mdash;Required. The UTC date and time that you sent the message. The time stamp format is: YYYY-MM-DDThh:mm:ss[+/-hh:mm]. The UTC offset is optional. For example, 2017-06-14T08:00:34 or 2017-06-14T01:00:34+07:00.<br /><br />The time stamp applies to each itinerary in the message. Bing processes an itinerary only if the time stamp is later than the time stamp of the same itinerary stored in Bing. For example, if Bing processes a message with time stamp 14:10 and then processes a message with time stamp 14:09, only those itineraries not included in the 14:10 message are processed.<br /><br />Messages with a time stamp older than 24 hours are not processed.</li><li>id&mdash;Required. An opaque, user-defined ID that advertisers use to uniquely identify the message. The transaction status report includes this ID.</li></ul> |[Transaction Type](#transactiontype)

 
<a name="transactiontype" /> 
## Transaction Type
Defines the transaction message.

|Element|Description|Children
|-|-|-
|Result|Required.<br /><br />The `Transaction` element must contain one or more `Result` elements. Specify one `Result` element for each itinerary (`Checkin` and `Nights` combination) that you specify for a property. The amount of data that you specify for each `Result` object determines the number of itineraries that you may specify. However, the size of the list plus the `Transaction` element must be less than 100 MB (or 10 MB compressed). |[Result Type](#resulttype)


 
<a name="resulttype" /> 
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
|ChargeCurrency|Optional.<br />Data type is string.<br /><br />Defines when the user pays for a booking. The following are the possible case-insensitive values.<br /><br /><ul><li>Deposit&mdash;The user is charged a portion at booking and the remainder at a later point in time, typically when the user checks out of the hotel.</li><li>Hotel&mdash;The user is charged at check-in. If the payment must be made in the hotel's currency, use this option.</li><li>Web&mdash;The user is charged online at the time of booking. This is the default value.</li></ul>|None
|Custom1|Optional.<br />Data type is string.<br /><br />A user-defined string that Bing uses as a substitution value of a simarly named dynamic query parameter in a point of sale (POS) URL. For example, if the POS URL is https://www.partnerdomain.com?promo=(CUSTOM1) and `Custom1` is set to summer2017, the resulting POS URL is https://www.partnerdomain.com?promo=summer2017. For more information, see [Using Dynamic Query Parameters](../pos-feed/create-pos-feed.md#using-dynamic-query-parameters).|None
|Custom2|Optional.<br />Data type is string.<br /><br />A user-defined string that Bing uses as a substitution value of a simarly named dynamic query parameter in a point of sale (POS) URL. For example, if the POS URL is https://www.partnerdomain.com?promo=(CUSTOM2) and `Custom2` is set to summer2017, the resulting POS URL is https://www.partnerdomain.com?promo=summer2017. For more information, see [Using Dynamic Query Parameters](../pos-feed/create-pos-feed.md#using-dynamic-query-parameters).|None
|Custom3|Optional.<br />Data type is string.<br /><br />A user-defined string that Bing uses as a substitution value of a simarly named dynamic query parameter in a point of sale (POS) URL. For example, if the POS URL is https://www.partnerdomain.com?promo=(CUSTOM3) and `Custom3` is set to summer2017, the resulting POS URL is https://www.partnerdomain.com?promo=summer2017. For more information, see [Using Dynamic Query Parameters](../pos-feed/create-pos-feed.md#using-dynamic-query-parameters).|None
|Custom4|Optional.<br />Data type is string.<br /><br />A user-defined string that Bing uses as a substitution value of a simarly named dynamic query parameter in a point of sale (POS) URL. For example, if the POS URL is https://www.partnerdomain.com?promo=(CUSTOM4) and `Custom4` is set to summer2017, the resulting POS URL is https://www.partnerdomain.com?promo=summer2017. For more information, see [Using Dynamic Query Parameters](../pos-feed/create-pos-feed.md#using-dynamic-query-parameters).|None
|Custom5|Optional.<br />Data type is string.<br /><br />A user-defined string that Bing uses as a substitution value of a simarly named dynamic query parameter in a point of sale (POS) URL. For example, if the POS URL is https://www.partnerdomain.com?promo=(CUSTOM5) and `Custom5` is set to summer2017, the resulting POS URL is https://www.partnerdomain.com?promo=summer2017. For more information, see [Using Dynamic Query Parameters](../pos-feed/create-pos-feed.md#using-dynamic-query-parameters).|None
|AllowablePointsOfSale|Optional.<br /><br />A list of points of sale (POS) that identify websites where users can book the room. By default, the user can use any POS defined in your points of sale feed file. Specify this element only if you want to limit the points of sale for this specific itinerary. |Array of [allowablePointsOfSaleType](#allowablepointsofsaletype)


 
<a name="allowablepointsofsaletype" /> 
## allowablePointsOfSaleType
Defines a point of sale (POS) where a user may book the room.

|Element|Description|Children
|-|-|-
|PointOfSale|<br /><br />Required.<br /><br />Attributes:<ul><li>id&mdash;Required. An opaque, user-defined ID that uniquely identifies a POS. This ID must match the ID of a POS defined in your pints of sale feed file.</li></ul> |None

