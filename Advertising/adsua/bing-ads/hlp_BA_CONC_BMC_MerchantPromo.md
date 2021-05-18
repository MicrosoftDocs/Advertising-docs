---
title: Getting started with Merchant Promotions
description: Learn how you can promote products directly from your Microsoft Shopping Campaigns with Merchant Promotions.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Getting started with Merchant Promotions

<content_tile class="training">      [        New to Microsoft Shopping Campaigns? Learn how to get started in this training course.      ](https://go.microsoft.com/fwlink?LinkId=2130009)    </content_tile>

With Merchant Promotions, you can promote products directly from your Microsoft Shopping Campaigns inventory with special offer tags. These tags appear at the bottom of your product ad as “special offer” links, helping to increase customer engagement. Merchant Promotions are free to add to your product ads, with the usual charges for any clicks you get. Including Merchant Promotions can improve the visibility of your ads, which can lead to more clicks and improve your ROI.

## How do I get started with Merchant Promotions?

The participation requirements for Merchant Promotions are:

- **Microsoft Merchant Center store:**  If you don't have one, learn [how to create a Microsoft Merchant Center store.](./hlp_BA_PROC_CreateBingMerchantCenterStore.md)
- **Microsoft Merchant Center product feed:**  Your Microsoft Merchant Center must have at least one product feed file. Your feed file is a text delimited file that contains all the information needed to submit a promotion. For manual uploads, .tsv or .xml file formats are accepted. For FTP uploads (available in the United States only), .tsv, .txt, or .xml file formats are accepted. After you create a feed file, [      submit it to Microsoft Merchant Center    ](./hlp_BA_CONC_BMCWhatIsCatalog.md). If you don't have a products feed, learn [how to create a feed file.](./hlp_BA_PROC_BMCCreateFeedFile.md)
- **Merchant Promotions approval request:**  Request access to Merchant Promotions from your account manager or by using the interest form linked above.
- Available in the following markets for desktop and mobile devices:
   - Australia
   - Canada
   - France
   - Germany
   - India
   - Italy
   - Netherlands
   - Spain
   - Sweden
   - Switzerland
   - United Kingdom
   - United States

Once you've been approved, take a look at how to create a promotion below.

## Why is my Merchant Promotion not serving?

Even if a Merchant Promotion is eligible to serve, they're not guaranteed to always serve. Whether an extension serves depends on a number of factors. Here are a few listed below:

- The relevance and quality of your ad
- The relevance and quality of the extension data provided
- Ad space availability on the page
- User signals, like location, device used, etc.
- Other extensions you enabled for your ad
- Availability of extension data for competing ads

Our algorithms optimizes and balances the needs of users, advertisers, and constraints of the search results page. Our algorithms chooses the best layout for each ad by evaluating hundreds of possible combinations based on all available extension data, space allocated, and the positive impact it can provide for advertiser and user.

**Best practice** : Providing extension data allows our algorithms to evaluate all the possible layouts for your ad. It increases the chances of additional space being allocated and increasing clicks for your ad.

## Option 1: Create multiple promotions by uploading a feed file
If you want to submit promotions in bulk, use a promotions feed file to submit multiple promotions with one feed from a spreadsheet. Take a look at the [Merchant Promotions feed specifications](./hlp_BA_CONC_BMC_MerchantPromoFeedFile.md) or view an example of a [.txt](https://go.microsoft.com/fwlink?LinkId=852614) or [.xml](https://go.microsoft.com/fwlink?LinkId=852613) feed before submitting your feed.  (You must use Edge, Chrome, or Firefox browsers to view the .xml feed example.)

1. On the top menu, click **Tools** and then click ** Microsoft Merchant Center**  (or from the global menu at the top of the page, click **Tools** and then **Microsoft Merchant Center**).
1. Click **Update feed** in Microsoft Merchant Center.
1. Select the **Target country/region &amp; language** from the preset list.
1. Select the feed file you want to upload.
1. Click **Upload**.

**What you need to know** :
- If the promotion doesn't apply to all products, be sure to map the promotion ID to the correct set of products in the master feed.
- The name of the file needs to start with Promotions_\*. If uploading via FTP, the file name of .tsv, .txt, or .xml files have to match the file name specified for a catalog’s settings. In the case of compressed text format, the compressed .txt file inside the archive (.zip, .gz, .gzip, .tar.gz, .tgz) must have the matching file name.
- You can use the UI to upload the file manually.
- You can use FTP to send the file programmatically. If you use FTP, make sure that the file name starts with Promotions_.

## Option 2: Create a promotion
If you want to create a single promotion, create the promotion directly in Microsoft Merchant Center.

1. On the top menu, click **Tools** and then click ** Microsoft Merchant Center**  (or from the global menu at the top of the page, click **Tools** and then **Microsoft Merchant Center**).
1. Click on the **Promotions** tab in Microsoft Merchant Center.
1. Click **Create promotion**.
1. Enter the **Promotion ID**.
1. Select the **            Target country/region &amp; language          ** from the preset list.
1. Enter the promotion **Title**.
1. Select the promotion's date and time.
1. Select the products that are eligible for the promotion. You can also provide a redemption code, if applicable.
1. (Optional) Enter the minimum purchase amount.
1. Click **Save**.

**Note** :
- If the promotion doesn't apply to all products, be sure to map the promotion ID to the correct set of products in the master feed.
- The promotion's date and time is based on your local time zone. Keep this in mind if you want to have the promotion in any other time zone.

 

