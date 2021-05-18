---
title: How do I manage my conversion goals?
description: The data grid on the conversion goals page allows you to view the goals you created and edit the name and description inline.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How do I manage my conversion goals?

The Conversion goals page allows you to review each goal and track the goal type, status, and the number of conversions.

1. In the left navigation pane, click **Conversion Tracking** and then **Conversion goals** (or from the global menu at the top of the page, click **Tools** and then **Conversion goals**).
1. In the table, review the columns.
> [!NOTE]
> For editable column values, edits apply to the conversion goal going forward and don't impact past conversion goal data.

## Status
**What it is:**  The status of a conversion goal can be either Enabled or Removed. When a goal is removed, Microsoft Advertising stops counting conversions for that conversion goal.

**Can I edit it:**  Yes. In the table, hover over the Status, click the arrow that appears, and then select **Enabled** or **Removed**.

## Goal name
**What it is:** The name of the conversion goal.

**Can I edit it:** Yes. Click the name and then make any necessary change in the the **Name** field. Please note that after you choose a name for your conversion goal, the same name may not be used again in the future.

## Tracking status
**What it is:** This is the status to tell you if your conversion goal is working. It can be:
- **Unverified** : Microsoft Advertising hasn’t received any user activity data from the UET tag on your website. It can take up to 24 hours for Microsoft Advertising to verify. If you still see this status, you either have not added the UET tag tracking code to your website or there is an issue with the setup that you need to fix.
- **No recent conversions** : Microsoft Advertising has seen your UET tag, but haven't recorded any conversions in the last 7 days. This is most likely because you either have created the goal incorrectly, have not tagged your entire website, especially the pages that have the conversion action or you don't have any users converting on your site.
- **Recording conversions** : Microsoft Advertising has seen your UET tag and has recorded conversions within the last 7 days. If your conversion window is greater than 7 days and you are filtering on the last 7 days, you may see this status even if no conversions are shown in the **Conversions** column, as conversions are reported at the time of the click.
- **Tag inactive** : Microsoft Advertising has not received any user activity data from the UET tag in the last 24 hours. Make sure that the UET tag tracking code is still on your website.

Note that the Unverified and Tag inactive statuses do not apply to [Mobile App Install](./hlp_BA_PROC_UETv2MobileApp.md) type goals.

**Can I edit it:** No

 
> [!NOTE]
> If your tracking status is **Unverified**, **Tag inactive**, or **No recent conversions**, troubleshoot your issues by following the steps in [Why am I not recording conversions or tracked revenue?](./hlp_BA_CONC_UET_TroubleshootCT.md)

## Include in "Conversions"
**What it is:** **** : This determines whether or not actions that meet the criteria of your conversion goal should appear in the "Conversions" column in your data table.

**Can I edit it:** Yes. Click the conversion goal's name, click **Next**, and then select or unselect **Include in "Conversions"**.

## Type
**What it is:** This is the conversion goal type, which can be destination URL, duration, pages viewed per visit, event, or mobile app install. You define the type when you create the conversion goal.

**Can I edit it:** Yes. Click the conversion goal's name and then select a type.

## Scope
**What it is:** This determines if the goal applies to all accounts or a specific account.

**Can I edit it:** No. Once this is set, you can't change it. If you want to change the scope, you need to create a new conversion goal and delete the old one.

## Count
**What it is:** This determines how your conversions are recorded within your chosen conversion window: Either all conversions that happen after an ad click, or only one conversion that happens after an ad click.

**Can I edit it:** Yes. Click the conversion goal's name, click **Next**, and for **Count**, select either **All** or **Unique**.

## Conversion window
**What it is:** This is the length of time after a click that you want to track conversions.

**Can I edit it:** Yes. Click the conversion goal's name, click **Next**, and for **Conversion window**, enter a new time frame.

## Tag ID
**What it is:** The name of the UET tag associated with this goal. Click on **View tag** to see the UET tag tracking code.

**Can I edit it:** Yes, in that you can change the UET tag associated with this goal. Click the conversion goal's name, click **Next**, and for **UET tag**, select a different tag.

## All conv.
**What it is:** This is the total value for conversions (for the selected date range), regardless of whether or not **Include in "Conversions"** is selected for this conversion goal. [Learn more about "Conversions" versus "All conversions"](./hlp_BA_CONC_ConvsVsAllConvs.md).

**Can I edit it:** No

## All conv. revenue
**What it is:**  This is the total revenue value tracked for conversions (for the selected date range), regardless of whether or not **Include in "Conversions"** is selected for this conversion goal. [Learn more about "Conversions" versus "All conversions"](./hlp_BA_CONC_ConvsVsAllConvs.md).

**Can I edit it:** No

## Repeat rate
**What it is:** This is the ratio of all conversions / unique conversions during your chosen conversion window for the selected date range. You can change the date range in the upper right corner of the page

**Can I edit it:** No


