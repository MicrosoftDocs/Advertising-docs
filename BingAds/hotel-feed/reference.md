---
title: "Hotel Feed Reference"
description: Describes the schema used to create a hotel feed file.
ms.service: "hotel-ads-hotel-feed"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
---

# Hotel Feed reference

> [!NOTE]
> This beta release of Hotel Ads is available to select participants only. For information about participating in the beta release program, please contact your account manager.

If you create hotel ads in Bing, you must use a hotel feed to provide Bing information about the hotels that you advertise. You must define and import your hotel feed prior to sending Bing [Transaction Messages](../transaction-message/transaction-message.md). 

For information about creating a hotel feed, see [Creating a Hotel Feed](../hotel-feed/create-hotel-feed.md).

> [!NOTE]
> The elements must be specified in the order defined by the [Hotel XSD](https://bhacstatic.blob.core.windows.net/schemas/hotel.xsd) (and as listed in this topic).

----

 
<a name="listings" /> 
## Listings
Defines the top-level element of a hotel feed.

|Element|Description|Children
|-|-|-
|listings|The top-level element in a hotel feed.|[Listings Type](#listingstype)

 
<a name="listingstype" /> 
## Listings Type
Defines a list of hotels in the feed.

|Element|Description|Children
|-|-|-
|language|Required.<br />Data type is string.<br /><br />The language that the hotel data in the feed is written in. Specify the language using the two-letter ISO 639 language code. For example, use **en** for English.<br /><br />Notes:<ul><li>The `language` element must be set to **en**.|None
|listing|Defines a hotel listing. Include a `listing` element for each hotel in the feed.|[Listing Type](#listingtype)


 
<a name="listingtype" /> 
## Listing Type
Defines a hotel.

|Element|Description|Children
|-|-|-
|id|Required.<br />Data type is string.<br /><br />An opaque, user-defined ID that uniquely identifies the hotel in the feed. <br /><br />When you create your transaction message, use this ID in the `Property` element of your transaction message to identify the hotel. |None
|name|Required.<br />Data type is string.<br /><br />The hotel's name. The name may contain a maximum of 200 characters. |None
|address|Required.<br />Data type is string or [Component Type](#componenttype).<br /><br />The street address of the hotel.<br /><br />Notes:<ul><li>You may specify the address using free-form text in the body of the `address` element or using `component` child elements to specify the components of the address (see [Component Type](#componenttype)).</li><li>You're encouraged to use `component` elements to specify the address' components.</li><li>If you use free-form text, separate each component of the address with a comma. For example, 1234 Billings Way, Redmond, WA, 98030.</li></ul>|[Component Type](#componenttype)
|country|Required.<br />Data type is string.<br /><br/>The country where the hotel is located. Specify the country using the two-letter ISO 3116 country code. For example, use **US** for United States.|None
|latitude|Required.<br /> Data type is decimal.<br /><br />The latitude of the hotel's geographical coordinates.<br /><br />Notes:<ul><li>The latitude and longitude are required only if you don't specify `phone`. It's preferred that you specify both the phone and geographical coordinates.</li><li>The latitude must be in the range -90.0 through 90.0.</li><li>Use [Location API](https://msdn.microsoft.com/library/ff701715.aspx) or another GeoCoding tool to generate the coordinates.</li></ul>|None
|longitude|Required.<br /> Data type is decimal.<br /><br />The longitude of the hotel's geographical coordinates.<br /><br />Notes:<ul><li>The latitude and longitude are required only if you don't specify `phone`. It's preferred that you specify both the phone and geographical coordinates.</li><li>The longitude must be in the range -180.0 through 180.0.</li><li>Use [Location API](https://msdn.microsoft.com/library/ff701715.aspx) or another GeoCoding tool to generate the coordinates.</li></ul>|None
|<a name="phone" />phone|Required.<br />Data type is string.<br /><br />A list of telephone numbers that customers use to contact the hotel.<br /><br />Attributes:<ul><li>type&mdash;Required. The type of telephone number specified. The following are the possible values.<br /><ul><li>main&mdash;Required. The hotel's main voice telephone number.</li><li>tollfree&mdash;Optional. The hotel's toll-free voice telephone number.</li><li>fax&mdash;Optional. The hotel's fax telephone number.</li><li>tdd&mdash;Optional. The hotel's telecommunications device for the deaf telephone number.</li><li>mobile&mdash;Optional. The hotel's mobile telephone number.</li></ul></ul>Notes:<ul><li>A phone number is required only if you don't specify `latitude` and `longitude`. It's preferred that you specify both the phone and geographical coordinates.</li><li>Provide unique telephone numbers for the listing.</li><li>Use dashes, spaces, or parentheses in the phone number to make it easier to read. For example, use “610-222-3333” or “(610) 222-3333” rather than “6102223333”.</li><li>Specify only one telephone number in each `phone` element. Do not specify multiple numbers, such as 650-123-2222/33.</li><li>The telephone number may contain an extension of up to 7 digits. Precede extensions with one of the following abbreviations: "ext", "extn", and "x". For example, "408-555-1111x12345" or "408-555-1111 x12345".</li><li>The telephone number may not include alphabetical characters.</li><li>Each listing should specify one of each type of phone number: "main", "mobile", "tollfree", "fax", or "tdd", if applicable.</li><li>If the telephone number includes the country code, precede it with a "+". For example, “+65 6722-2323” for a number in Singapore where the country code is 65, or “+001 (408) 555-1111” for a number in the United States where the country code is 001.</li></ul>|None

 
<a name="componenttype" /> 
## Component Type
Defines a component of a street address.

|Element|Description|Children
|-|-|-
|component|Optional.<br />Data type is string.<br /><br />Specify a `component` element for each component of the address. <br /><br />Attributes:<ul><li>name&mdash;Required. The name of the address component. The following are the possible values.<br /><ul><li>addr1&mdash;Required. The hotel's street address.</li><li>addr2&mdash;Optional. Second street address line.</li><li>addr3&mdash;Optional. Third street address line. </li><li>city&mdash;Required. The name of the city where the hotel is located.</li><li>province&mdash;Required. The name of the state, region, or province where the hotel is located.</li><li>postal_code&mdash;Required. The address' postal code.</li></ul></li></ul> |None

