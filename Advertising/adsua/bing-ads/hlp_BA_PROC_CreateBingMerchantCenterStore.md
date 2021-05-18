---
title: Create a Microsoft Merchant Center store
description: If you want to list your feed on Bing, you first need to create Microsoft Merchant Center store.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Create a Microsoft Merchant Center store

<content_tile class="training">      [        New to Microsoft Shopping Campaigns? Learn how to get started in this training course.      ](https://go.microsoft.com/fwlink?LinkId=2130007)    </content_tile>

If you want to list your feed on Bing, you first need to create Microsoft Merchant Center store. Once you create a store it will either be auto-approved, auto-rejected or queued for a manual review. The review can take up to 5 days, but you will receive an email when an approval decision has been made.

1. On the top menu, click **Tools** and then click ** Microsoft Merchant Center**  (or from the global menu at the top of the page, click **Tools** and then **Microsoft Merchant Center**).
1. Click **Create store**.
1. Enter your store info, including your Store description and SSL Checkout selection. You also have the option to block aggregators here.
1. You'll also be asked to verify your site through **Domain validation**. You have two choices:
   - Validated via Bing Webmaster Tools. [Learn more](./hlp_BA_PROC_ClaimYourDomain.md)
   - Validated via [Universal Event Tracking (UET) tag](./hlp_BA_CONC_UETv2WhatIsTag.md)

**Note: **If you validate your domain using a UET tag, the tag has to register at least 50 events before the domain appears as an option when you create a Microsoft Merchant Center store.

1. Click **Save**.        After successful store creation, you will be taken to a page where you will be informed of the store status. You'll be able to check if your store was automatically approved/rejected or is queued up for manual review.

After your store is approved, you can [create your feed](./hlp_BA_CONC_BMCWhatIsCatalog.md).

## Things to keep in mind when creating a store

- Store name is required and cannot be changed later and it will appear in your product ads, so accuracy is important.
- Destination URL has to have been verified using Bing Webmaster Tools or a UET tag. It must also comply with URL formatting rules such as starting with a protocol (http:// or https://).
- If you want to use the content API for creating and sending feeds, you will need to get a tenant URL. [Learn more](https://go.microsoft.com/fwlink?LinkId=843127)
- If you validate your domain using a UET tag, the tag has to register at least 50 events before the domain appears as an option when you create a Microsoft Merchant Center store.

## Potential store rejection reasons

- Attempting to claim an unverified domain
- Microsoft Advertising customer has been identified as an adult advertiser.
- Lack of presence in the markets supported for product ads by Microsoft Advertising.
- Lack of a “real” privacy policy on website.
- Non-encrypted (non-SSL) checkout. You will want to verify that your SSL certificates are valid.

## Creating multiple stores:

You can create multiple stores, but you are not allowed to sell the same products through multiple stores. For example, if you sell sporting equipment you can create a golf store and a basketball store. You can also create multiple stores for the same domain, up to the number of markets we serve. However, you can only create a feed that targets a specific market from one of those stores. You can create as many feeds targeting that market from within that one store, but only that store.


