---
title: About Product Listings
description: Product Listings show in the Bing shopping tab for free!
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# About Product Listings

> [!NOTE]
> Product Listings are available in the Bing shopping tab in the United States only. If you don't see this feature yet, don't worry - it's coming soon!

With Product Listings, your products can show in the Bing shopping tab for free! The Bing shopping tab has a dedicated unpaid section, where any clicks from the unpaid section are free. Free listings give you wider exposure for your products by displaying them in more places. With more impressions to a wider audience, you can increase your click-through and conversion rates.

## Requirements for eligibility

- Submitted and approved products in [Microsoft Merchant Center store](./hlp_BA_PROC_CreateBingMerchantCenterStore.md)
- Comply with [Microsoft Advertising policies](./hlp_BA_CONC_EditorialGuidelines.md)

## How do I enable Product Listings?

If you have a Microsoft Merchant Center store with approved offers, you are automatically opted in for Product Listings – no additional work for you to do!

If you want to opt out of Product Listings, click the **Show free Product Listings in the shopping tab**  toggle from the **Product Listings** page of your merchant center store.

## Product Listings requirements

- Submit products to Microsoft Merchant Center using any of the feed submission methods: feed file upload, the content API, or Google Merchant Center import. [Learn more](./hlp_BA_CONC_BMCWhatIsCatalog.md)
- Approved products in the store will be eligible to show in the free section of the Bing shopping tab.
- Products must comply with [Microsoft Advertising policies](./hlp_BA_CONC_EditorialGuidelines.md).
- Products must meet the [product specification requirements](./hlp_BA_CONC_AboutBingMerchantCenterCatalogFile.md).
- The “link” attribute must point to the direct URL of the product’s page on the retailer’s website.
   - The URL must be a direct link to the product’s landing page.
   - The URL cannot contain any campaign tracking parameters.

- The “ads_redirect” attribute will not be used and if it is included in the feed file, will be ignored.

## Tracking Product Listings

Take a look at the details you need to know about URLs and tracking for Product Listings.

- If you want to track Product Listings and Product Ads traffic, be sure to include the "link" and "ads_redirect" attributes in the feed file, with different tracking parameters.
- Use the "link" attribute to track free clicks. This URL must point to the product page and you can add tracking parameters to track the free clicks.
   - Free Product Listings will use this URL to drive clicks to the products on the retailers' site. The "ads_redirect" attribute will not be used for Product Listings.
   - Example URL: http://www.contoso.com/product.asp?pn=ISI1&amp;utm_source=Bing&amp;utm_medium=freeproductlistings​
   - Note: Do not add campaign tracking parameters to the "link" attribute. The tracking template values will not be replaced with campaign values, as there are no campaigns associated with Product Listings.

- Use the "ads_redirect" attribute to track clicks from Product Ads. This URL must point to the product page and you can add tracking parameters to track paid Product Ads clicks.
   - For Product Ads, when both "link" and "ads_redirect" attributes are present, the URL from the "ads_redirect" attribute will be used to drive clicks.
   - Ensure that tracking parameters used to track Product Listings are not in the "ads_redirect" attribute.

## Frequently asked questions

- **Are products associated with bids from MSC eligible to show in the unpaid section?**  Yes, if the products are relevant to users’ searches, they are eligible to show in the unpaid section.
- **Will I be charged for clicks from the unpaid section?**  No, all clicks from the unpaid section is free with no charges to clicks for you!
- **What reporting data will be available for Product Listings?**  Impressions and clicks will be reported for your Product Listings, available in your Microsoft Merchant Center.


