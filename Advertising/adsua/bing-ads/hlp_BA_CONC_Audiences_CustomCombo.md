---
title: Combined lists: Mix and match audiences to reach just the right customers
description: Learn how to combine audiences to reach just the right set of customers.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Combined lists: Mix and match audiences to reach just the right customers

> [!IMPORTANT]
> Not everyone has this feature yet. If you don't, don't worry—it's coming soon!

With combined lists, you combine existing audience lists to create a new one. Combine lists using AND, OR, and NOT conditions to reach just the right set of customers.

## Examples

- **Selling products** : Let's say you sell camping gear, and you want to drive sales of camping accessories:
|**List A**  Purchased a tent|**AND**|**( List B**  Viewed an air mattress|**OR**|**List C )**  Viewed a sleeping bag|**=**|**Combined list**  Audience for accessories sale|
|---|---|---|---|---|---|---|

- **Getting leads** : Let's say you provide tax-preparation services, and you want to reach new customers:
|**List A**  Previous website visitor|**NOT**|**List B**  Already filed taxes|**=**|**Combined list**  Potential new customers|
|---|---|---|---|---|

Both of these examples were possible previously, but required multiple audience associations or audience exclusions. With combined lists, there's just one audience list to work with.

## Using combined lists

## How do I create a combined list?
1. In the left pane, click **Shared Library** and then **Audiences** (or from the global menu at the top of the page, click **Tools** and then **Audiences**).
1. Click **Create audience**.
1. Give this audience a unique name.
1. For **Type**, select **Combined list**.
1. Click **Next**.
1. Combine audience lists into a set of conditions:
   1. First, select **how** you want to combine audiences:
|Combination option|What it means|
|---|---|
|Any of these audiences (OR)|This will include customers who are in any of these audience lists.|
|Each of these audiences (AND)|This will include only customers who are in every single one of these audience lists.|
|None of these audiences (NOT)|This will **exclude** customers who are in any of these audience lists.|

   1. Then, search or browse for existing audience lists and select the appropriate ones.
   1. Click **Done**.

1. You now have the option to click **Add** and create another set of conditions to combine with the set you just created. Each condition set is combined with the other using an AND condition.
1. When you're done, click **Save**.

> [!NOTE]
> Combined lists must have at least 300 members.

## How do I associate combined lists?
1. From the **Campaigns** page, click the **Audiences** tab (or from the main menu on the left, click **All campaigns** and then **Audiences**).
1. Click **Create association**.
1. Select the ad group or campaign you want to associate with the combined list.
1. Under **Ad group targeting** or **Campaign targeting**, select **Combined list** and then select the appropriate list.
1. Select your **Targeting setting**:
   - **Bid only** : Shows ads to people searching for your ad, with the option to make bid adjustments for the selected audience.
   - **Target and bid** : Shows ads only to the selected audience, with the option to make bid adjustments.

1. Set the **Default bid adjustment**. By default, new targeting associations are set to 15%, however, the bid adjustment can range from -90% to +900%.
1. Click **Save**.

## What audience types can I combine, and are there any restrictions?
|Audience type|Restrictions|
|---|---|
|Remarketing list|Can only be combined with other remarketing lists and/or dynamic remarketing lists.|
|Dynamic remarketing list|Can only be combined with other dynamic remarketing lists and/or remarketing lists.|
|Custom audience|Can only be combined with other custom audiences.|
|Similar audience|Can only be combined using a single OR condition with one other similar audience.  				(Not everyone has this feature yet.)|
|Customer list|Can only be combined with other customer lists.  				(Not everyone has this feature yet.)|
|In-market audience|Not eligible for combined lists.|
|LinkedIn profile targeting|Not eligible for combined lists.|
|Combined list|Combined lists cannot be combined.|

> [!NOTE]
> Combined lists are just one of our [audience targeting options](./hlp_BA_CONC_Audiences_Options.md).


