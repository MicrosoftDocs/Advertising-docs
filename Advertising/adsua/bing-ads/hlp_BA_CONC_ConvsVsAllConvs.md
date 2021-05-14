---
title: Conversion goals: "Conversions" versus "All conversions"
description: Learn about the differences between the Conversions columns and the All conversions columns in the data table.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Conversion goals: "Conversions" versus "All conversions"

Different [conversion goals](./hlp_BA_CONC_UETv2CTGoalType.md) can have different values for your business. That's why, when creating or editing a conversion goal, you can choose whether or not to include each time the goal is achieved in your "Conversions" columns. This makes sure that the "Conversion" columns on your Conversion goal data table and in your reports reflect only the conversion goals that matter most to you.

## How to change the Include in "Conversions" setting for a conversion goal

## When creating a conversion goal
1. Click **Campaigns** at the top of the page, and then on the left pane, click **Conversion Tracking** and then **Conversion goals** (or from the global menu at the top of the page, click **Tools** and then **Conversion goals**).
1. Click **Create conversion goal**.
1. Name the goal, choose your conversion goal type, and then click **Next**.
1. Under **Goal details**, uncheck **Include in "Conversions"**.

> [!IMPORTANT]
> If you use an automated bidding [bid strategy](./hlp_BA_CONC_BidStrategy.md), unchecking **Include in "Conversions"** will result in these conversions no longer factoring into automated bidding calculations.
> The **Include in "Conversions"** setting does not affect view-through conversions (not everyone has this feature yet). View-through conversions appear in both columns by default. [Learn more about view-through conversions](./hlp_BA_CONC_ViewThroughConv.md).

## When editing a conversion goal
1. Click **Campaigns** at the top of the page, and then on the left pane, click **Conversion Tracking** and then **Conversion goals** (or from the global menu at the top of the page, click **Tools** and then **Conversion goals**).
1. Select the conversion goal you want to edit.
1. Click **Edit**&nbsp;&gt;&nbsp;**Edit goal**.
1. Click **Next**.
1. Under **Goal details**, uncheck (or re-check) **Include in "Conversions"**.

> [!IMPORTANT]
> If you use an automated bidding [bid strategy](./hlp_BA_CONC_BidStrategy.md), unchecking **Include in "Conversions"** will result in these conversions no longer factoring into automated bidding calculations.
> The **Include in "Conversions"** setting does not affect view-through conversions (not everyone has this feature yet). View-through conversions appear in both columns by default. [Learn more about view-through conversions](./hlp_BA_CONC_ViewThroughConv.md).

## Example of when to uncheck Include in "Conversions"

Let's say you sell sunglasses online, and you have a conversion goal named "SALES" to track each time a sale is made. But you're also curious about how many times customers add a pair of sunglasses to their shopping carts, so you create a conversion goal named "CART" to track that as well.

Sales matter the most to you, and that means two things:
- You want to optimize your bidding around the SALES conversion goal.
- You don't want the CART conversion goal cluttering your Conversion goal data table and your reports.

All you need to do is uncheck Include in "Conversions" for the CART conversion goal. Now shopping-cart customer actions aren't factored into your bidding optimization and don't appear in your data table and reports under "Conversions". However, you can still track the CART conversion goal using the "All conversions" columns (see below).

## The "Conversions" and "All conversions" columns

If you uncheck Include in "Conversions" for a conversion goal, you can still track it using the "All conversions" columns of your Conversion goal data table and your reports (for example, "All conversions", "All conversions rate", and "All conversions revenue"). Using the above example, these columns work like this:

<table style="min-width:600px;">
  <tr>
    <th scope="col" rowspan="2" style="text-align:center">Example conversion goal</th>
    <th scope="col" rowspan="2" style="text-align:center">Include in "Conversions"</th>
    <th scope="col" colspan="2" style="text-align:center">Conversion goal data will appear in</th>
  </tr>
  <tr>
    <th scope="col" style="text-align:center">"Conversions" columns</th>
    <th scope="col" style="text-align:center">"All conversions" columns</th>
  </tr>
  <tr>
    <td style="text-align:center">SALES</td>
    <td style="text-align:center">Checked</td>
    <td style="text-align:center;vertical-align:middle">
        ![Yes](../images/Global_Icon_CheckMark.png)
      </td>
    <td style="text-align:center;vertical-align:middle">
        ![Yes](../images/Global_Icon_CheckMark.png)
      </td>
  </tr>
  <tr>
    <td style="text-align:center">CART</td>
    <td style="text-align:center">Unchecked</td>
    <td style="text-align:center;vertical-align:middle">
        ![No](../images/Global_Icon_Xmark.png)
      </td>
    <td style="text-align:center;vertical-align:middle">
        ![Yes](../images/Global_Icon_CheckMark.png)
      </td>
  </tr>
</table>


