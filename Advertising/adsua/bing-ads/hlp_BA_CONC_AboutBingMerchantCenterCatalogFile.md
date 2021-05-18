---
title: How is the feed file organized?
description: Learn the details of each field that can be in your Microsoft Merchant Center feed file.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How is the feed file organized?

<content_tile class="training">      [        New to Microsoft Shopping Campaigns? Learn how to get started in this training course.      ](https://go.microsoft.com/fwlink?LinkId=2129851)    </content_tile>

Your feed file is a text delimited file that has a different product item on each line. You create the text delimited file and then [      submit it to Microsoft Merchant Center    ](./hlp_BA_CONC_BMCWhatIsCatalog.md).

You can find the rules for creating the feed file at [How do I create a feed file?](./hlp_BA_PROC_BMCCreateFeedFile.md) If you're using Google feed files, make it even easier to import by using the Google Merchant Center import tool. [Learn more](./hlp_BA_CONC_BMC_GMCImportIntro.md)

Here are the required and optional fields you can include in the feed:

## Required Fields
<table>
  <tr>
    <th scope="col">Field name</th>
    <th scope="col">Description</th>
    <th scope="col">What you need to know</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">id</th>
    <td>
              A unique identifier for the item.
              <para>
                <strong>Example:</strong> 
                 ISI1
              </para><para>
                <strong>Requirements:</strong> 
                 
                50 Unicode character limit
                 
                <strong>Recommended:</strong>  ASCII only: alphanumeric, underscores (_), and dashes (-)

              </para></td>
    <td>
      <ul type="unordered">
        <li>ID must be unique for each item in your feed per market.</li>
        <li>If you have multiple feeds, IDs of items across different feeds still need to be unique.</li>
        <li>
                  Special ASCII characters (e.g., asterisk (*), comma (,), backslash (\), ampersand (&amp;), etc. are allowed.
                </li>
        <li>The ID is the same as the merchant product ID (MPID).</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              title
            </th>
    <td>
              Title of the item
              <para>
                <strong>Example:</strong> 
                 Women's shoes
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric
                 150 character limit
                 Don't enclose in quotes
              </para></td>
    <td>
      <ul type="unordered">
        <li>Use relevant titles that match with what users are searching for with key information first in the title (e.g., Women’s over the knee boots).</li>
        <li>When applicable, we recommend you include gender, size, color, material, and pattern details in title (e.g., Women’s small red wool sweater).</li>
        <li>Include characteristics like color to differentiate from other products.</li>
        <li>Do not include promotional text (e.g., Free shipping) or use all caps (e.g., WOMEN’S SHOES).</li>
        <li>Uploading an item for the first time will be pending review until the offer title has been successfully reviewed. Updating the offer title of an existing item will be reverted to the pending review status until it has been successfully reviewed again. The review process can take up to 3 business days.</li>
        <li>The title of the item can be slightly different, but it must be for the same item.</li>
        <li>For mobile devices or tablets, the price can be 0 when payment options with multiple installments are provided. For such items, you must include the product_category value of "Electronics &gt; Communications &gt; Telephony &gt; Mobile Phones" (267) for mobile devices or "Electronics &gt; Computers &gt; Tablet Computers" (4745) for tablets.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              link
            </th>
    <td>
              Direct URL of the item's page on your website
              <para>
                <strong>Example:</strong> 
                  http://www.contoso.com/ 
                product.asp?pn=ISI1
              </para><para>
                <strong>Requirements:</strong> 
                 
                0-2000 characters
                 HTTP or HTTPs only and no redirects. For redirect URLs, use the ads_redirect field.
              </para></td>
    <td>
      <ul type="unordered">
        <li>Link should point to the specific product instead of your store’s home page or pages with multiple products.</li>
        <li>The Product URL domain must match the Store URL domain.</li>
        <li>
                  Must be a path under your store's destination URL. For aggregators, this must be a direct link to the seller's product page. Aggregators are third party sites that consolidate items to Bing on behalf of individual merchants. In the feed that an aggregator submits, the link attribute must be a direct link to the seller's product page and the seller-name attribute is required. Adding items submitted on behalf of the merchant must comply with our policies and [Terms of Service](./hlp_BA_CONC_EditorialGuidelines.md).
                </li>
        <li>Uploading an item for the first time will be pending review until the product URL has been successfully reviewed. Updating the product URL of an existing item will be reverted to the pending review status until it has been successfully reviewed again. The review process can take up to 3 business days.</li>
        <li>Use as few redirects as possible and be sure that the redirects go to the same verified store domains to avoid offer rejections.</li>
        <li>Do not require customers to register, sign in, or take other actions to view information about your product. Make sure customers see your final landing page immediately after clicking your ad.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              price
            </th>
    <td>
              Base price, excluding tax and shipping, submitted in local currency.
              <para>
                <strong>Example:</strong> 
                 23.99
              </para><para>
                <strong>Requirements:</strong> 
                 
                Numeric
                0.00 to 10000000.00 (10 million)
                
               <para></para>Use two decimal places and no symbols (e.g.. $)
              </para></td>
    <td>
      <ul type="unordered">
        <li>The price from the landing page of your offer must be the same price as indicated in the feed. </li>
        <li>
                  For the United States, exclude tax in the price. For the United Kingdom, include any value added tax (VAT) in the price. See [Microsoft Merchant Center feed tax policy](./hlp_BA_CONC_BMCTax.md) for more details.
                </li>
        <li>Uploading an item for the first time will be pending review until the price has been successfully reviewed. Updating the price of an existing item will be reverted to the pending review status until it has been processed again. The pricing update can take up to 6 hours to process. </li>
        <li>For mobile devices or tablets, the price can be 0 when payment options with multiple installments are provided. For such items, you must include the product_category value of "Electronics &gt; Communications &gt; Telephony &gt; Mobile Phones" (267) for mobile devices or "Electronics &gt; Computers &gt; Tablet Computers" (4745) for tablets.</li>
        <li>Auction price is not allowed. The price must be a fixed price for the product.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              description
            </th>
    <td>
              Item description
              <para>
                <strong>Example:</strong> 
                 Bright yellow 100% cotton dress shirt
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric
                 10000 character limit
                 No HTML code and no promotional text
                 Do not enclose in quotes
              </para></td>
    <td>
      <ul type="unordered">
        <li>The description from the landing page of your offer must be the same description as indicated in the feed. </li>
        <li>We recommend that you include size, color, and pattern when applicable.</li>
        <li>User relevant description with the most important data at the front.</li>
        <li>Uploading an item for the first time will be pending review until the description has been successfully reviewed. Updating the description of an existing item will be reverted to the pending review status until it has been successfully reviewed. The review process can take up to 3 business days. </li>
        <li>The description of the item can be slightly different, but it must be for the same item.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              image_link
            </th>
    <td>
              URL of an image of the item
              <para>
                <strong>Example:</strong> 
                 http://www.contoso.com/ images/ISI1.jpg
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric
                 1000 character limit
                 Link must be HTTP or HTTPs only
                 Image must be: bmp, gif, exif, jpg, png, tiff
                 The recommended minimum size is 220px by 220px
                 The image size cannot exceed 3.9 MB
                 No watermarks or free shipping text
                 Only one image per item
              </para></td>
    <td>
      <ul type="unordered">
        <li>Do not include any text within your images, including promotional messaging.</li>
        <li>Use images with a white background for a “pop” effect.</li>
        <li>
                  Update robots.txt file to allow Microsoft Advertising to crawl your site. Your ad cannot be served if the crawling is incomplete. [Learn more](https://go.microsoft.com/fwlink?LinkId=690094).
                </li>
        <li>The image link URL is case-sensitive. Changing the casing on the URL will cause the URL to be re-crawled.</li>
        <li>Uploading an item for the first time will be pending review until the image URL has been successfully crawled. Updating the image URL of an existing item will be reverted to the pending review status until it has been successfully re-crawled. The review process can take up to 3 business days. </li>
        <li>If you have updated the image, be sure to update the image URL for the new image to be reflected in the ad.</li>
        <li>If the images aren't displaying because the URL is missing an image or the image size is too large or small, update the URL for the offer so it can be reviewed in the next crawl.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">shipping</th>
    <td>
              Cost of shipping, submitted in local currency. This is a required field for Austria and Germany only.<para><para>Shipping has multiple subfields and can have the following headers:</para><ul><li>shipping(price)</li><li>shipping(country:price)</li><li>shipping(country:service:price)</li><li>shipping</li></ul>
                <strong>Example:</strong> 
                 
                12.99
              </para><para>
                <strong>Requirements:</strong> 
                 Numeric
                 0.01 to 10000000.00 (10 million)
                 Use two decimal places and no symbols (e.g., €)
                 For free shipping, use 0
              </para></td>
    <td>
      <ul type="unordered">
        <li>The shipping field is required for Austria and Germany only.</li>
        <li>Multiple shipping prices for any item is accepted. For example, DE:Standard:10, DE:Express:20, and DE:Same Day:30 can be used for the same item.</li>
        <li>The format depends on the attribute name in the header row of the feed file and the order of the values must match the order in the attribute name. For example, shipping(country:price) must be DE:6.49 or shipping(country:service:price) must be DE:Standard:12.99</li>
        <li>Each sub-attribute needs to be separate with a colon and each delivery attribute group needs to be separated with a comma.</li>
        <li>If a country is not included, the shipping price will apply to the target country of the item by default.</li>
        <li>Uploading an item's shipping for the first time will be pending review until the shipping has been successfully reviewed. This can take up to 30 hours to process. Updating the shipping of an existing item will be reverted to the pending review status until it has been processed again. The shipping update can take up to 8 hours to process. </li>
      </ul>
    </td>
  </tr>
</table>

## Required (if value is assigned by the manufacturer) - Item Identification
<table>
  <tr>
    <th scope="col">Field name</th>
    <th scope="col">Description</th>
    <th scope="col">What you need to know</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              mpn
            </th>
    <td>
              Manufacturer Part Number
              <para>
                <strong>Example:</strong> 
                 ADNK-5020
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric
                  
                70 character limit
              </para></td>
    <td>
      <ul type="unordered">
        <li>MPN should be specific to one unique product.</li>
        <li>MPNs are assigned by the manufacturer.</li>
        <li>
                  Learn more about [unique identifiers for your product ads](./hlp_BA_CONC_BMC_UniqueIdentifiers.md).
                </li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              gtin
            </th>
    <td>
              Global Trade Item Number. 
                Up to 10 GTIN values can be provided, with a maximum of 14 digits per value. For multiple GTIN values, separate by a comma and space.
              <para>
                <strong>Example:</strong> 
                 00012345600012
              </para><para>
                <strong>Requirements:</strong> 
                 
                Numeric
                 14 digits max per value  
                 Multi-value
              </para></td>
    <td>
              Learn more about [unique identifiers for your product ads](./hlp_BA_CONC_BMC_UniqueIdentifiers.md).
            </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              brand
            </th>
    <td>
              Item’s manufacturer, brand or publisher
              <para>
                <strong>Example:</strong> 
                 Contoso
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric
                 70-character limit
					  10-word limit
              </para></td>
    <td>
      <ul type="unordered">
        <li>Do not add your store name as the brand unless you manufacture the product.</li>
        <li>We recommend to keep the brand character limit to 70, but it can be up to 1000 characters.</li>
        <li>The maximum word limit is 10.</li>
        <li>Uploading an item for the first time will be pending review until the brand has been successfully crawled. Updating the brand of an existing item will be reverted to the pending review status until it has been successfully re-crawled. The review process can take up to 3 business days. </li>
        <li>
                  Learn more about [unique identifiers for your product ads](./hlp_BA_CONC_BMC_UniqueIdentifiers.md).
                </li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">identifier_exists (required for new products only when gtin and brand, or mpn and brand isn't available)</th>
    <td>
              Used to indicate that unique product identifiers (gtin, brand, and mpn) aren't available for a product.
              <para>
                <strong>Example</strong> : 
                FALSE  
                <strong>Requirements</strong> : 
                Boolean: TRUE or FALSE
              </para></td>
    <td>
      <ul>
        <li>Products that may not have an identifier_exists attribute include custom goods, like homemade products, or products that were made before gtins were created, like antiques.</li>
        <li>
                  Learn more about [unique identifiers for your product ads](./hlp_BA_CONC_BMC_UniqueIdentifiers.md).
                </li>
      </ul>
    </td>
  </tr>
</table>

## Optional Fields - Apparel Products
<table>
  <tr>
    <th scope="col">Field name</th>
    <th scope="col">Description</th>
    <th scope="col">What you need to know</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              gender
            </th>
    <td>
              Gender targeted by the item
              <para>
                <strong>Example:</strong> 
                 male
              </para><para>
                <strong>Requirements:</strong> 
                 
                Valid options: male, female, unisex. No other option will be accepted.
              </para></td>
    <td>
      <ul>
        <li> Required for all Apparel &amp; Accessories products when targeting these countries: France, Germany, United Kingdom, and United States</li>
        <li> Optional for products in the following Apparel &amp; Accessories sub-categories: Pinback Buttons, Tie Clips, Cufflinks, Wristbands, Shoe Covers, Shoelaces, Spurs, Watch Bands, Keychains, Wallet Chains, Lanyards, Checkbook Covers, Badge &amp; Pass Holder, Watch Winders, Watch Stickers &amp; Decals, Handkerchiefs, and Decorative Fans.</li>
        <li>We recommend including gender in the title for products where it's a distinguishing attribute.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              age_group
            </th>
    <td>
              Age group targeted by the item
              <para>
                <strong>Example:</strong> 
                 newborn
              </para><para>
                <strong>Requirements:</strong> 
                 
                Valid Options: newborn, infant, toddler, kids, adult
              </para></td>
    <td>
      <ul>
        <li>
                  Required for all Apparel &amp; Accessories products when targeting these countries: France, Germany, United Kingdom, and United States
                </li>
        <li>
                  Optional for products in the following Apparel &amp; Accessories sub-categories: Pinback Buttons, Tie Clips, Cufflinks, Wristbands, Shoe Covers, Shoelaces, Spurs, Watch Bands, Keychains, Wallet Chains, Lanyards, Checkbook Covers, Badge &amp; Pass Holder, Watch Winders, Watch Stickers &amp; Decals, Handkerchiefs, and Decorative Fans.
                </li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              color
            </th>
    <td>
              The dominant color of the item
              <para>
                <strong>Example:</strong> 
                 red/black/white
              </para><para>
                <strong>Requirements:</strong> 
                 
                Text: Character limit 100
                 Supports up to 3 values separated by a slash [/] with most dominant color first
                 Color attributes, like "stainless steel" or "mahogany" are also accepted
              </para></td>
    <td>
      <ul>
        <li>Required for all Apparel &amp; Accessories products when targeting these countries: France, Germany, United Kingdom, and United States</li>
        <li>We recommend adding the dominant color in the title.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              size
            </th>
    <td>
              Size of the item
              <para>
                <strong>Example:</strong> 
                 small, medium, large
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric
                 Max 100 characters
                 String/Unicode characters
              </para></td>
    <td>
      <ul type="unordered">
        <li>
                  Required for all Apparel &amp; Accessories products when targeting these countries: France, Germany, United Kingdom, and United States
                </li>
        <li>Indicate size values based on your target country.</li>
        <li>Use consistent size values for the same items. (e.g., “small”, “medium”, and “large” and not “small,” “M,” and “Lg”).</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              size_type
            </th>
    <td>
              Size type of the item
              <para>
                <strong>Example:</strong> 
                 regular, petite
              </para><para>
                <strong>Requirements:</strong> 
                 
                Supported values: regular, petite, plus, big and tall, or maternity
              </para></td>
    <td>size_type is recommended when the size attribute is provided.</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              size_system
            </th>
    <td>
              Size system of the item
              <para>
                <strong>Requirements:</strong>  Single value
                 
                Supported values: DE, FR, AU, US, and UK
              </para></td>
    <td>
      <ul>
        <li>If size_system is not provided, the item will default to the size system of the target country.</li>
        <li>size_system is recommended when the size attribute is provided.</li>
      </ul>
    </td>
  </tr>
</table>

## Optional Fields - Product Variants
<table>
  <tr>
    <th scope="col">Field name</th>
    <th scope="col">Description</th>
    <th scope="col">What you need to know</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              item_group_id
            </th>
    <td>
              Used to group items that may vary by color, material, pattern, size, age_group, or gender
              <para>
                <strong>Example:</strong> 
                 XYZ123
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric
                 Max 50 Unicode characters
                 
                <strong>Recommended:</strong> 
                 
                ASCII only: alphanumeric, underscores (_), and dashes (-)
              </para></td>
    <td>
      <ul type="unordered">
        <li>This ID is different from the "ID" attribute.</li>
        <li>Values must be different for items, unless items are variants of the same item.</li>
        <li>At least one of the variant attributes (size, color, material, pattern, age_group, or gender) must be provided and the same variant attribute must be provided for all items within the group.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              material
            </th>
    <td>
              The material of the item
              <para>
                <strong>Example:</strong> 
                 leather/suede/silk
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric: Max 200 characters
                 Supports up to 3 values separated by a slash [/] with most dominant material first
              </para></td>
    <td>Values may be displayed, so we recommend you use values that users can understand.</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              pattern
            </th>
    <td>
              The pattern or graphic print of the item
              <para>
                <strong>Example:</strong> 
                 checkered
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric: Max 100 characters
              </para></td>
    <td>Values may be displayed, so we recommend you use values that users can understand.</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              additional_image_link
            </th>
    <td>
              The URLs of additional images
              <para>
                <strong>Example:</strong> 
                 http://www.contoso.com/ images/ISI1.jpg
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric
                 2000 character limit
                 Link must be HTTP or HTTPs only
                 Image must be: bmp, gif, exif, jpg, png, or tiff
                 The recommended minimum size is 220px by 220px
                 The image size cannot exceed 3.9 MB
                 No watermarks or free shipping text.
              </para></td>
    <td>
              Values may be displayed, so we recommend you use values that users can understand.
               
              Can have up to 10 images, separated by a comma (,) delimiter.
               
              "%2C" value in the image URL should be considered as (,) and part of the image URL link (e.g., 2 image URLs that contain commas will look like: http://www.contoso.com/image2%2C3.jpg,http://  contoso.com/image2%2C4.jpg).
            </td>
  </tr>
</table>

## Optional Fields - Other
<table>
  <tr>
    <th scope="col">Field name</th>
    <th scope="col">Description</th>
    <th scope="col">What you need to know</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              adult
            </th>
    <td>
              Microsoft Advertising does not support adult products.
              <para>
                <strong>Example:</strong> 
                  FALSE
              </para><para>
                <strong>Requirements:</strong> 
                 
                Boolean:TRUE or FALSE
              </para></td>
    <td>Any adult products submitted in the feed will be rejected.</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              availability
            </th>
    <td>
              Availability of item
              <para>
                <strong>Example:</strong> 
                 in stock
                 out of stock
                 preorder
              </para><para>
                <strong>Requirements:</strong> 
                 
                Valid options: in stock, out of stock, preorder. 
                 Default is "in stock."
              </para></td>
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
    <th scope="row" style="font-weight: normal">
              product_category
            </th>
    <td>
              Predefined product category (equivalent to google_product_category)
              <para>
                <strong>Example:</strong> 
                 Software &gt; Computer Software
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric 
                 255 character limit
                 Delimiters: greater than symbol [&gt;].
                 
                Only the greater than symbol &gt; is a valid delimiter. Any other value is treated as invalid.
                 
                <strong>Full list of taxonomy values</strong> :
                
                 <ul><li>
                    [All languages](https://go.microsoft.com/fwlink?LinkId=2118268)
                  </li><li>
                    [Example feed file](https://go.microsoft.com/fwlink?LinkId=506749)
                  </li></ul></para></td>
    <td>
      <ul>
        <li>IDs, instead of string values, are now supported. View the updated taxonomy categories: Taxonomy and Taxonomy with IDs</li>
        <li>For mobile devices or tablets, the price can be 0 when payment options with multiple installments are provided. For such items, you must include the product_category value of "Electronics &gt; Communications &gt; Telephony &gt; Mobile Phones" (267) for mobile devices or "Electronics &gt; Computers &gt; Tablet Computers" (4745) for tablets.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              condition
            </th>
    <td>
              Condition of item
              <para>
                <strong>Example:</strong> 
                 new
              </para><para>
                <strong>Requirements:</strong> 
                 Valid options: new; used; refurbished
                 Default is "new."
              </para></td>
    <td>
      <ul type="unordered">
        <li>If no values are provided, the condition will be set to "new" by default.</li>
        <li>'New' products are brand new and have never been used, with the original packaging never opened.</li>
        <li>'Refurbished' products have been professionally restored, is free of defects, and comes with a warranty. It may or may not have the original packaging.</li>
        <li>'Used' products are anything other than 'new' or 'refurbished,' where the products have been used previously, with the original packaging opened or missing.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              expiration_date
            </th>
    <td>
              The date the item will expire
              <para>
                <strong>Example:</strong> 
                 2015-01-25
              </para><para>
                <strong>Requirements:</strong> 
                 
                ISO 8601 standard format: YYYY-MM-DD
                 Maximum supported is 30 days from date of upload. 
                 The default is 30 days.
              </para></td>
    <td>If the expiration date isn't provided, items will expire after 30 days.</td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              multipack
            </th>
    <td>
              Used when bundling multiple identical items into a single unit
              <para>
                <strong>Example:</strong> 
                 10
              </para><para>
                <strong>Requirements:</strong> 
                 
                Integer, greater than 1
              </para></td>
    <td>
              When setting the price, it must be the <strong>total</strong>  price of the multipack.
            </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              product_type
            </th>
    <td>
              Your category of the item
              <para>
                <strong>Example:</strong> 
                 Home &gt; Electronics &gt; DVD Player
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric
                 750 character limit
                 Delimiters: greater than [&gt;]
              </para></td>
    <td>
              You can have more than one product type if your item applies to more than one category.
            </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              mobile_link
            </th>
    <td>
              Mobile landing page URL
              <para>
                <strong>Example:</strong> 
                 http://www.contosomobile.com/ product.asp
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric
                 Max 2000 character limit
                 Same rules as the link attribute apply
              </para></td>
    <td>
              Link should point to the specific product instead of your store’s home page.
            </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              unit_pricing_measure
            </th>
    <td>
              The measure and dimension of product as it is sold.
              <para>
                <strong>Example:</strong> 
                 1.5 kg
              </para><para>
                <strong>Requirements:</strong> 
                 
                Numeric, plus unit
                 
                <strong>Supported units:</strong> 
                <ul><li>Weight: oz, lb, mg, g, kg</li><li>Volume (US imperial): floz, pt, qt, gal</li><li>Volume: ml, cl, l, cbm</li><li>Length: in, ft, yd, cm, m</li><li>Area: sqft, sqm</li><li>Per unit: ct</li></ul></para></td>
    <td>
      <ul>
        <li>Use the measure or dimension of the product without the packaging. </li>
        <li>Use positive numbers only.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              unit_pricing_base_measure
            </th>
    <td>
              The product’s base measure for pricing (e.g., 100ml means the price is calculated based on a 100ml unit).
              <para>
                <strong>Example:</strong> 
                 100 g
              </para><para>
                <strong>Requirements:</strong> 
                 
                Numeric, plus unit
                 
                <strong>Supported units:</strong> 
                <ul><li>Weight: oz, lb, mg, g, kg</li><li>Volume (US imperial): floz, pt, qt, gal</li><li>Volume: ml, cl, l, cbm</li><li>Length: in, ft, yd, cm, m</li><li>Area: sqft, sqm</li><li>Per unit: ct</li></ul></para></td>
    <td>
      <ul>
        <li>This attribute is optional when you submit unit_pricing_measure.</li>
        <li>Use the same unit of measure for both unit_pricing_measure and unit_pricing_base_measure attributes.</li>
        <li>The price is used to calculate the unit price of the product. For example, if the price is 3 USD, unit_pricing_measure is 150ml, and unit_pricing_base_measure is 100ml, the unit price is 2 USD per 100ml.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              installment
            </th>
    <td>
              The monthly installment plan for a product, displayed by the number of months 
              <para>
                <strong>Example:</strong> 
                 12:15 USD
              </para><para>
                <strong>Requirements:</strong> 
                 
               months: The number of installments, displayed as an integer with a range from 1 to 1000.
			    
				amount: The amount paid per month, displayed as a number greater than 0 with two decimals in the local currency, with no symbols (for example, $).
              </para></td>
    <td>
      <ul>
        <li>The price attribute is the up-front payment and the installment attribute is the monthly installments. </li>
        <li>The currency used in the installment attribute must match the currency used for the price attribute. </li>
        <li>The installment amount must be greater than 0.00 USD.</li>
        <li>The installment attribute is available only for mobile and tablet cateogry of products. For any other categories, the installment attribute will be ignored.</li>
        <li>If you have a single product with both full price and installment price, add two rows for the same product in the feed. 
					<ul><li>One row will be for the full price to be submitted in the price field.</li><li>The other row will be for the installment price, with the upfront cost in the price field and the installment months and price in the installment field.</li></ul></li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
             energy_efficiency_class 
             max_energy_efficiency_class 
             min_energy_efficiency_class 
              (EU and CH only. May be required by local laws or regulations.)
            </th>
    <td>
              The product's energy label
              <para>
                <strong>Example:</strong> 
                 A+
              </para><para>
                <strong>Requirements:</strong> 
                 
                Only the values below are supported:
                <ul><li>G</li><li>F</li><li>E</li><li>D</li><li>C</li><li>B</li><li>A</li><li>A+</li><li>A++</li><li>A+++</li></ul></para></td>
    <td>
      <ul>
        <li>For water heaters, include the energy efficiency class for:
                 
                  Conventional water heaters
                   
                  Solar water heaters
                   
                  Heat pump water heaters
                   
                  Water heater packages
                </li>
        <li>For reversible air conditioners, include the energy efficiency class for heating during an average season.</li>
      </ul>
    </td>
  </tr>
</table>

## Optional Fields - Bing Attributes
<table>
  <tr>
    <th scope="col">Field name</th>
    <th scope="col">Description</th>
    <th scope="col">What you need to know</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              seller_name
            </th>
    <td>
              Merchant/Store that provides this item
              <para>
                <strong>Example:</strong> 
                 Contoso Shoes
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric
                 255 character limit
                 Only required for aggregators - not applicable for direct merchants
              </para></td>
    <td>
      <ul>
        <li>For aggregators, the direct merchant name as SellerName must be sent per Microsoft policy. For direct merchants, this attribute is optional. Aggregators are third party sites that consolidate items to Bing on behalf of individual merchants. In the feed that an aggregator submits, the link attribute must be a direct link to the seller's product page and the seller-name attribute is required. Adding items submitted on behaf of the merchant must comply with our policies and [Terms of Service](./hlp_BA_CONC_EditorialGuidelines.md).</li>
        <li>seller_name and ads_redirect attributes are accepted via Google-formatted XML feed files.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              ads_redirect
            </th>
    <td>
              Redirect URL that overrides the URL given in the "link" attribute. Ensure that this URL will redirect to the same URL as given in the "link" or "mobile_link" attribute.
              <para>
                <strong>Example:</strong> 
                 http://www.contoso.com/shoe/
              </para><para>
                <strong>Requirements:</strong> 
                 
                Max 2000 characters  
                HTTP, HTTPs, or Google-formatted XML only  
                Must redirect to a landing page  
                See [accepted symbols](./hlp_BA_PROC_BMCCreateFeedFile.md) in feed files
              </para></td>
    <td>
      <ul>
        <li>Uploading an item for the first time will be pending review until the ads redirect URL has been successfully crawled. Updating the ads redirect URL of an existing item will be reverted to the pending review status until it has been successfully re-crawled. The review process can take up to 3 business days.</li>
        <li>Use as few redirects as possible and be sure that the redirects go to the same verified store domains to avoid offer rejections.</li>
        <li>Use a value that will resolve into a valid URL after any parameters or tracking templates are replaced with their final values.</li>
        <li>seller_name and ads_redirect attributes are accepted via Google-formatted XML feed files.</li>
        <li>"bingads_redirect" is an accepted header.
				</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              custom_label_0  
              custom_label_1  
              custom_label_2  
              custom_label_3  
              custom_label_4
            </th>
    <td>
              Use to identify products for ad campaign filters
              <para>
                <strong>Example:</strong> 
                  Best sellers, High ROAS, Winter
              </para><para>
                <strong>Requirements:</strong> 
                 Alphanumeric
                 Max 200 characters
                 Single-value
                 Up to 1000 unique values for each custom label attribute (up to 5000 labels total)
              </para></td>
    <td>Use custom labels to add a value to the label, such as seasonal or sale items.</td>
  </tr>
</table>

## Optional Fields- Sales and Promotions
<table>
  <tr>
    <th scope="col">Field name</th>
    <th scope="col">Description</th>
    <th scope="col">What you need to know</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              sale_price
            </th>
    <td>
              Items’s sale price, excluding tax and shipping
              <para>
                <strong>Example:</strong> 
                 20.99
              </para><para>
                <strong>Requirements:</strong> 
                 
                Numeric
                 Range is 0.00 to 10000000.00 (10 million)
                 No symbols (e.g., $) 
              </para></td>
    <td>
      <ul type="unordered">
        <li>
                  For the United States, exclude tax in the price. For the United Kingdom, include any value added tax (VAT) in the price. See [Microsoft Merchant Center feed tax policy](./hlp_BA_CONC_BMCTax.md) for more details.
                </li>
        <li>Uploading an item for the first time will be pending review until the price has been successfully reviewed. Updating the price of an existing item will be reverted to the pending review status until it has been processed again. The pricing update can take up to 6 hours to process. </li>
        <li>For mobile devices or tablets, the price can be 0 when payment options with multiple installments are provided. For such items, you must include the product_category value of "Electronics &gt; Communications &gt; Telephony &gt; Mobile Phones" (267) for mobile devices or "Electronics &gt; Computers &gt; Tablet Computers" (4745) for tablets.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              sale_price_effective_date
            </th>
    <td>
              Sale’s start and end date and time
              <para>
                <strong>Example:</strong> 
                 2013-11-05T08:15-05:00/2013-11-10T09:30-05:00
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric
                 
                Start date must be earlier than end date. 
                 
                Date and time format: YYYY-MM-DD followed by the letter 'T', the time of day followed by an expression for the time zone as defined by the ISO 8601 standard.
              </para></td>
    <td>
      <ul type="unordered">
        <li>The end date needs to be in the same format.</li>
        <li>For items on sale, submit both the sale price and sale effective date attributes. If you update the sale price attribute but not the sale price effective date, the sale price will continue to be used for your item. </li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight: normal">
              promotion_ID
            </th>
    <td>
              Used to group items by promotion
              <para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric 
                 
                Only underscore (_) and dash (-) symbols allowed
                 
                Max 60 character limit per promotion, with a total of 10 promotions accepted
                 
                Up to 10 promotion IDs can be mapped to an item and must be separated by commas
              </para></td>
    <td>
      <ul>
        <li>If the promotion doesn't apply to a product, you can leave this field blank.</li>
        <li>If the promotion doesn't apply to all products, be sure to map the promotion ID to the correct set of products in the master feed.</li>
        <li>The promotion's date and time is based on your local time zone. Keep this in mind if you want to have the promotion in any other time zone.</li>
      </ul>
    </td>
  </tr>
</table>

 

