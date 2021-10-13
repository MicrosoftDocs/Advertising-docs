---
title: About the installment attribute for product ads
description: The installment attribute for product ads is the monthly installment plan for a product, displayed by the number of months.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# About the installment attribute for product ads

<content_tile class="training">	[	New to Microsoft Shopping Campaigns? Learn how to get started in this training course.	](https://go.microsoft.com/fwlink?LinkId=2129851)	</content_tile>

The installment attribute for product ads is the monthly installment plan for a product, displayed by the number of months. You can include the installment pricing with or without a down payment for relevant offers, to display the most accurate pricing options for your products.

## Why use installment pricing?

- **Increased traffic volume** . Displaying your most accurate pricing in your ads help to grow ad engagement boost your potential click-through rate.
- **More informed shoppers** . Providing installment pricing and any down payment costs to potential customers provides them with more information before purchasing.
- **Improved market share** . Displaying a more accurate pricing option can encourage customers to click your ad instead of your competitors’ ads.

## Installment attribute requirements
- This attribute can only be applied to mobile and tablet product categories. The installment field will be ignored for all other categories.
- The price attribute will be treated as the down payment and the installment amount will account for the remaining monthly installments.
- For mobile devices or tablets, the price can be 0 when payment options with multiple installments are provided. For such items, you must include the product_category values:
   - 4745 - Electronics > Computers > Tablet Computers
   - 267 - Electronics > Communications > Telephony > Mobile Phones
   - Electronics > Communications > Telephony > Mobile Phones > Feature Phones
   - Electronics > Communications > Telephony > Mobile Phones > Smartphones
   - Electronics > Communications > Telephony > Mobile Phones > Watch Phones

## Installment attribute format
- **Months**: The number of installments, displayed as an integer with a range from 1 to 1000.
- **Amount**: The amount paid per month, displayed as a number greater than 0 with two decimals in the local currency, with no symbols (for example, $).

If you have a single product with both full price and installment price, add two rows for the same product in the feed.

- One row will be for the full price to be submitted in the price field.
- The other row will be for the installment price, with the upfront cost in the price field and the installment months and price in the installment field.

For example, let’s say the full price for the product is $900 and the installment cost is $0. For installment pricing, the upfront cost is $0 and the installment price is $30 for 30 months.

## What file formats support the installment attribute?
- Text feeds
- XML feeds
- Google import
- CAPI: XML, JSON

## Why was my offer containing the installment attribute rejected?
Here are some possible reasons why the installment attribute was rejected:

- The installment doesn’t contain the **months** attribute.
- **Months** is not an integer.
- **Amount** is the same format as the price attribute.
- **Installment** is provided but **months** is 0.
- **Price** is 0 but the **installment** is not provided.
- **Price** is 0 but the **amount** is not present or is 0.
- **Months** is less than 1 or greater than 100.
- The account currency is different from the price currency.

## What I need to know
- The price attribute is the up-front payment and the installment attribute is the monthly installments.
- The currency used in the installment attribute must match the currency used for the price attribute.
- The installment amount must be greater than 0.00 USD.
- The installment attribute is available only for mobile and tablet category of products. For any other categories, the installment attribute will be ignored.


