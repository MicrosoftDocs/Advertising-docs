---
title: What can I include in my Merchant Promotion feed file?
description: Take a look at what the required and optional fields are for your Merchant Promotion feed file.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# What can I include in my Merchant Promotion feed file?

<content_tile class="training">      [        New to Microsoft Shopping Campaigns? Learn how to get started in this training course.      ](https://go.microsoft.com/fwlink?LinkId=2129851)    </content_tile>

Your feed file is a text delimited file that contains all the information needed to submit a promotion. For manual uploads, .tsv or .xml file formats are accepted. For FTP uploads (available in the United States only), .tsv, .txt, or .xml file formats are accepted. After you create a feed file, [      submit it to Microsoft Merchant Center    ](./hlp_BA_CONC_BMCWhatIsCatalog.md).

**Availability** : United States, Canada, United Kingdom, Australia, India, France, and Germany on PC and mobile devices.

Here are the required and optional fields you can include in the catalog feed:

## Required Fields
<table type="type1" style="border:0;padding:10px">
  <tr>
    <th scope="col">Field name</th>
    <th scope="col">Description</th>
    <th scope="col">What you need to know</th>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">promotion_id</th>
    <td>
      <para>The unique ID for the promotion.</para>
      <para>
                <strong>Example:</strong> 
                 50off
              </para>
      <para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric
                 
                60-character limit
              </para>
    </td>
    <td>
      <ul type="unordered">
        <li>ID must be unique for each promotion.</li>
        <li>For online promotions that apply to specific products, the promotion_id in the promotions feed must match the promotion_id in the product feed so Microsoft Advertising knows which products apply to the promotion.</li>
        <li>
                  Spaces or symbols (for example, $ or %) are not allowed.
                </li>
        <li>Values must be separated by commas.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              product_applicability
            </th>
    <td>
      <para>Indicates if the promotion is applicable to all products or specific products.</para>
      <para>
                <strong>Valid values:</strong> 
                 
                ALL_PRODUCTS
                 
                SPECIFIC_PRODUCTS
              </para>
    </td>
    <td>
      <ul type="unordered">
        <li>If the promotion is only applicable to specific products, the promotion_id column must be present in the product feeds. This is to ensure that the promotion is mapped to the right products.</li>
        <li>If the promotion applies to all products, the promotion_id does not need to be added in the products feed.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              offer_type
            </th>
    <td>
      <para>Indicates if there is a code or not.</para>
      <para>
                <strong>Valid values:</strong> 
                  NO_CODE
                  GENERIC_CODE
              </para>
    </td>
    <td>
      <ul type="unordered">
        <li>This determines if the coupon code is required to redeem the offer.</li>
        <li>A GENERIC_CODE is a code that is the same for all users.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              long_title
            </th>
    <td>
      <para>The full title of the promotion.</para>
      <para>
                <strong>Example:</strong> 
                 Extra 50% off shoes
              </para>
      <para>
                <strong>Requirements:</strong> 
                 
                60-character limit
              </para>
    </td>
    <td>
      <ul type="unordered">
        <li>
                  The full description of the promotion should be accurate and meet the [editorial requirements](./hlp_BA_CONC_BMC_MerchantPromoPolicies.md).
                </li>
      </ul>
    </td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              promotion_effective_dates
            </th>
    <td>
      <para>Date and time that the promotion will be live on Bing.com.</para>
      <para>
                <strong>Example:</strong> 
                 2016-07-07T01:00:00-08:00/2016-08-07T01:00:00-08:00
              </para>
      <para>
                <strong>Requirements:</strong> 
                 
                Format is Start-Date-Time/End-Date-Time
              </para>
    </td>
    <td>
      <ul type="unordered">
        <li>The promotion must be live on your website to be live on Bing.com.</li>
        <li>Separate the start and end date with a forward slash (/).</li>
        <li>The start and end date format is: (YYYY-MM-DD), followed by the letter T, then the time of day when the promotion starts, followed by the time zone expression as defined by the ISo 8601 standard. For example:
                  If you want your promotion to run from 1:00 p.m. on July 7, 2016, to 1:00 p.m. on August 7, 2016 (Pacific Standard Time), you would submit: 2016_07-07T13:00:00-08:00/2016-08-07T13:00:00-08:00. 
                  If you want your promotion to run from 1:00 p.m. on July 7, 2016, to 1:00 p.m. on August 7, 2016 (Greenwich Mean Time), you would submit: 2016_07-07T13:00:00-00:00/2016-08-07T13:00:00-00:00.
                    If you want your promotion to run from 1:00 p.m. on July 7, 2016, to 1:00 p.m. on August 7, 2016 (Eastern Standard Time), you would submit: 2016_07-07T13:00:00-05:00/2016-08-07T13:00:00-05:00.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              redemption_channel
            </th>
    <td>
      <para>Indicates if the promotion is online.</para>
      <para>
                <strong>Valid value:</strong> 
                 ONLINE
              </para>
    </td>
    <td></td>
  </tr>
</table>

## Optional Fields
<table type="type1" style="border:0;padding:10px">
  <tr>
    <th scope="col">Field name</th>
    <th scope="col">Description</th>
    <th scope="col">What you need to know</th>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              generic_redemption_code
            </th>
    <td>
      <para>The text code that customers use online.</para>
      <para>
                <strong>Example:</strong> 
                 EXTRA50
              </para>
      <para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric
                 
                60-character limit
              </para>
    </td>
    <td>
      <ul type="unordered">
        <li>This code is provided only when offer_type has a value of GENERIC_CODE.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              promotion_display_dates
            </th>
    <td>
      <para>Date and time that the promotion will be live on Bing.com that falls within the promotion_effective_dates.</para>
      <para>
                <strong>Example:</strong> 
                 2016-07-07T01:00:00-08:00/2016-08-07T01:00:00-08:00
              </para>
      <para>
                <strong>Requirements:</strong> 
                 
                Format is Start-Date-Time/End-Date-Time
              </para>
    </td>
    <td>
      <ul>
        <li>This can be used with promotion_effective_date to validate promotions before they are active.</li>
        <li>Separate the start and end date with a forward slash (/).</li>
        <li>
                  The start and end date format is: (YYYY-MM-DD), followed by the letter T, then the time of day when the promotion starts, followed by the time zone expression as defined by the ISo 8601 standard. For example:
                    If you want your promotion to run from 1:00 p.m. on July 7, 2016, to 1:00 p.m. on August 7, 2016 (Pacific Standard Time), you would submit: 2016_07-07T13:00:00-08:00/2016-08-07T13:00:00-08:00.
                    If you want your promotion to run from 1:00 p.m. on July 7, 2016, to 1:00 p.m. on August 7, 2016 (Greenwich Mean Time), you would submit: 2016_07-07T13:00:00-00:00/2016-08-07T13:00:00-00:00.
                    If you want your promotion to run from 1:00 p.m. on July 7, 2016, to 1:00 p.m. on August 7, 2016 (Eastern Standard Time), you would submit: 2016_07-07T13:00:00-05:00/2016-08-07T13:00:00-05:00.
                </li>
      </ul>
    </td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              minimum_purchase_amount
            </th>
    <td>
      <para>The minimum amount of purchase for the promotion to be applicable.</para>
      <para>
                <strong>Example:</strong> 
                 15 USD
              </para>
      <para>
                <strong>Requirements:</strong> 
                 
                Numerical
                 No symbols (for example, $)
              </para>
    </td>
    <td>
      <ul type="unordered">
        <li>Only currencies in the specified country/region are supported.</li>
      </ul>
    </td>
  </tr>
</table>

 

