---
title: How do I create and submit local product inventory update feeds?
description: Make updates easily to frequently updated product inventory attributes with local product inventory update feeds.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How do I create and submit local product inventory update feeds?

> [!IMPORTANT]
> Local Inventory Ads are currently available in Australia, Austria, Belgium, France, Germany, Italy, the Netherlands, Spain, Sweden, Switzerland, the United Kingdom and United States.

For the product inventory attributes that are updated frequently, like price and quantity, you can easily make updates using local product inventory update feeds.

## When should I use the local product inventory update feed?

We recommend that you submit your full local product inventory feed once a day. But when you want to update only the price and quantity attributes that’s already been submitted in your main local product inventory feed file, you can do so without having to update the entire feed.

## Availability

We are working with retailers who have physical stores in the United Kingdom and United States.

## Upload feed file via FTP (Files under 1GB)

You can use this option if the feed file is smaller than 1GB. This is the recommended option if the feed file is larger than 4MB.

When submitting via FTP:

- The file name must be in the following format: inventoryfeed_{market}.txt (for example, inventoryfeed_enus.txt).
- The supported market values are enus, enuk, dede, frfr, enau, enca, and enin.
- The file name is case sensitive.
- If you send the file with a zip file, both the zip file name and the file name must follow the naming format above.

**FTP server requirements**

The recommended FTP upload mechanism is via an FTP program. It is however possible to do so via the command line or custom scripts (such as Python’s ftplib.FTP module). The FileZilla FTP client is recommended for all platforms.

Use the following settings for file transfer with your FTP client:

- Host: ftps://feeds.adcenter.microsoft.com
- Username: Your store’s FTP user name. Your user name must be 6 - 64 characters and cannot include any special characters. Use only a - z, A- Z, and 0 - 9.
- Password: Your store’s FTP password
- Transfer Mode: Passive

Learn more about [FTP uploads](./hlp_BA_CONC_BMCFTPRequirements.md).

The feed contains the following attributes, as detailed below:

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
        <li>Special ASCII characters (for example, asterisk (*), comma (,), backslash (\), ampersand (&amp;), etc. are allowed.</li>
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
      <ul>
        <li>If an item is temporarily out of stock, include "0".</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
        price (optional)
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
</table>

## Upload feed file
You can use this option if the feed file is smaller than 4MB.

1. On the top menu, click **Tools** and then click ** Microsoft Merchant Center**  (or from the global menu at the top of the page, click **Tools** and then **Microsoft Merchant Center**).
1. Click the store name and then the **Feed management** tab.
1. Click **Create feed**.
1. Enter the **Feed information**. Enter the **Feed name**, select the **Location**, and select the **Feed type**. You can select from three different feed types: Local product inventory, local product inventory update, and local product feed.
1. Enter the **Feed input method** details. You can opt to Automatically download file from URL, upload file using FTP, or manually upload file.
1. Click **Save**.

## File format requirements
- File must be tab delimited plain text with extensions: .txt, .zip, .gz, .gzip, .tar.gz, .tgz.            -	.xml files are also accepted (if Google-formatted).
- The file name must be in the following format: inventoryfeed_{market}.txt (for example, inventoryfeed_enus.txt).
- If uploading via FTP, the file name of .txt or .xml files have to match the file name specified for a catalog’s settings.            In the case of compressed text format, the compressed .txt file inside the archive (.zip, .gz, .gzip, .tar.gz, .tgz) must have the matching file name.
- File must start with a single header row
- Each product offer has to be on a separate line of the file
- Do not include HTML in the text files
- Do not include trailing tabs at the end of lines
- Do not include tabs or line breaks in the middle of offer attributes
- Special/Invalid characters will cause processing problems. Learn more about Accepted Symbols in Feed Files next

## Accepted symbols in feed files
Here are the symbols/special characters and what attribute they are accepted in.

|Symbols|Where you can use|
|---|---|
|Period [.]|Prices, URLs|
|Colon [:]              Question [?]              Forward-slash [/]              Equal [=]|URLs|
|Hyphen [-]|Offer Identifiers where this is valid (eg: ISBN, MPN)|
|Pipe [|]              Comma [,]               Greater [>]|Multi-value fields (MerchantCategory, B_Category, ads_label)|
|Any Unicode symbol|Brand, Title, Description|


