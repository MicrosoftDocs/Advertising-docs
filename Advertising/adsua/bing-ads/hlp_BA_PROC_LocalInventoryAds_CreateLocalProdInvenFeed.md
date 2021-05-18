---
title: How do I create local product inventory feeds?
description: Learn about creating the local product inventory feed, which is needed for the list of products that you sell in each store specifically for your Local Inventory Ads.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How do I create local product inventory feeds?

> [!IMPORTANT]
> Local Inventory Ads are currently available in Australia, Austria, Belgium, France, Germany, Italy, the Netherlands, Spain, Sweden, Switzerland, the United Kingdom and United States.

After creating a local products feed, you need to create a local products inventory feed for your Local Inventory Ads. The local products inventory feed is needed for the list of products that you sell in each store specifically.

## What is the difference between local product inventory and local product inventory update feeds?

Because your inventory price and quantity change frequently by store, you can use local product inventory update feeds for up-to-date information of your local inventory ads.

When submitting via FTP:

- **Local product inventory feeds**  include all of your inventory for all of your stores. You submit the feed on a daily basis.
- **Local product inventory update feeds**  are used only for frequently changing details like the price and quantity of your items in specific stores.

## Availability

We are working with retailers who have physical stores in the United Kingdom and United States.

## How do I create a local products inventory feed?

1. Create a feed file that is tab-delimited plain text with the following extensions: .txt, .zip, .gz, .gzip, .tar.gz, .tgz. We only support .xml files if it is an existing Google-formatted .xml file.
1. Include the following attributes in your local product inventory feeds.

