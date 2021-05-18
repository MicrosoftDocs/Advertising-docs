---
title: About Shopping Campaigns for Brands
description: Use Shopping Campaigns for Brands to drive sales with retail partners.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# About Shopping Campaigns for Brands

> [!NOTE]
> This feature is available in open beta for the United Kingdom and United States only.
> This feature is only available from the redesigned Microsoft Advertising.

By partnering with retailers that sell your products, Shopping Campaigns for Brands helps you reach and influence potential customers across the Microsoft Search Network and Microsoft Audience Network. Shopping Campaigns for Brands allows you to:

- Boost your product sales across all retailers with a single campaign.
- Increase your product visibility on digital shelves.
- Get insights into your brand, audience, and product performance across the Microsoft Search and Audience network.

## Benefits of using Shopping Campaigns for Brands

- **Get started right away** : As a brand, you just need to provide your brands' names. Retailers who sell your products are automatically identified and invited to partner with you.
- **Drive sales across retailers seamlessly** : A single campaign can target all your retailer partners - there's no need to create individual campaigns for each retailer.
- **Product-level insights for each retailer** : You can view and analyze product-level reporting on conversions and revenues, broken down by each retailer. Note: This requires a given retailer to share product-level conversion data.

## Onboarding for brands

To get started as a brand, check out the following steps:

## Step 1: Enter your brands
1. From the top of the page, click **Tools**, then **Shopping for Brands** under **Shared Library**.
1. Click **Brands**, then click **Add brand**.
1. Enter all your brands and its websites. A website URL would look like: **http://contoso.com** with no slashes ( / ). You can also add the sub-brands (optional) to help us identify all of your products.
1. Click **Save**.

## Step 2: View matched retailers and products
After you entered your brands, retailers who sell your products can be automatically identified and linked (which is what we recommend) or you can manage retailer link requests individually. The **Overview** page provides information about your linked retailers and matched products.

1. From the global menu, click **Tools** and then **Shopping for Brands** under **Shared Library**.
1. Click **Retail partners**.
1. Click **Add retail partner** or switch the **Link to all retail partners ** toggle on (recommended) to allow Microsoft to automatically match you with retailers who sell your products.
1. If you are manually linking a retailer's store, enter the **Retailer store ID**. This is the Microsoft Merchant Center store identifier that you'll need to obtain from your partner.
1. Click **Send request**.

**How are my brands matched to retailers?**

Brands are matched to retailers via the Microsoft Brand Product Graph that:
- Identifies your products available at different retailers based on attributes like GTIN and MPN
- Catalogs brands and their aliases, then establishes product-brand relationships

## Step 3: Create a campaign
With Shopping Campaigns for Brands, you only need to [create a single campaign](./hlp_BA_CONC_BSC_GetStarted.md)  that reaches across all shopping surfaces (search, e-commerce, and physical stores).

Go to the **Campaigns** page, then click **Create campaign** > **Boost product sales** to get started. Follow the steps of the wizard and when it’s time to select a **Store**, select **All retail partners**.

## Onboarding for retailers

Retailers must approve linking requests from brands to their Microsoft Merchant Center store. Once a brand-to-store link is established, brands and retailers are then able to cooperatively bid on shared products.

## Step 1: Create a product feed
Put simply, a product feed is a list of items you're promoting with a third party. A product feed contains a list of product attributes, such as product title, description, and price.

Use the product feed import template to create a list, which you'll need to upload to Microsoft Advertising following these steps:

1. From the global menu, click **Tools** and then **Merchant Center**.
1. Select the store you want to add the feed to, then click **Create feed**.
1. Enter the feed details and select the **Input Method**  to submit your feed file.
1. Click **Create feed** to create the product feed.

