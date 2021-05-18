---
title: About aggregators
description: If you are an aggregator, here are some details you need to display ads for the products of merchants you represent.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# About aggregators

Aggregators are third-party sites that consolidate products to Bing on behalf of individual merchants. If you are an aggregator, here are some details you need to display ads for the products of merchants you represent.

## Signing up

To get started as an aggregator, you need to:

- [Create a Microsoft Merchant Center store](./hlp_BA_PROC_CreateBingMerchantCenterStore.md). Create a single store with your domain URL. If you also directly sell specific sets of products, you need to create a separate store to directly advertise those products.
- [Contact support](https://go.microsoft.com/fwlink?LinkId=398371) to identify yourself as an aggregator.
- Once that is set up, you must use a single store and submit products to the store.

## Feed requirements

Your feed file is a text delimited file that contains all the information needed for your product ads. Feed files for aggregators can be submitted like any product feed file – manually, via FTP, automatically downloaded from a URL, or from Google Merchant Center import. For manual uploads, .tsv or .xml file formats are accepted. For FTP uploads, .tsv, .txt, or .xml file formats are accepted. [Learn more](./hlp_BA_CONC_BMCWhatIsCatalog.md)

The following product identifiers are required for aggregators:

- **Seller name**  must be the name of the final retailer.
- **Link**  (product URL and destination URL) must be a direct link to the seller's product page.

You can optionally use **bingads_redirect**  to track leads to the final seller’s page. The redirect must be immediate with no additional pages from when the customer clicks your ad and the final seller’s landing page.

## What you need to know

- Product ads served through aggregators appear as normal product ads, with the seller’s name displayed.
- Aggregators’ ads compete with direct retailers’ ads.
- Sellers may block aggregators from advertising on their behalf. If aggregators are blocked, the seller’s products would be rejected on the aggregator’s store. You can view these details in the rejection reports.
- Ads must comply with all [Microsoft Advertising policies](./hlp_BA_CONC_EditorialGuidelines.md).


