---
title: Unique identifiers for your product ads
description: Use unique product identifiers to add userful information to your products.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Unique identifiers for your product ads

Unique product identifiers like brand, gtin, and mpn are used to define a product in a global marketplace. Tagging your products with unique identifiers makes it easier for customers to find your products. Learn more about [how the feed file is organized](./hlp_BA_CONC_AboutBingMerchantCenterCatalogFile.md).

## Types of unique product identifiers

<table>
  <tr>
    <th scope="col">gtin - Universal Product Code (UPC)</th>
  </tr>
  <tr>
    <td>
      <para>
          <strong>Used</strong> : Primarily in North America
        </para>
      <para>
          <strong>Format</strong> : 12 numeric digits
        </para>
      <para>
          <strong>What you need to know</strong> :
          <ul><li>Also called GTIN-12 and UPC-A.</li><li>A unique numerical value for commercial products usually appearing under the barcode printed on retail products.</li></ul></para>
    </td>
  </tr>
  <tr>
    <th scope="col">gtin - European Article Number (EAN)</th>
  </tr>
  <tr>
    <td>
      <para>
          <strong>Used</strong> : Primarily outside of North America
        </para>
      <para>
          <strong>Format</strong> : 13 numeric digits but can be either 8 or 14 numeric digits
        </para>
      <para>
          <strong>What you need to know</strong> :
          <ul><li>Also called GTIN-13.</li><li>A unique numerical value for commercial products usually appearing under the barcode printed on retail products.</li></ul></para>
    </td>
  </tr>
  <tr>
    <th scope="col">gtin - Japanese Article Number (JAN)</th>
  </tr>
  <tr>
    <td>
      <para>
          <strong>Used</strong> : Only in Japan
        </para>
      <para>
          <strong>Format</strong> : 8 or 13 numeric digits
        </para>
      <para>
          <strong>What you need to know</strong> :
          <ul><li>Also called GTIN-13.</li><li>A unique numerical value for commercial products usually appearing under the barcode printed on retail products.</li></ul></para>
    </td>
  </tr>
  <tr>
    <th scope="col">gtin - International Standard Book Number (ISBN)</th>
  </tr>
  <tr>
    <td>
      <para>
          <strong>Used</strong> : Globally
        </para>
      <para>
          <strong>Format</strong> :
          <ul><li>ISBN-10: 10 numeric digits</li><li>ISBN-13 (recommended): 13 numeric digists, typically starting with 978 or 979</li></ul></para>
      <para>
          <strong>What you need to know</strong> : A unique numerical value for commercial books published since 1970 that is on the back of the book with the barcode.
        </para>
    </td>
  </tr>
  <tr>
    <th scope="col">brand</th>
  </tr>
  <tr>
    <td>
      <para>
          <strong>Used</strong> : Globally
        </para>
      <para>
          <strong>What you need to know</strong> : The brand of the product.
        </para>
    </td>
  </tr>
  <tr>
    <th scope="col">mpn - Manufacturer Part Number (MPN)</th>
  </tr>
  <tr>
    <td>
      <para>
          <strong>Used</strong> : Globally
        </para>
      <para>
          <strong>Format</strong> : Alphanumeric digits
        </para>
      <para>
          <strong>What you need to know</strong> : The unique number that identifies the product to its manufacturer.
        </para>
    </td>
  </tr>
</table>

## What unique product identifiers are needed and how will they be enforced?

We recommend that you tag all three attributes for all your items, as they help to define your products in a global marketplace. Take a look at the policies for using product identifiers in the feed below.

- **New products** : Submit all three attributes for new products that have GTINs:       
   1. **gtin** assigned by manufacturer
   1. **brand**
   1. **mpn** assigned by manufacturer

- **Products without GTINs** : For products that don’t have a GTIN, submit **brand** and **mpn**. Examples of products without GTINs include store brand products, antique products, replacement parts, custom-made products, etc.
- **Products without a brand** : Submit the **brand** attribute only if the product has a clear brand or manufacturer associated.
- **Products without a GTIN, brand, or mpn** : For products that don’t have all three identifiers, submit **identifier_exists**  with the value set to **FALSE**. Examples of products without unique identifiers include custom handmade products, vintage products, etc.

## Troubleshooting GTIN issues

## Where can I find the unique product identifiers?
Each product has a specific GTIN assigned by the manufacturer, so make sure you always use the exact values. To find unique product identifiers, you can:

- Check the packaging of the product. GTINs appear below the barcode on the product’s packaging.
- Contact the manufacturer.
- Check on ISBNdb.com.

## How do I know if my GTIN is correct?
Here are some ways you can check to see if your GTIN is correct:

- **Check the number of digits** . Each GTIN has a specific number of digits (refer to the table above), so make sure you have the correct number of digits.
- **Use only numbers** .
- **Check the check digit or letter for ISBN-10** . The last digit in the GTIN is a computer check digit to ensure that the unique identifier is correct. Use the [GS1 Check Digit Calculator](https://go.microsoft.com/fwlink?LinkId=849051) to calculate the check digit.
- **Check the restricted range numbers** . Restricted ranges (prefixes of 2, 02, and 04) and coupon ranges (05, 981, 982, and 983) should not be included in GTINs.

Download the [GS1 GTIN validation guide](https://go.microsoft.com/fwlink?LinkId=849052) for additional information.


