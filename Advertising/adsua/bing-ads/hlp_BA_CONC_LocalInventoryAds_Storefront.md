---
title: About storefront hosting for Local Inventory Ads
description: Learn about Local Inventory Ads for your Microsoft Shopping Campaigns.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# About storefront hosting for Local Inventory Ads

> [!IMPORTANT]
> Local Inventory Ads are currently available in Australia, Austria, Belgium, France, Germany, Italy, the Netherlands, Spain, Sweden, Switzerland, the United Kingdom and United States.

Bing supports both Bing-hosted and merchant-hosted storefront for Local Inventory Ads. With a Bing-hosted storefront, you can direct customers to a Bing-hosted page, where your products and local retail store information is displayed. On the other hand, a merchant-hosted storefront lets you direct customers to your own website, where you can manage your customers shopping experiences.

## Availability

We are working with retailers who have physical stores in the United Kingdom and United States.

## How a merchant-hosted storefront works

Once a customer clicks on a Local Inventory Ad, the store code is passed to the merchant by Bing. Then, the merchant generates the local store landing page for the clicked product.

## Merchant-hosted local storefront implementation

<table>
  <tr>
    <th scope="col">Feature type</th>
    <th scope="col">What it is</th>
    <th scope="col">How it's displayed</th>
    <th scope="col">Landing page behavior</th>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">Full</th>
    <td>Clicks on a local inventory ad takes a customer to the product landing page that shows an item's availability at a specific store.</td>
    <td>Customers are shown a distance annotation (for example, 2 mi) that shows the distance to the store that sells the item.</td>
    <td>Clicking on a "see what's in store" local inventory ad directs customers to the product landing page with details on the item's availability at a specific store.</td>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">Basic</th>
    <td>Clicks on a local inventory ad takes a customer to a product landing page that shows an item's availability at a nearby store.</td>
    <td>Customers are shown the in-store annotation that shows that the item is available for purchase at a nearby store.</td>
    <td>Clicking on a "see what's in store" local inventory ad directs customers to a Bing-hosted local storefront.</td>
  </tr>
</table>

## Feed requirements for merchant-hosted local storefront

A local products feed contains all the products that you sell in your stores with attributes describing the products. Learn how to create and submit local product feeds [here](./hlp_BA_PROC_LocalInventoryAds_CreateLocalProductFeed.md).

In addition to the required attributes for all local product feeds, for merchant-hosted local storefronts, you need to:

- Add the following attributes: ads_redirect and link_template
- Include the store_code URL parameter for both attributes above

Here's an example of how your feed file might look:

<table>
  <tr>
    <th scope="col">itemid</th>
    <th scope="col">title</th>
    <th scope="col">price</th>
    <th scope="col">ads_redirect</th>
    <th scope="col">link_template</th>
  </tr>
  <tr>
    <th style="font-weight:normal;background-color:transparent;border-bottom:solid 1px #ccc" scope="row">1234</th>
    <td>Adatum 50" 4K HDTV</td>
    <td>$599.99</td>
    <td>http://tailspintoys.com/1234?store={store_code}&amp;trackingParameter=value
</td>
    <td>http://tailspintoys.com/1234?store={store_code}</td>
  </tr>
</table>


