---
title: Share website exclusion lists across accounts
description: Learn how to create shared website exclusion lists and associate them with multiple accounts.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Share website exclusion lists across accounts

> [!NOTE]
> This feature is only available from the redesigned Microsoft Advertising.

You can keep your ads from showing on specific websites using account-level website exclusion lists.

## What you need to know about website exclusion lists

- Account-level website exclusions are applied in addition to any exclusions set at the campaign or ad-group level.
- Shared website exclusion lists are created, edited, and deleted from the manager-account level. At the account level, you can view and disassociate lists.
- Once you create a website exclusion list, you must associate it with at least one account for it to take effect.
- You can't add Microsoft sites (such as microsoft.com) to your excluded websites list.
- Maximums:
   - 3 shared website exclusion lists per manager account.
   - 10,000 URLs per website exclusion list (but you cannot add more than 5,000 at one time).
   - No limit on the number of accounts a website exclusion list may be associated with.

## Create account-level website exclusion lists

1. At the manager-account level, from the global menu, click **Tools** and then **Website exclusion lists**.
1. On the **Website exclusion lists** page, click **Create website exclusion list**.
1. Name your list in the **List name** box.
1. Enter the URLs of websites that you don't want your ads to show on.
## Examples of URL formats
contoso.com 					www.contoso.com 					autos.contoso.com 					contoso.com/widgets 					http://www.contoso.com 					https://www.contoso.com
Tip: If you want to exclude any page on a specific domain, leave off the "www" prefix. For example, use "contoso.com" if you want to block traffic from www.contoso.com and www2.contoso.com.

1. Click **Save**.

> [!NOTE]
> To add URLs to an existing website exclusion list, just return to the **Website exclusion lists** page, select the list's name, and then click **Add website exclusions**.

## Associate website exclusion lists to accounts

1. While at the manager-account level, from the global menu, click **Tools** and then **Website exclusion lists**.
1. Either:
   1. Select the list's name and then click **Accounts sharing this list**&nbsp;&gt;&nbsp;**Add accounts**.
   1. Select the checkbox next to one or more lists and then click **Add to accounts**.

1. Click the arrow next to each appropriate account in the **All manager accounts and accounts** list to move it to the **Selected items** list (or click **Add all** to select the entire list).
1. Click **Save**.

> [!NOTE]
> To see the website exclusion lists applied to an individual account, from that account's global menu, click **Tools** and then **Website exclusion lists**.

## Add campaign- or ad-group-level website exclusions

Campaign- and ad-group-level website exclusions are applied in addition to any exclusions set at the account level.

1. To exclude specific websites at the campaign level:
   - From the main menu on the left, click **All campaigns** and then **Campaigns**.
   - Select the checkbox next to the name of the campaign that you want to edit.

1. To exclude specific websites at the ad-group level:
   - From the main menu on the left, click **All campaigns** and then **Ad groups**.
   - Select the checkbox next to the name of the ad group that you want to edit.

1. Click **Edit**&nbsp;&gt;&nbsp;**Other changes**.
1. For **Select a setting**, select **Website exclusions**, and then enter the URLs of websites you want to exclude in the box.
1. Click **Apply**.

## Manage website exclusion lists

To make changes to an existing website exclusion list at the manager-account level, from the global menu, click **Tools** and then **Website exclusion lists**:

- **Delete a list** : Select the checkbox next to one or more lists and then click **Delete**.
- **Remove a website exclusion from a list** : Select the list's name,  select the checkbox next to one or more website exclusions, and then click **Delete**.
- **Disassociate a list from an account** : Select the list's name, click **Accounts sharing this list**, select the checkbox next to one or more accounts, and then click **Disassociate**.
- **Rename a list** : Hover over the list's name and select the pencil icon.


