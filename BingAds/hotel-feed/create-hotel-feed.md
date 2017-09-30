---
title: "Creating a Hotel Feed"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "scottwhi"
---
# Creating a Hotel Feed
> [!NOTE]
> Hotel Ads is now under pilot and available to pilot participants only. Please contact your account manager for details.

To provide Bing your hotel listings, create an XML document that contains a listing of each hotel you want to advertise. A listing describes the hotel's name, address, telephone number, and geographical coordinates.

The document must use UTF-8 encoding and must conform to the [Hotel XSD](https://bhacstatic.blob.core.windows.net/schemas/hotel.xsd). 

> [!NOTE]
> Bing does not support all XSD elements. Bing ignores any element or attribute in the document that it does not support. The [Hotel Feed Reference](../hotel-feed/reference.md) includes only those elements and attributes that Bing supports. 

> [!NOTE]
> The document must specify the elements in the order defined in the Hotel XSD (or as shown in the reference).



## Getting the data right

Because Bing attempts to match properties in your hotel feed to businesses in Bing Maps, it is import that the data you provide about the hotel is accurate and complete.

If your property has missing or incorrect information, Bing may not be able to match it. If Bing cannot match the property, Bing will not advertise it. When your TAM imports your hotel feed file, they will let you know the hotels that Bing could not match.


## The top-level element in your feed

The hotel feed contains a single, top-level [listings](../hotel-feed/reference.md#listings) element. The `listings` element contains two required child elements: `language` and `listing`. 

```
<?xml version="1.0" encoding="UTF-8"?>
<listings  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
? <language>en</language>
? <listing>
? ? . . .
? </listing>
? ...
</listings>
```

The `language` element specifies the language that the data in the feed is written in. To specify the language, use the two-letter ISO 639 language code. For example, use **en** for English.

> [!NOTE]
> The hotel feed supports only the English language.

The [listing](../hotel-feed/reference.md#listingstype) element contains information about the hotel, such as it's name, address, and phone number. For information about defining a listing, see [Defining a hotel listing](#defining-a-hotel-listing).


## Defining a hotel listing

The `listing` element defines a hotel. You must specify a `listing` element for each hotel that you advertise. The listing must specify all elements. The exception is that you may specify either the geographical coordinates or a telephone number. Although you may specify either the coordinates or telephone number, you should specify both to ensure a better chance of matching properties in Bing Maps.

```
? <listing>
? ? <id>abc123</id>
? ? <name>Great Ambers Getaway</name>
? ? <address>
? ? ? <component name="addr1">1234 Porter Road</component>
? ? ? <component name="city">Goldendale</component>
? ? ? <component name="province">WA</component>
? ? ? <component name="postal_code">98234</component>
? ? </address>
? ? <country>US</country>
? ? <latitude>47.694351</latitude>
? ? <longitude>-122.451782</longitude>
? ? <phone type="main">123-456-7890</phone>
? </listing>
```

The ID in the `id` element is user-defined and must be unique within the feed.

The address in the `address` element is the hotel's street address. The address must be a street address and not a post office box. You can specify the hotel's address using the `component` element seen in the above example or by using a free-form string seen in the below example. The preference is to use `component` elements.

```
? ? <address>1234 Porter Road, Goldendale, WA, 98234</address>
```

The `latitude` and `longitude` element specify the hotel's geographical coordinates. Use a geocoding API such as [Location API](https://go.microsoft.com/fwlink/?linkid=859317) to generate the coordinates from a street address.

The listing must specify at least the hotel's main telephone number. The main number should be the front desk's phone number and not a central reservations phone number. The more contact phone numbers that you provide the better. The following example shows the other phone options.

```
? ? <phone type="main">123-456-7890</phone>
? ? <phone type="tollfree">800-456-7890</phone>
? ? <phone type="fax">123-456-7890</phone>
? ? <phone type="tdd">123-456-7890</phone>
? ? <phone type="mobile">123-456-7890</phone>
```

For more information about specifying telephone numbers, see the [phone](../hotel-feed/reference.md#phone) element.
 

## General rules

- Use the Hotel XSD to validate your hotel feed file before sending it to Bing.
  
- The hotel feed document must use UTF-8 encoding.
  
- The feed must include listings for all your hotels&mdash; the feed process does not support partial updates.
  
- Bing ignores any element or attribute that it does not support.
  
- Elements must be in the order specified in the Hotel XSD.
  
- If your data includes special characters such as apostrophies or quotes, escape them or use CDATA sections. If you escape them, you may use entity codes or character codes. For example, you can escape Paul's as Paul\&apos;s or Paul\&#39;s.
  
- Do not include elements that do not contain data. For example, if you do not provide the geographical coordinates for a hotel, do not include empty \<latitude/\> and \<longitude/\> elements.
    
- Do not use HTML in your XML elements.
  


## Next steps

After creating your feed file, use the [Hotel XSD](https://bhacstatic.blob.core.windows.net/schemas/hotel.xsd) to validate it.

Ask your account manager to import the feed file.

Be sure to also import your points of sale data. For information about creating your points of sale feed file, see [Points of Sale Feed](../pos-feed/pos-feed.md).

After Bing successfully imports your data and is able to match your hotels with properties in Bing Maps, you may begin sending your hotel pricing and availability data. For information, see [Transaction Messages](../transaction-message/transaction-message.md). 
