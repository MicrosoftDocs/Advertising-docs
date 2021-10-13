---
title: Share website exclusion lists across accounts
description: Learn how to create shared website exclusion lists and associate them with multiple accounts.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Share website exclusion lists across accounts

You can keep your ads from showing on specific websites using account level website exclusion lists.

## What you need to know about website exclusion lists

- Account level website exclusions are applied in addition to any exclusions set at the campaign or ad group level.
- Shared website exclusion lists are created, edited, and deleted from the manager account level. At the account level, you can view and disassociate lists.
- Once you create a website exclusion list, you must associate it with at least one account for it to take effect.
- Website exclusions will not exclude search ads that are part of the Bing, AOL, and Yahoo owned and operated sites.
- Maximums:		 
   - 3 shared website exclusion lists per manager account.
   - 10,000 URLs per website exclusion list (but you cannot add more than 5,000 at one time).
   - There is no limit on the number of accounts a website exclusion list may be associated with.

## How to create account level website exclusion lists

1. [!INCLUDE [WebsiteExclusionLists](./includes/WebsiteExclusionLists.md)]
1. On the **Website exclusion lists** page, select **Create website exclusion list**.
1. Name your list in the **List name** box.
1. Enter the URLs of websites that you don't want your ads to show on.
## Examples of URL formats
contoso.com 					www.contoso.com 					autos.contoso.com 					contoso.com/widgets 					http://www.contoso.com 					https://www.contoso.com
Tip: If you want to exclude any page on a specific domain, leave off the "www" prefix. For example, use "contoso.com" if you want to block traffic from www.contoso.com and www2.contoso.com.

1. Select **Save**.

> [!NOTE]
> To add URLs to an existing website exclusion list, just return to the **Website exclusion lists** page, select the list's name, and then select **Add website exclusions**.

## Associate website exclusion lists to accounts

1. While at the manager account level, from the top menu, select **Tools** > **Website exclusion lists**.
1. Either:
   1. Select the list's name and then select **Accounts sharing this list**&nbsp;&gt;&nbsp;**Add accounts**.
   1. Select the checkbox next to one or more lists and then select **Add to accounts**.

1. Select the arrow next to each appropriate account in the **All manager accounts and accounts** list to move it to the **Selected items** list (or select **Add all** to select the entire list).
1. Select **Save**.

> [!NOTE]
> To see the website exclusion lists applied to an individual account, from that account's top menu, select **Tools** > **Website exclusion lists**.

## How to add campaign or ad group level website exclusions

Campaign and ad group level website exclusions are applied in addition to any exclusions set at the account level.

1. To exclude specific websites at the campaign level:
   - [!INCLUDE [CampaignsCampaigns](./includes/CampaignsCampaigns.md)]
   - Select the checkbox next to the campaign that you want to edit.

1. To exclude specific websites at the ad group level:
   - [!INCLUDE [AdGroupsCampaigns](./includes/AdGroupsCampaigns.md)]
   - Select the checkbox next to  the ad group that you want to edit.

1. Select **Edit**&nbsp;&gt;&nbsp;**Other changes**.
1. For **Select a setting**, select **Website exclusions** and then enter the URLs of websites you want to exclude in the box.
1. Select **Apply**.

> [!NOTE]
> You can specify a maximum of 2,500 URLs to exclude.
> Each URL must specify the domain name, and can specify one subdomain name and a maximum of two directories.
> Duplicate URLs are not added.
> Ad group level website exclusions override campaign level website exclusions.

## Manage website exclusion lists

To make changes to an existing website exclusion list at the manager account level, from the top menu, select **Tools** > **Website exclusion lists**:

- **Delete a list** : Select the checkbox next to one or more lists and then select **Delete**.
- **Remove a website exclusion from a list** : Select the list's name, select the checkbox next to one or more website exclusions, and then select **Delete**.
- **Disassociate a list from an account** : Select the list's name and then select **Accounts sharing this list**. Select the checkbox next to one or more accounts, and then select **Disassociate**.
- **Rename a list** : Hover over the list's name and select the pencil icon.