## Here are the required and optional fields you can include in the product feed file.
<table>
  <tr>
    <th scope="col">Field name</th>
    <th scope="col">Description</th>
    <th scope="col">What you need to know</th>
  </tr>
  <tr>
    <td>id
                 
                  (required)
              </td>
    <td>
                  A unique identifier for the item.
                  <para>
                    <strong>Example:</strong> 
                     ISI1
                  </para><para>
                    <strong>Requirements:</strong> 
                     
                    50 Unicode character limit.
                     
                    <strong>Recommended:</strong>  ASCII only: alphanumeric, underscores (_), and dashes (-)
                  </para></td>
    <td>
      <ul type="unordered">
        <li>ID must be unique for each item in your catalog.</li>
        <li>If you have multiple feeds, IDs of items across different feeds still need to be unique.</li>
        <li>
                      Special ASCII characters (for example, asterisk (*), comma (,), backslash (\), ampersand (&amp;), etc. are allowed.
                    </li>
        <li>The ID is the same as the merchant product ID (MPID).</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
                  brand
                   
                  (required)
                </td>
    <td>
                  Item’s manufacturer, brand, or publisher
                  <para>
                    <strong>Example:</strong> 
                     Contoso
                  </para><para>
                    <strong>Requirements:</strong> 
                     
                    Alphanumeric
                    <para>70 character limit</para></para></td>
    <td>
      <ul type="unordered">
        <li>Do not add your retailer name as the brand unless you manufacture the product.</li>
        <li>We recommend to keep the brand character limit to 70, but it can be up to 1000 characters.</li>
        <li>Uploading an item for the first time will be pending review until the brand has been successfully crawled. Updating the brand of an existing item will be reverted to the pending review status until it has been successfully re-crawled. The review process can take up to 3 business days. </li>
        <li>
                      Learn more about [unique identifiers for your product ads](./hlp_BA_CONC_BMC_UniqueIdentifiers.md).
                    </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
                        mpn
                         
                        (required)
                      </td>
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
        <li>
                            Learn more about [unique identifiers for your product ads](./hlp_BA_CONC_BMC_UniqueIdentifiers.md).
                          </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
                        gtin
                         
                       (required)
                      </td>
    <td>
                        Global Trade Item Number. The GTIN field has a limit of 50 characters, with each GTIN value having up to 14 digits. For multiple GTIN values, separate by a comma and space.
                        <para>
                          <strong>Example:</strong> 
                           00012345600012
                        </para><para>
                          <strong>Requirements:</strong> 
                           
                          Numeric, 14 digits max per value, multi-value, 50 character limit
                        </para></td>
    <td>
                        Learn more about [unique identifiers for your product ads](./hlp_BA_CONC_BMC_UniqueIdentifiers.md).
                      </td>
  </tr>
  <tr>
    <td>
                  title
                </td>
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
  <tr>
    <td>
                  description
                </td>
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
    <td>
                  link
                </td>
    <td>
                  Direct URL of the item's page on your website
                  <para>
                    <strong>Example:</strong> 
                      http://www.contoso.com/ 
                    product.asp?pn=ISI1
                  </para><para>
                    <strong>Requirements:</strong> 
                     
                    <para>0-2000 characters</para><para>HTTP or HTTPs only and no redirects. For redirect URLs, use the ads_redirect field.</para></para></td>
    <td>
      <ul type="unordered">
        <li>Link should point to the specific product instead of your store’s home page or pages with multiple products.</li>
        <li>The Product URL domain must match the Store URL domain.</li>
        <li>
                      Must be a path under your store's destination URL. For aggregators, this must be a direct link to the seller's product page. Aggregators are third party sites that consolidate items to Bing on behalf of individual merchants. In the catalog that an aggregator submits, the link attribute must be a direct link to the seller's product page and the seller-name attribute is required. Adding items submitted on behalf of the merchant must comply with our policies and [Terms of Service](./hlp_BA_CONC_EditorialGuidelines.md).
                    </li>
        <li>Uploading an item for the first time will be pending review until the product URL has been successfully reviewed. Updating the product URL of an existing item will be reverted to the pending review status until it has been successfully reviewed again. The review process can take up to 3 business days.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
                  image_link
                </td>
    <td>
                  URL of an image of the item
                  <para>
                    <strong>Example:</strong> 
                     http://www.contoso.com/ images/ISI1.jpg
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
</table>

## Step 2: Approve retail partner request
We recommend that you enable automatic approval for store linking requests. This ensures that any new brands who sell your products onboard, they're automatically linked to your Microsoft Merchant Center account. Without automatic linking, you'll need to check for and approve requests manually.

**To automatically approved retail partner requests:**

1. From the global menu, click **Tools** and then **Microsoft Merchant Center**.
1. Select the Microsoft Merchant Center store.
1. Click **Settings**, and then **Linked manager accounts**.
1. Switch the **Auto-approve link requests** toggle on.

**To approve a retail partner request:**

1. On the top menu, click **Tools** and then click ** Microsoft Merchant Center**  (or from the global menu at the top of the page, click **Tools** and then **Microsoft Merchant Center**).
1. Select the Microsoft Merchant Center store you want to edit.
1. Click **Settings**, and then click **Retail partners**.
1. You'll see a grid that contains the **Customer ID**, **Customer name**, and **Product** your partner associated to your store, plus **Actions** you can take on the request. From the **Actions** column, you can **Accept** or **Decline** a linking request.

**To remove a partner's access from your store:**

1. On the top menu, click **Tools** and then click ** Microsoft Merchant Center**  (or from the global menu at the top of the page, click **Tools** and then **Microsoft Merchant Center**).
1. Select the Microsoft Merchant Center store you want to edit.
1. Select **Settings**, and then select **Retail partners**.
1. Find your partner in the grid, and then click **Unlink**.

## Keep an eye on your campaign

You can view your campaigns' performances on the **All Campaigns** page. All existing Microsoft Shopping Campaigns reports support Shopping Campaigns for Brands.

If you are a retailer, you can see the impact of Shopping Campaigns for Brands in the Product dimensions and Production partition reports. Both reports contain Assisted impressions, Assisted clicks, and if you have conversion tracking enabled, Assisted Conversions. These metrics  respectively track impressions, clicks, and conversions on Shopping Campaigns for Brands.

<table>
  <tr>
    <th colspan="2" scope="row">Product partition</th>
  </tr>
  <tr>
    <td>
      <strong>What it shows:</strong> The impressions, clicks, spend, average cost-per-click, and average conversion for each product group in your Microsoft Shopping Campaigns.
    </td>
    <td>
      <strong>Why run it:</strong> To see the performance data for the product groups in your shopping campaigns and to optimize your campaigns accordingly.
    </td>
  </tr>
  <tr>
    <th colspan="2" scope="row">Product partition unit</th>
  </tr>
  <tr>
    <td>
      <strong>What it shows:</strong> The impressions, clicks, spend, average cost-per-click, and average conversions for each product group in your Microsoft Shopping Campaigns. Depending on the report time and columns you choose, the report may include more than one row per product group.
    </td>
    <td>
      <strong>Why run it:</strong> To see product partition unit data of your Product Groups in Shopping Campaigns.
    </td>
  </tr>
  <tr>
    <th colspan="2" scope="row">Product dimension</th>
  </tr>
  <tr>
    <td>
      <strong>What it shows:</strong> The impressions, clicks, spend, average cost-per-click, and conversion for each product in your catalog [each line item in Microsoft Merchant Center catalog].
    </td>
    <td>
      <strong>Why run it:</strong> To figure out which of your products are triggering ads and getting the most clicks and optimize the ones not performing so well.
    </td>
  </tr>
  <tr>
    <th colspan="2" scope="row">Product search term</th>
  </tr>
  <tr>
    <td>
        <strong>What it shows: </strong>The impressions, clicks, click-through rate, and average position for search terms that have triggered your ads.
      </td>
    <td>
        <strong>Why run it: </strong>To see what your audience is searching for when your ads are shown. You can use this information to make informed additions, removals, or edits to both your keyword and negative keyword lists.
      </td>
  </tr>
  <tr>
    <th colspan="2" scope="row">Product match count</th>
  </tr>
  <tr>
    <td>
        <strong>What it shows: </strong>The number of products that are matched and targeted at the campaign, ad group, and product group level.
      </td>
    <td>
        <strong>Why run it: </strong>To see if you covered your bidding across the Microsoft Shopping Campaigns inventory.
      </td>
  </tr>
</table>


