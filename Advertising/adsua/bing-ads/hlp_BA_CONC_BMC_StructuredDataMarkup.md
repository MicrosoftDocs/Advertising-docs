---
title: Using structured data markup
description: Learn how using microdata, a form of structured data markup, can help you display better content in search results.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Using structured data markup

Structured data markup is a type of HTML encoding that makes it easier for search engines to read and retrieve data from your website. When search engines can quickly find and display more-relevant information about your business, prospective customers find you more easily in search results.

Without structured data markup, search engines may only display minimal information, such as the site's URL and simple one-line description. With proper structured data markup, search engines can better read contents on a webpage, such as displaying a store's products, prices, and availability.

## Getting started with structured data markup

Your webmaster needs to edit—or markup—your site's HTML using open-source microdata from [Schema.org](https://go.microsoft.com/fwlink?LinkId=862743). Microdata is a set of standardized descriptive tags attached to a site's HTML code that allows search engines to effectively read site contents.

Schema.org's microdata is used by Bing and other leading search engines to provide better results and richer browsing experiences.

> [!IMPORTANT]
> Although it's possible to markup HTML using RDF and JSON, Bing only supports Offer and Product microdata. See Schema.org's [Offer object](https://go.microsoft.com/fwlink?LinkId=862745) and [Product object](https://go.microsoft.com/fwlink?LinkId=862747) for more information.

To surface your offers on relevant searches, you need to have at least one offer on your landing page. If you have multiple offers on the landing page, you'll need to annotate each offer on the page with a SKU or a GTIN that correspond to identical SKU/GTIN tags in Microsoft Merchant Center.

## HTML code example with microdata for one offer
&lt;div itemscope="" itemtype="http://Contoso.com/Product"&gt;           &nbsp;&lt;meta itemprop="name" content="Product Name" /&gt;           &nbsp;&lt;meta itemprop="sku" content="SINGLE_SKU" /&gt;           &nbsp;&lt;meta itemprop="description" content="Product's description." /&gt;           &nbsp;&lt;meta itemprop="gtin14" content="54789012345689"/&gt;           &nbsp;&lt;meta itemprop="image" content="https://www.Contoso.com/product01.jpg" /&gt;           &nbsp;&lt;meta itemprop="brand" content="Product Brand" /&gt;           &nbsp;&lt;div itemprop="offers" itemscope="" itemtype="http://Contoso.com/Offer"&gt;           &nbsp;&nbsp;&lt;meta itemprop="priceCurrency" content="USD" /&gt;           &nbsp;&nbsp;&lt;meta itemprop="price" content="28.99" /&gt;           &nbsp;&nbsp;&lt;meta itemprop="availability" content="http://Contoso.com/InStock" /&gt;           &nbsp;&lt;/div&gt;           &lt;/div &gt; 

## HTML example with microdata for multiple offers
&lt;div itemscope="" itemtype="http://Contoso.com/Product"&gt;           &nbsp;&lt;meta itemprop="name" content="Product Sku 01 Name" /&gt;           &nbsp;&lt;meta itemprop="sku" content="SKU_01" /&gt;           &nbsp;&lt;meta itemprop="description" content="Product's description." /&gt;           &nbsp;&lt;meta itemprop="gtin14" content="54789012345689"/&gt;           &nbsp;&lt;meta itemprop="image" content="https://www.Contoso.com/product01.jpg" /&gt;           &nbsp;&lt;meta itemprop="brand" content="Product Brand" /&gt;           &nbsp;&lt;div itemprop="offers" itemscope="" itemtype="http://Contoso.com/Offer"&gt;           &nbsp;&nbsp;&lt;meta itemprop="priceCurrency" content="USD" /&gt;           &nbsp;&nbsp;&lt;meta itemprop="price" content="28.99" /&gt;           &nbsp;&nbsp;&lt;meta itemprop="availability" content="http://Contoso.com/InStock" /&gt;           &nbsp;&lt;/div&gt;           &lt;/div &gt;                     &lt;div itemscope="" itemtype="http://Contoso.com/Product"&gt;           &nbsp;&lt;meta itemprop="name" content="Product Sku 02 Name" /&gt;           &nbsp;&lt;meta itemprop="sku" content="SKU_02" /&gt;           &nbsp;&lt;meta itemprop="description" content="Product's description." /&gt;           &nbsp;&lt;meta itemprop="gtin14" content="54789012345690"/&gt;           &nbsp;&lt;meta itemprop="image" content="https://www.Contoso.com/product02.jpg" /&gt;           &nbsp;&lt;meta itemprop="brand" content="Product Brand" /&gt;           &nbsp;&lt;div itemprop="offers" itemscope="" itemtype="http://Contoso.com/Offer"&gt;           &nbsp;&nbsp;&lt;meta itemprop="priceCurrency" content="USD" /&gt;           &nbsp;&nbsp;&lt;meta itemprop="price" content="32.99" /&gt;           &nbsp;&nbsp;&lt;meta itemprop="availability" content="http://Contoso.com/InStock" /&gt;           &nbsp;&lt;/div&gt;           &lt;/div &gt; 

For more information about setting up microdata, see [Schema.org's getting started guide](https://go.microsoft.com/fwlink?LinkId=862744).

## Microdata requirements

- The microdata must be embedded in the HTML returned from your web server. It can't be generated after JavaScript executes a page load.
- Your landing page microdata must be static. For example, prices can’t fluctuate based on user data (such browser, cookies, or IP address).
- The microdata must match the values that are shown to the user. Purposefully incorrect data in your landing page violates the [Microsoft Advertising Terms and Conditions](https://go.microsoft.com/fwlink?LinkId=401036).


