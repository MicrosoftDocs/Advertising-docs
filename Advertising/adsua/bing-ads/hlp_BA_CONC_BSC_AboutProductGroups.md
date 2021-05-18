---
title: Understand and use product groups
description: Product groups are used to specify which products from your Microsoft Merchant Center catalog should be included in a particular ad group.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Understand and use product groups

## What are product groups?

Once you create a shopping campaign, Microsoft Advertising creates a default ad group. Within this ad group is a single product group that contains all the products from your Microsoft Merchant Center feed. This product group is what you use to bid on instead of keywords and all the products within this product group uses the same bid.

> [!NOTE]
> In order to understand product groups, first make sure you are familiar with both [product ads](./hlp_BA_CONC_AboutProductAds.md) and [shopping campaigns](./hlp_BA_CONC_BSC_Overview.md).

We recommend that you break down the single product group into smaller product groups, so that each product group contains closely related products. This will help you manage which ads to show, and when to show them. With product groups, you can narrow down the default group into a customized list of specific products and divide up to 5 levels for each product group.

## Product group attributes
<table>
  <tr>
    <th scope="col">Attribute</th>
    <th scope="col">Description</th>
    <th scope="col">What you need to know</th>
  </tr>
  <tr>
    <th scope="row" style="border-bottom:solid 1px #ccc">Category</th>
    <td>Predefined product category
							 
							<strong>Example</strong> : Software &gt; Computer Software
						</td>
    <td>
      <ul>
        <li>You can have up to 5 categories per offer.</li>
        <li>Full list of taxonomy values:
									<ul><li>[All languages](https://go.microsoft.com/fwlink?LinkId=2118268)</li><li>[Example feed file](https://go.microsoft.com/fwlink?LinkId=506749)</li></ul></li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="border-bottom:solid 1px #ccc">Brand</th>
    <td>Item’s manufacturer, brand, or publisher
							 
							<strong>Example</strong> : Contoso
> 							 
							<strong>Requirements</strong> :
							 Alphanumeric
							 70-character limit
							 10-word limit
						</td>
    <td>
      <ul>
        <li>Do not add your store name as the brand unless you manufacture the product. </li>
        <li>Uploading an item for the first time will be pending review until the brand has been successfully crawled. Updating the brand of an existing item will be reverted to the pending review status until it has been successfully re-crawled. The review process can take up to 3 business days.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="border-bottom:solid 1px #ccc">Condition</th>
    <td>Condition of item
							 
							<strong>Example</strong> : new
> 							 
							<strong>Requirements</strong> : Valid options: new; used; refurbished
						</td>
    <td>
      <ul>
        <li>If no values are provided, the condition will be set to "new" by default.</li>
        <li>'New' products are brand new and have never been used, with the original packaging never opened.</li>
        <li>'Refurbished' products have been professionally restored, are free of defects, and come with a warranty. They may or may not have the original packaging.</li>
        <li>'Used' products are anything other than 'new' or 'refurbished,' where the products have been used previously, with the original packaging opened or missing.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="border-bottom:solid 1px #ccc">Item ID</th>
    <td>A unique identifier for the item.
						 
						<strong>Example</strong> : ISI1
> 						 
						<strong>Requirements</strong> : 50 Unicode character limit
> 						 
						<strong>Recommended</strong> : ASCII only: alphanumeric, underscores (_) and dashes (-)
						</td>
    <td>
      <ul>
        <li>ID must be unique for each item in your catalog per market.</li>
        <li>If you have multiple feeds, the IDs of items across different feeds still need to be unique.</li>
        <li>Special ASCII characters (e.g., asterisk (*), comma (,), backslash (\), ampersand (&amp;), etc. are allowed.</li>
        <li>The ID is the same as the merchant product ID (MPID).</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row" style="border-bottom:solid 1px #ccc">Product type</th>
    <td>Your category of the item
							 
							<strong>Example</strong> : Home &gt; Electronics &gt; DVD Player
> 							 
							<strong>Requirements</strong> : 
							 Alphanumeric
							 750-character limit
							 Delimiters: greater than [&gt;]
						</td>
    <td>You can have more than one product type if your item applies to more than one category.</td>
  </tr>
  <tr>
    <th scope="row" style="border-bottom:solid 1px #ccc">Custom label</th>
    <td>Use to identify products for ad campaign filters
							 
							<strong>Example</strong> : Best sellers, High ROAS, Winter
> 							 
							<strong>Requirements</strong> : 
							 Alphanumeric
							 Max 200 characters
							 Single-value
							 Up to 1000 unique values for each customer label attributes (up to 5000 labels total)
						</td>
    <td>
      <ul>
        <li>You can use up to 5 labels per offer.</li>
        <li>Use custom labels to add a value to the label, such as seasonal or sale items.</li>
      </ul>
    </td>
  </tr>
</table>

## How do I subdivide product groups?
1. From the **Campaigns** page, click the **Product Groups** tab (or from the main menu on the left, click **All campaigns** and then **Product groups**).
1. Click the ad group that contains the product group you want to edit.
1. Click + next to the product group.
1. Select a category to narrow down for your new product group. You can continue to add up to 5 levels per product group.

## How can I view different product groups?
1. From the **Campaigns** page, click the **Product Groups** tab (or from the main menu on the left, click **All campaigns** and then **Product groups**).
1. Click the ad group that contains the product group and subdivided product groups you want to view.
1. By default, the product groups are displayed in the table in the Hierarchy view. You can see how your product groups are organized by clicking on the arrow next to the product group and drilling down to the subdivided product groups. 					  					To view product groups in the List view, click the list icon ![list icon](../images/BA_CONC_PGG_ListIcon.png) above the table. This view lets you see your product groups across an entire account, campaign, or ad group from the table.					  					You can hover over the product group to quickly see all the products that are included in the product group.

## How do I filter product groups?
1. From the **Campaigns** page, click the **Product Groups** tab (or from the main menu on the left, click **All campaigns** and then **Product groups**).
1. Click the ad group that contains the product groups you want to filter.
1. Click **Filters** and then **Create filter**.
1. Select the filter options.
1. Select the **Save filter** checkbox, and then in the box, enter the name.
1. Click **Apply**.
1. To apply a saved filter, on the **Campaigns** page, select any tab, click **Filters**, and then under **Apply saved filters**, select the filter set you want to apply.

## How do I make bulk changes to my product group's bids?
You can make bulk changes to your product groups at the ad group, campaign, or account level.

1. From the **Campaigns** page, click the **Product Groups** tab (or from the main menu on the left, click **All campaigns** and then **Product groups**).
1. Select the checkbox next to the product groups you want to update.
1. Click **Edit** and then **Change bids**.
1. Increase or decrease the bid by percentage, with a maximum or minimum bid option.
1. (Optional) Click **Preview** to see what will change.
1. Click **Save**.

## About product group performance data
- Structural changes to product groups, like updating or deleting product groups, appear immediately in the table.
- Structural changes often necessitate the redistribution of existing performance data across the new structure. Once the data has been reprocessed and is up to date, you will no longer see the alert above the table.

## What you need to know
- There is a 1 to 1 relationship between ad groups and product groups. In other words, each ad group has one product group and vice versa.
- You can view your product groups on the **Product Group** tab within each ad group.
- When viewing your product group, if there is a small triangle to the left of an item in the **Product Group** column, that row has been divided further by some other attribute. Click the triangle to expand that row and see the more granular segments.
- Remember to "exclude" items that you don't want to be in your product group.
- You can narrow down a product group in your catalog feed up to 5 levels. For example, Office supplies > Office instruments > Writing and drawing instruments > Pens and pencils > Pens > New


