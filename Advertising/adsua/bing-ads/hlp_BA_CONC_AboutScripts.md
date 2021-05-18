---
title: How can I automate my campaigns with Microsoft Advertising Scripts?
description: Learn how to automate your account and campaigns with Microsoft Advertising Scripts.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How can I automate my campaigns with Microsoft Advertising Scripts?

Microsoft Advertising Scripts are pieces of JavaScript code you can use to automatically create, change, or delete items in your account based on custom criteria. You can make hundreds (or thousands!) of changes across your account all at once, without needing to make the changes manually.

Here are some examples of using scripts:
- Schedule campaigns linked to a launch or sale.
- Have an ad pause automatically when the item it's advertising is out of stock.
- Make a rule across your account to increase broad-match keyword bids by 25% for keywords that generated more than 100 impressions that day.

## Using Microsoft Advertising Scripts

## Who should use scripts?
Scripts are most helpful for people who manage large campaigns and/or a large number of campaigns. It also helps to have some experience scripting in JavaScript.

It's important to keep in mind that Microsoft Advertising Scripts can make wide-ranging changes to your campaigns, and that scripts do not have an "Undo" button. If you find this prospect daunting, then [automated rules](./hlp_BA_CONC_AutoRuleIntro.md) might be more suitable for you.

## How do I create and run Microsoft Advertising Scripts?
1. On the left navigation pane, click **Bulk Operations** and then **Scripts** (or from the global menu at the top of the page, click **Bulk actions** and then click **Scripts**). This is the main **Scripts** page where you will see any scripts you have already created.
1. Click **Create script**.
1. In the script editor, write or paste in your script.
   1. To see example scripts that you can copy, click **Show examples**.
   1. For instructions on scripting, take a look at our [Scripts documentation](https://go.microsoft.com/fwlink?LinkId=871630), and for more script snippets you can copy, check out our [scripts code examples](https://go.microsoft.com/fwlink?LinkId=871631).

1. Click **Save**.
1. Click **Preview** to see a list of all the changes this script will make. Previewing a script is optional, but is **strongly** recommended.
1. If you want to run the script right away, click **Run script now**.
1. If you want to run the script at a certain time, or at multiple specific times, click  **Create schedule**.

> [!NOTE]
> If you have multiple accounts and want to run a script across them, you'll need to create the script from your [Accounts Summary page](./hlp_BA_CONC_AccountsSummary.md)&nbsp;— click **Bulk Operations** and then **Scripts**.
> If you share accounts with other account managers, be aware that only the author of a script will be able to see and run that script.

## How do I manage scripts?
After you run a script, it will appear under **Logs** on the main **Scripts** page (From the global menu at the top of the page, click **Bulk actions** &gt; **Scripts**. There you will see when the script ran, how long it took to run, how many changes were made, and how many changes failed. For more information on what the script did:
1. In the script's **Summary** column, click **View details**.
1. On the script's **Log details** page, you'll see all the changes the script made.
1. To see how the script made these changes — as well as any errors encountered and log messages you included with the script — click **Logs**.

To run a script that you have already created:
1. Find the script in your list of previously-created scripts on the main **Scripts** page.
1. Click **Run** &nbsp; — or click **Create schedule** to have the script run at a certain time, or at multiple specific times.

## Can I use the scripts that I created in Google Ads?
Yes, just paste them right in. When you click **Save**, we will automatically make some changes to make them compatible with Microsoft Advertising. However, you will need to update the script manually to fix the following compatibility issues:
- If the script calls the budget selector, it returns only shared budgets. To get a campaign's individual budget, you must access it directly from the campaign.
- If the script includes IDs, you’ll need to turn them into strings by wrapping them in double quotation marks. For example, you’ll need to change .withIds([1234]) to .withIds("1234"]).
- If the script calls an entity's getStatsFor() method, you’ll need to change the call to getStats() and specify the date range using the selector's forDateRange() method.
- If the script calls the keyword selector's withIds() method, make sure you pass only an array of keyword IDs. In Microsoft Advertising, keyword IDs are unique, so there’s no need to pass an array of ad group ID and keyword ID pairs.

> [!NOTE]
> If the script adds negative keywords with broad match type, Microsoft Advertising converts them to phrase match type when adding them to the account. Microsoft Advertising doesn't support broad match type for negative keywords.

 
## For more information

Visit our documentation site for details on scripting:

|[Get Started with Microsoft Advertising Scripts](https://go.microsoft.com/fwlink?LinkId=871630)|&nbsp;|[Microsoft Advertising Scripts Code Examples](https://go.microsoft.com/fwlink?LinkId=871631)|
|---|---|---|