## Required attributes
<table>
  <tr>
    <th scope="col">Field name</th>
    <th scope="col">Description</th>
    <th scope="col">What you need to know</th>
  </tr>
  <tr>
    <td>
              store code
            </td>
    <td>
              A unique code for the item.
              <para>
                <strong>Example:</strong> 
                 1234
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric
              </para></td>
    <td>
      <ul type="unordered">
        <li>
                  Code must be unique for each store.
                </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
              itemid
            </td>
    <td>
              A unique identifier for the item.
              <para>
                <strong>Example:</strong> 
                 ISI1
              </para><para>
                <strong>Requirements:</strong> 
                 
                50-character limit
              </para></td>
    <td>
      <ul type="unordered">
        <li>ID must be unique for each item in your catalog.</li>
        <li>If you have multiple feeds, IDs of items across different feeds still need to be unique.</li>
        <li>
                  Special ASCII characters (for example, asterisk (*), comma (,), backslash (\), ampersand (&amp;), etc. are allowed.
                </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
              quantity
            </td>
    <td>
              The number of items available in stock.
              <para>
                <strong>Example:</strong> 
                 20
              </para><para>
                <strong>Requirements:</strong> 
                 
                Numeric value
              </para></td>
    <td>
      <ul type="unordered">
        <li>if an item is temporarily out of stock, include "0".</li>
      </ul>
    </td>
  </tr>
</table>

## Optional attributes
<table>
  <tr>
    <th scope="col">Field name</th>
    <th scope="col">Description</th>
    <th scope="col">What you need to know</th>
  </tr>
  <tr>
    <td>
              price
            </td>
    <td>
              Base price, excluding tax and shipping, submitted in local currency.
              <para>
                <strong>Example:</strong> 
                 23.99
              </para><para>
                <strong>Requirements:</strong> 
                 
                Numeric
                <para>0.00 to 10000000.00 (10 million)</para><para>Use two decimal places and no symbols (e.g. $).</para></para></td>
    <td>
      <ul type="unordered">
        <li>The price from the landing page of your offer must be the same price as indicated in the feed. </li>
        <li>The store-level values in the inventory feed will override the national level values from the local products feed.</li>
        <li>
                  For the US, exclude tax in the price. For the UK, include any value added tax (VAT) in the price. See [Microsoft Merchant Center feed tax policy](./hlp_BA_CONC_BMCTax.md) for more details.
                </li>
        <li>Uploading an item for the first time will be pending review until the price has been successfully reviewed. Updating the price of an existing item will be reverted to the pending review status until it has been processed again. The pricing update can take up to 6 hours to process. </li>
        <li>For mobile devices or tablets, the price can be 0, as the subsidized price with a contract is allowed. For such items, you must include the phrase "only with contract" (or similar) in the title with the product_category value of "Electronics &gt; Communications &gt; Telephony &gt; Mobile Phones" (267) for mobile devices or "Electronics &gt; Computers &gt; Tablet Computers" (4745) for tablets.</li>
        <li>For mobile devices or tablets, the price can be 0 when payment options with multiple installments are allowed (US only). For such items, you must include the phrase "with installment plan" (or similar) in the title with the product_category value of "Electronics &gt; Communications &gt; Telephony &gt; Mobile Phones" (267) for mobile devices or "Electronics &gt; Computers &gt; Tablet Computers" (4745) for tablets.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
              sale_price
            </td>
    <td>
              Item’s sale price, excluding tax and shipping
              <para>
                <strong>Example:</strong> 
                 20.99
              </para><para>
                <strong>Requirements:</strong> 
                 
                Numeric; Range is 0.00 to 10000000.00 (10 million); No symbols ($)
              </para></td>
    <td>
      <ul type="unordered">
        <li>
                  For the US, exclude tax in the price. For the UK, include any value added tax (VAT) in the price. See [Microsoft Merchant Center feed tax policy](./hlp_BA_CONC_BMCTax.md) for more details.
                </li>
        <li>The store-level values in the inventory feed will override the national level values from the local products feed.</li>
        <li>Uploading an item for the first time will be pending review until the price has been successfully reviewed. Updating the price of an existing item will be reverted to the pending review status until it has been processed again. The pricing update can take up to 6 hours to process. </li>
        <li>For mobile devices or tablets, the price can be 0, as the subsidized price with a contract is allowed. For such items, you must include the phrase "only with contract" (or similar) in the title with the product_category value of "Electronics &gt; Communications &gt; Telephony &gt; Mobile Phones" (267) for mobile devices or "Electronics &gt; Computers &gt; Tablet Computers" (4745) for tablets.</li>
        <li>For mobile devices or tablets, the price can be 0 when payment options with multiple installments are allowed (US only). For such items, you must include the phrase "with installment plan" (or similar) in the title with the product_category value of "Electronics &gt; Communications &gt; Telephony &gt; Mobile Phones" (267) for mobile devices or "Electronics &gt; Computers &gt; Tablet Computers" (4745) for tablets.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
              sale_price_effective_date
            </td>
    <td>
              Sale’s start and end date and time
              <para>
                <strong>Example:</strong> 
                 2013-11-05T08:15-05:00/2013-11-10T09:30-05:00
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric; Start date must be earlier than end date.  
                Date and time format: YYYY-MM-DD followed by the letter 'T', the time of day followed by an expression for the time zone as defined by the ISO 8601 standard.
              </para></td>
    <td>
      <ul type="unordered">
        <li>The end date needs to be in the same format.</li>
        <li>The store-level values in the inventory feed will override the national level values from the local products feed.</li>
        <li>For items on sale, submit both the sale price and sale effective date attributes. If you update the sale price attribute but not the sale price effective date, the sale price will continue to be used for your item. </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
              availability
            </td>
    <td>
              Availability of item
              <para>
                <strong>Example:</strong> 
                  in stock
                  out of stock
                  preorder
              </para><para>
                <strong>Requirements:</strong> 
                 
                Valid options: in stock, out of stock, preorder. <para>Default is "in stock."</para></para></td>
    <td>
      <ul type="unordered">
        <li>If no values are provided, the availability will be set to "in stock" by default.</li>
        <li>Uploading an item for the first time will be pending review until the availability has been successfully reviewed. Updating the availability of an existing item will be reverted to the pending review status until it has been processed again. The update can take up to 6 hours to process. </li>
        <li>“in stock” products are available for sale and the advertiser is accepting and fulfilling orders. </li>
        <li>“out of stock” products are either unavailable or the advertiser wants to exclude these products from being served temporarily. </li>
        <li>“preorder” products haven’t been released yet but advertiser will accept orders and ship at the availability date.</li>
        <li>
                  Mapping details:
                   in stock: InStock, LimitedAvailability
                   out of stock: Discontinued, OutOfStock, SoldOut
                   preorder: PreOrder, PreSale
                </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>weeks of supply</td>
    <td>
              The estimate of how many weeks of inventory you have.
               
              <strong>Example</strong> :
               3.5
            </td>
    <td>
      <ul>
        <li>Divide the quanitiy of the items available by the average of weekly items sold.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>pick up method</td>
    <td>
              Pick-up options available for the store.
               
              <strong>Example</strong> :
               reserve
               
              <strong>Requirements</strong> :
               
              buy, reserve, and not supported
            </td>
    <td>
      <ul>
        <li>buy: The purchase occurs online.</li>
        <li>reserve: The item is reserved online but purchased in-store.</li>
        <li>not supported: The item is available only online and not for store pick-up.</li>
        <li>Can either be at the local feed level or the inventory feed level.</li>
        <li>The store level values in the inventory feed will override the national level values from the local products feed.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>pick up sla</td>
    <td>
              The expected date that an item is available for pick-up.
               
              <strong>Example</strong> :
               same day
               
              <strong>Requirements</strong> :
               
              same day, next day
            </td>
    <td>
      <ul>
        <li>same day: The item is available for pick-up the same day it was ordered.</li>
        <li>next day: The item is available for pick-up the day after it was ordered.</li>
        <li>Can either be at the local feed level or the inventory feed level.</li>
        <li>The store level values in the inventory feed will override the national level values from the local products feed.</li>
      </ul>
    </td>
  </tr>
</table>

## How do I submit local product feeds?
Once you created your local products feed, you must submit your product information through Microsoft Merchant Center.

1. On the top menu, click **Tools** and then click ** Microsoft Merchant Center**  (or from the global menu at the top of the page, click **Tools** and then **Microsoft Merchant Center**).
1. Click the store name and then the **Feed management** tab.
1. Click **Create feed**.
1. Enter the **Feed information**. Enter the **Feed name**, select the **Location**, and select the **Feed type**. You can select from three different feed types: Local product inventory, local product inventory update, and local product feed.
1. Enter the **Feed input method** details. You can opt to Automatically download file from URL, upload file using FTP, or manually upload file.
1. Click **Save**.


