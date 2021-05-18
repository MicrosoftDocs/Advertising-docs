---
title: Setting up Local Inventory Ads
description: This is your one-stop shop to get set up with Local Inventory Ads.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Setting up Local Inventory Ads

> [!IMPORTANT]
> Local Inventory Ads are currently available in Australia, Austria, Belgium, France, Germany, Italy, the Netherlands, Spain, Sweden, Switzerland, the United Kingdom and United States.

We'll show you how set up Local Inventory Ads, walking you through the steps you must take in order.

Need a refresher on Local Inventory Ads? Check out [What are Local Inventory Ads?](./hlp_BA_CONC_LocalInventoryAds_Intro.md)

## 1. Provide store location data
You must import store location data from you Google My Business account to Microsoft Advertising. This is currently the only way to get your store location data set up Local Inventory Ads. You can set up an automated feed for your location data by linking your Microsoft Advertising account to your Google My Business account.

## How do I connect my Google My Business account?
Before you get started, here are a few things to keep in mind:

- The automated feed can only be set up in the UI. The grid in the Shared Library > Business Data > Business location feed will only display location feed items that have been imported into Microsoft Advertising from Google My Business. If the location is deleted in Google My Business, it will be deleted in Microsoft Advertising as well.
- Entries that were deleted in Microsoft Advertising will still be displayed. To see only the active business locations, you can filter the list to display **All but removed**.
- Once the automated business data feed is set up, the data is refreshed every 24 hours.

## What are the required Google My Business fields that I will need?
- Country code
- Business name
- Address line 1
- City
- Province name
- State or province code
- Postal code
- StoreCode
- Store hours
   - SundayHours
   - MondayHours
   - TuesdayHours
   - WednesdayHours
   - ThurdsayHours
   - FridayHours
   - SaturdayHours

## 2. Upload online products information
[Upload online products information](./hlp_BA_CONC_AboutBingMerchantCenterCatalogFile.md): Upload online products feed through Microsoft Merchant Center. If you are already using Microsoft Shopping Campaigns, this step may not be required.

## 3. Submit local products information
For Local Inventory Ads, you must create and submit a local products feed. A local products feed contains all the products that you sell in your stores with attributes describing the products.

