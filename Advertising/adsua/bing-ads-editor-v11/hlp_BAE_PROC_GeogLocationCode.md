---
title: How can I get location target codes?
description: Learn how to manage location targets in bulk in Microsoft Advertising Editor.
ms.service: "Bing-Ads-Editor-v11"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How can I get location target codes?

Microsoft Advertising Editor makes it easy to manage location targets in bulk, using either the multiple changes tool in the **Locations** tab or an import file. Either way, you’ll need to use the location codes for the location targets that you’re trying to add.

1. Go to the [Geographical location codes](https://go.microsoft.com/fwlink?LinkId=536556) page and sign in to the developer portal.
1. Select the location codes file based on your language preference.
1. Once you download the applicable GeoLocations .csv file, filter the data in the file based on the type of target you are trying to add (e.g., Country, City, MetroArea, PostalCode, or State).
1. Check the **Display Name** column to find the location that you would like to add to your campaign/ad group.
1. Find the correct corresponding code for the selected location from the **Location ID** column.
Let's say you're using the multiple changes tool to target the city of Seattle with a 10% bid adjustment. You'd enter the following in the tool (the value from the **Location ID** column in the file should be assigned to the **Target** column):

|Target|Bid Adjustment|ID|
|---|---|---|
|67560|10|71287|

Or if you were doing a file import using the Microsoft Advertising file format, the value from the **Location ID** column in the file should be assigned to the **Target** column in your import file.

Note: The ID column is the ID of your location target in Microsoft Advertising. If you want to update existing location targets, include the ID, otherwise, it should be blank if it's a new location target.


