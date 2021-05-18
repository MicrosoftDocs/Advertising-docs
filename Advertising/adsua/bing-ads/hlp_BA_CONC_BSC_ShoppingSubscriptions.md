---
title: Advertise software subscriptions with Microsoft Shopping Campaigns
description: Sell software subscriptions where customers can buy a prepaid license to use for 1 year or longer.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Advertise software subscriptions with Microsoft Shopping Campaigns

Use Microsoft Shopping Campaigns to sell your software subscriptions where customers can buy a prepaid license to use for 1 year or longer.

For the subscriptions to be supported by Microsoft Shopping Campaigns, they must:

- Be sold in prepaid, yearly (12 month) increments of at least 1 year.
- Contain all required attributes listed below.
- Meet all landing page requirements listed below.

Here’s a closer look at the requirements for your product feed and landing pages for software subscriptions.

## Required fields to include in feed
<table>
  <tr>
    <th scope="col">Field name</th>
    <th scope="col">Description</th>
    <th scope="col">What you need to know</th>
  </tr>
  <tr>
    <th scope="row" style="font-weight:normal;border-bottom:solid 1px #ccc">
              title
            </th>
    <td>
              Title of the subscription
              <para>
                <strong>Example:</strong> 
                 Contoso 1-year subscription
              </para><para>
                <strong>Requirements:</strong> 
                 Include the word "subscription"
				 Alphanumeric
                 150 character limit
                 Don't enclose in quotes
              </para></td>
    <td>
              You must include the word "subscription" and the duration in the title.
            </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight:normal;border-bottom:solid 1px #ccc">
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
        <li>The price must be for the full software subscription, with a minimum of 1 year.</li>
        <li>
                  If you offer any subsidized periods for prepaid 12-month subscriptions, you must include it in the total price.
                </li>
        <li>If the subscription price is different after the first year, enter the prepaid price for the first year.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight:normal;border-bottom:solid 1px #ccc">
              product_category
            </th>
    <td>
              Predefined product category (equivalent to google_product_category)
              <para>
                <strong>Example:</strong> 
                 Software | Computer Software
              </para><para>
                <strong>Requirements:</strong> 
                 
                Alphanumeric 
                 255 character limit
                 Delimiters: greater than symbol [&gt;].
                 
                Only the greater than symbol &gt; is a valid delimiter. Any other value is treated as invalid.
                 
                <strong>Full list of taxonomy values</strong> :
                <ul><li>
                    [English](https://go.microsoft.com/fwlink?LinkId=507666)
                  </li><li>
                    [French](https://go.microsoft.com/fwlink?LinkId=836857)
                  </li><li>
                    [German](https://go.microsoft.com/fwlink?LinkId=837552)
                  </li><li>
                    [Example feed file](https://go.microsoft.com/fwlink?LinkId=506749)
                  </li></ul></para></td>
    <td>
             Use the following category: Software | Computer Software | [Category]. For example, Software | Computer Software &gt; Business &amp; Productivity Software
            </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight:normal;border-bottom:solid 1px #ccc">
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
    <th scope="row" style="font-weight:normal;border-bottom:solid 1px #ccc">
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
    <th scope="row" style="font-weight:normal;border-bottom:solid 1px #ccc">
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
                 70 character limit
              </para></td>
    <td>
      <ul type="unordered">
        <li>Do not add your store name as the brand unless you manufacture the product.</li>
        <li>We recommend to keep the brand character limit to 70, but it can be up to 1000 characters.</li>
        <li>Uploading an item for the first time will be pending review until the brand has been successfully crawled. Updating the brand of an existing item will be reverted to the pending review status until it has been successfully re-crawled. The review process can take up to 3 business days. </li>
        <li>
                  Learn more about [unique identifiers for your product ads](./hlp_BA_CONC_BMC_UniqueIdentifiers.md).
                </li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight:normal;border-bottom:solid 1px #ccc">shipping</th>
    <td>
              Cost of shipping, submitted in local currency. This is a required field for Germany only.<para><para>Shipping has multiple subfields and can have the following headers:</para><ul><li>shipping(price)</li><li>shipping(country:price)</li><li>shipping(country:service:price)</li><li>shipping</li></ul>
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
             The shipping field is required for Germany only. For software subscriptions sold in Germany, enter the shipping cost as 0.00 EUR.
            </td>
  </tr>
  <tr>
    <th scope="row" style="font-weight:normal;border-bottom:solid 1px #ccc">
              image_link
            </th>
    <td>
              URL of an image of the item
              <para>
                <strong>Example:</strong> 
                 http://www.bingshop.com/ images/ISI1.jpg
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
        <li>We recommend that you submit an image of the software box, if possible. Logos and icons are also accepted.</li>
        <li>Do not include any text within your images, including promotional messaging.</li>
        <li>Use images with a white background for a “pop” effect.</li>
        <li>Update robots.txt file to allow Microsoft Advertising to crawl your site. Your ad cannot be served if the crawling is incomplete. [Learn more](https://go.microsoft.com/fwlink?LinkId=690094).</li>
        <li>The image link URL is case-sensitive. Changing the casing on the URL will cause the URL to be re-crawled.</li>
        <li>Uploading an item for the first time will be pending review until the image URL has been successfully crawled. Updating the image URL of an existing item will be reverted to the pending review status until it has been successfully re-crawled. The review process can take up to 3 business days. </li>
      </ul>
    </td>
  </tr>
</table>

## Landing page requirements
For software subscriptions, you need to send your customers to specific landing pages that outlines the details of the subscriptions. Take a look at the requirements for the software subscription landing pages:

- **Create different landing pages for each product variant** . For example, if your software subscription has different versions, each version needs a separate landing page.
- **Show the total price of the full software subscription**  and make sure that it is preselected. The total price must be preselected and be for the full subscription, with a minimum of 1 year. Any subsidized periods for the prepaid 12-month subscriptions must be included in the total price.
- **Disclose renewal and cancellation terms** . Be sure to include all renewal information (is the subscription automatically renewed or a fixed term?) and any cancellation details (what happens if a customer wants to cancel a prepaid subscription before the 1-year period is up?).

For more information, see our article on  [setting up landing pages](./hlp_BA_PROC_ChangeLandingPage.md).