## How do I create a local products feed?

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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              itemid
									</th>
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
        <li>If you are already using an online products feed, we recommend matching this value to the ID value in the online products feed.</li>
        <li>If you have multiple feeds, IDs of items across different feeds still need to be unique.</li>
        <li>
                  Special ASCII characters (for example, asterisk (*), comma (,), backslash (\), ampersand (&amp;), etc. are allowed.
											</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
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
											<para>150 character limit.</para><para>Don't enclose in quotes.</para></para></td>
    <td>
      <ul type="unordered">
        <li>Use relevant titles that match with what users are searching for with key information first in the title (for example, Women’s over the knee boots).</li>
        <li>When applicable, we recommend you include gender, size, color, material, and pattern details in title (for example, Women’s small red wool sweater).</li>
        <li>Include characteristics like color to differentiate from other products.</li>
        <li>Do not use all caps (for example, WOMEN’S SHOES).</li>
        <li>Uploading an item for the first time will be pending review until the offer title has been successfully reviewed. Updating the offer title of an existing item will be reverted to the pending review status until it has been successfully reviewed again. The review process can take up to 3 business days. </li>
        <li>The title of the item can be slightly different, but it must be for the same item.</li>
        <li>For mobile devices or tablets, the price can be 0, as the subsidized price with a contract is allowed. For such items, you must include the phrase "only with contract" (or similar) in the title.</li>
        <li>For mobile devices or tablets, the price can be 0 when payment options with multiple installments are allowed (US only). For such items, you must include the phrase "with installment plan" (or similar) in the title.</li>
      </ul>
    </td>
  </tr>
</table>

## Recommended attributes
<table>
  <tr>
    <th scope="col">Field name</th>
    <th scope="col">Description</th>
    <th scope="col">What you need to know</th>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
									description
										 (Required for local products if the data is not available in the online products feed)
									</th>
    <td>
									Item description
										<para>
											<strong>Example:</strong> 
											 Bright yellow 100% cotton dress shirt
										</para><para>
											<strong>Requirements:</strong> 
											 
										Alphanumeric
											<para>10000 character limit.</para><para>No HTML code. Do not enclose in quotes. </para></para></td>
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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
									image_link
										 (Required for local products if the data is not available in the online products feed)
									</th>
    <td>
									URL of an image of the item
										<para>
											<strong>Example:</strong> 
											 http://www.bingshop.com/ images/ISI1.jpg
										</para><para>
											<strong>Requirements:</strong> 
											 
										Alphanumeric
											<para>1000 character limit</para><para>
											Link must be HTTP or HTTPs only. Image must be: bmp, gif, exif, jpg, png, tiff and the recommended minimum size is 220px by 220px. The image size cannot exceed 3.9 MB. No watermarks or free shipping text. Only one image per item.
											</para></para></td>
    <td>
      <ul type="unordered">
        <li>Do not include any text within your images, including promotional messaging.</li>
        <li>Use images with a white background for a “pop” effect.</li>
        <li>
											Update robots.txt file to allow Microsoft Advertising to crawl your site. Your ad cannot be served if the crawling is incomplete. [Learn more](https://go.microsoft.com/fwlink?LinkId=690094).
											</li>
        <li>The image link URL is case-sensitive. Changing the casing on the URL will cause the URL to be re-crawled.</li>
        <li>Uploading an item for the first time will be pending review until the image URL has been successfully crawled. Updating the image URL of an existing item will be reverted to the pending review status until it has been successfully re-crawled. The review process can take up to 3 business days. </li>
      </ul>
    </td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
									condition
									</th>
    <td>
									Condition of item
										<para>
											<strong>Example:</strong> 
											 new
										</para><para>
											<strong>Requirements:</strong> 
											 
											Valid options: new; used; refurbished Default is "new."
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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
									product_category
									</th>
    <td>
									Predefined product category (equivalent to google_product_category)
										<para>
											<strong>Example:</strong> 
											 Software | Computer Software
										</para><para>
											<strong>Requirements:</strong> 
											 
											Alphanumeric, 255 character limit
											 
											Delimiters: greater than symbol [&gt;].
											 
											Only the greater than symbol &gt; is a valid delimiter. Any other value is treated as invalid.
											 
											<strong>Full list of taxonomy values</strong>:
											<ul><li>
												[All languages](https://go.microsoft.com/fwlink?LinkId=2118268)
											  </li><li>
												[Example feed file](https://go.microsoft.com/fwlink?LinkId=506749)
											  </li></ul></para></td>
    <td>
      <ul>
        <li>IDs, instead of string values, are now supported. View the updated taxonomy categories: Taxonomy and Taxonomy with IDs</li>
        <li>For mobile devices or tablets, the price can be 0, as the subsidized price with a contract is allowed. For such items, you must include the phrase "only with contract" (or similar) in the title with the product_category value of "Electronics &gt; Communications &gt; Telephony &gt; Mobile Phones" (267) for mobile devices or "Electronics &gt; Computers &gt; Tablet Computers" (4745) for tablets.</li>
        <li>For mobile devices or tablets, the price can be 0 when payment options with multiple installments are allowed (US only). For such items, you must include the phrase "with installment plan" (or similar) in the title with the product_category value of "Electronics &gt; Communications &gt; Telephony &gt; Mobile Phones" (267) for mobile devices or "Electronics &gt; Computers &gt; Tablet Computers" (4745) for tablets.</li>
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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">webitemid</th>
    <td>Alternative ID to match items between online products feed and local products feed.</td>
    <td>If you are unable to use the same value for itemid and id in your feeds, we recommend matching webitemid value in the local products feed with id value in the online products feed for the same item.</td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
				gtin
						 (Required for local products if the data is not available in the online products feed)
					</th>
    <td>
              Global Trade Item Number. The GTIN field has a limit of 50 characters, with each GTIN value having up to 14 digits. For multiple GTIN values, separate by a comma and space.
						<para>
							<strong>Example:</strong> 
							 00012345600012s
						</para><para>
							<strong>Requirements:</strong> 
							 
                Numeric, 14 digits max per value, multi-value, 50 character limit
						</para></td>
    <td />
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              brand
						 (Required for local products if the data is not available in the online products feed)
					</th>
    <td>
              Item’s manufacturer, brand or publisher
						<para>
							<strong>Example:</strong> 
							 Contoso
						</para><para>
							<strong>Requirements:</strong> 
							 
                Alphanumeric
							<para>70 character limit</para></para></td>
    <td>
      <ul type="unordered">
        <li>Do not add your store name as the brand unless you manufacture the product.</li>
        <li>We recommend to keep the brand character limit to 70, but it can be up to 1000 characters.</li>
        <li>Uploading an item for the first time will be pending review until the brand has been successfully crawled. Updating the brand of an existing item will be reverted to the pending review status until it has been successfully re-crawled. The review process can take up to 3 business days. </li>
      </ul>
    </td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              mpn
						 (Required for local products if the data is not available in the online products feed)
					</th>
    <td>
              Manufacturer Part Number
						<para>
							<strong>Example:</strong> 
							 ADNK-5020
						</para><para>
							<strong>Requirements:</strong> 
							 
                Alphanumeric, 70 character limit
						</para></td>
    <td>
      <ul type="unordered">
        <li>MPN should be specific to one unique product.</li>
        <li>MPNs are assigned by the manufacturer.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">identifier_exists (required for new products only when gtin and brand, or mpn and brand isn't available)</th>
    <td>
              Used to indicate that unique product identifiers (gtin, brand, and mpn) aren't available for a product.
						<para>
							<strong>Example</strong> : 
                FALSE 
							 
							<strong>Requirements</strong> : 
                Boolean: TRUE or FALSE
						</para></td>
    <td>Products that may not have an identifier_exists attribute include custom goods, like homemade products, or products that were made before gtins were created, like antiques.</td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              sale_price
	</th>
    <td>
              Items’s sale price, excluding tax and shipping
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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              sale_price_effective_date
	</th>
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
        <li>The store-level values in the inventory feed will override the national level values from the local products feed.</li>
        <li>The end date needs to be in the same format.</li>
        <li>For items on sale, submit both the sale price and sale effective date attributes. If you update the sale price attribute but not the sale price effective date, the sale price will continue to be used for your item. </li>
      </ul>
    </td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">pick up method</th>
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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">pick up sla</th>
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

## Apparel item attributes
For apparel items, be sure to include the additional attributes if they are not provided in the online products feed.

<table>
  <tr>
    <th scope="col">Field name</th>
    <th scope="col">Description</th>
    <th scope="col">What you need to know</th>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
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
    <td>We recommend including gender in the title for products where it's a distinguishing attribute.</td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              age_group
				</th>
    <td>
              Age group targeted by the item
					<para>
						<strong>Example:</strong> 
						 newborn
					</para><para>
						<strong>Requirements:</strong> 
						 
                Valid Options: newborn, infant, toddler, kid, adult
					</para></td>
    <td />
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
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
						<para>Supports up to 3 values separated by a slash [/] with most dominant color first.</para><para>Color attributes, like "stainless steel" or "mahogany" are also accepted.</para></para></td>
    <td>We recommend adding the dominant color in the title.</td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              size
				</th>
    <td>
              Size of the item
					<para>
						<strong>Example:</strong> 
						 small, medium, large
					</para><para>
						<strong>Requirements:</strong> 
						 
                Alphanumeric, Max 100 characters
					</para></td>
    <td>
      <ul type="unordered">
        <li>Indicate size values based on your target country.</li>
        <li>Use consistent size values for the same items. (e.g., “small”, “medium”, and “large” and not “small,” “M,” and “Lg”).</li>
      </ul>
    </td>
  </tr>
</table>

## How do I submit local product feeds

Once you created your local products feed, you must submit your product information through Microsoft Merchant Center.

## 4. Upload inventory information
After creating a local products feed, you need to create a local products inventory feed for your Local Inventory Ads. The local products inventory feed is needed for the list of products that you sell in each store specifically.

## What is the difference between local product inventory and local product inventory update feeds?

Because your inventory price and quantity change frequently by store, you can use local product inventory update feeds for up-to-date information of your local inventory ads.

When submitting via FTP:

- **Local product inventory feeds**  include all of your inventory for all of your stores. You can submit the feed on a daily basis.
- **Local product inventory update feeds**  are used only for frequently changing details like the price and quantity of your items in specific stores.

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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              store code
							</th>
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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              itemid
							</th>
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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              quantity
							</th>
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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              sale_price
			</th>
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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
              sale_price_effective_date
	</th>
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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">
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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">weeks of supply</th>
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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">pick up method</th>
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
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">pick up sla</th>
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

## 5. Enable shopping campaigns into Local Inventory Ads
After you sign in to your Microsoft Advertising account:

1. Go to the **Campaigns** page.
1. Select the shopping campaign you want to use for Local Inventory Ads.
1. Click on the **Settings** tab.
1. Under **Shopping settings**, check the **Enable local inventory ads** box.
1. Click **Save**.

## Channel and channel exclusivity

Now that local inventory ads are enabled for your shopping campaign, you can set filters by channel and channel exclusivity.

- **Channel** : 				 				**Local store**: Automatically filter to products that are sold in local stores, including products that may also be sold online.				 				**Online**: Filter products that are only sold on your website.
- **Channel exclusivity** : 				 				**Multi-channel**: Filter products that are sold both online and in store.				 				**Single channel**: Filter products that are sold only in store or online.

You can show products sold only in local stores but not online by setting the filters to “Channel”: “Local stores” and “Channel exclusivity”: “Single-channel”.


