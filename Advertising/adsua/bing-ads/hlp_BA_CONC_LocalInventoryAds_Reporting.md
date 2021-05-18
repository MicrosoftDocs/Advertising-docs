---
title: Using Local Inventory Ad reports
description: Learn about the different Local Inventory Ad reports you can view.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Using Local Inventory Ad reports

> [!IMPORTANT]
> Local Inventory Ads are currently available in Australia, Austria, Belgium, France, Germany, Italy, the Netherlands, Spain, Sweden, Switzerland, the United Kingdom and United States.

Now that your Local Inventory Ads are up and running, you’ll want to keep track of how your ads are performing.

The following click type data is available for the reports listed below:

- **Shopping ad** : A click on your ad, showing an online product.
- ** Shopping ad – local** : A click on your ad, showing a local product.
- **Shopping ad – multichannel local** : A click on the local section of your ad that has two links. One click to the local product and another click to the online product.
- **Shopping ad – multichannel online** : A click on the in-store decoration will result in the multichannel local click reporting. Click on the main ad with the in-store decoration will result in the multichannel online click.

## Availability

We are working with retailers who have physical stores in the United Kingdom and United States.

## Add shopping ad click types to reports
When running product partition, product partition unit, or product dimension reports, be sure to add the click type column to view your shopping ad click type data.

1. On the **Reports** page, in the left pane, select the report you want to run under **Product ads** (or from the global menu, click **Reports** > **Standard reports**).
1. In the **Choose your columns** section, add the **Click type** attribute.
1. Click **Run** to generate the report, or **Download** to get the report as a .csv or .tsv file.

## Using reports to track Local Inventory Ads
From Microsoft Merchant Center, you can see the following reports:

|Report type|Description|
|---|---|
|Store summary|**What it shows**: Data for local feeds, online feeds, and all other feeds.|
|Published report|**What it shows**: Data for the number of published offers.|
|Reject report|**What it shows**: Data for the number of rejected offers.|
|Matching report|**What it shows**: Data for the number of offers matched to the online product feed.|

From Microsoft Advertising reporting, you can view the following reports:

<table>
  <tr>
    <th colspan="2" scope="col">Product partition</th>
  </tr>
  <tr>
    <td>
        <strong>What it shows:</strong> The impressions, clicks, spend, average cost-per-click and average conversion for each product group in your Microsoft Shopping Campaigns.
      </td>
    <td>
        <strong>Why run it:</strong> To see the performance data for the product groups in your shopping campaigns and to optimize your campaigns accordingly. This report will also allow you to segment your data by the store code and click type.
      </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Product partition unit</th>
  </tr>
  <tr>
    <td>
        <strong>What it shows:</strong> The impressions, clicks, spend, average cost-per-click, and average conversions for each product group in your Microsoft Shopping Campaigns. Depending on the report time and columns you choose, the report may include more than one row per product group. This report will also allow you to segment your data by the store code and click type.
      </td>
    <td>
        <strong>Why run it:</strong> To see product partition unit data of your Product Groups in Shopping Campaigns.
      </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Product dimension</th>
  </tr>
  <tr>
    <td>
        <strong>What it shows:</strong> The impressions, clicks, spend, average cost-per-click and conversion for each product in your catalog [each line item in Microsoft Merchant Centercatalog]. This report will also allow you to segment your data by the store code and click type.
      </td>
    <td>
        <strong>Why run it:</strong> To figure out which of your products are triggering ads and getting the most clicks and optimize the ones not performing so well.
      </td>
  </tr>
</table>

## Add channel and channel exclusivity filters
Use channel and channel exclusivity filters for your local inventory products.

- **Channel** : Filter products for online or local availability.
- **Channel exclusivity** : Filter products depending on online or local availability, or both.

You can show products sold only in local stores but not online by setting the filters to “Channel”: “Local stores” and “Channel exclusivity”: “Single-channel”.

## How do I segment my report by channel or channel exclusivity?
Create a channel or channel exclusivity report from the **Dimensions** tab:

- On the **Campaigns** page, click the **Dimensions** tab, and then select **Channel** or **Channel exclusivity** from the **Show:** dropdown.

Create a channel or channel exclusivity report on the **Reports** page:

1. On the **Reports** page, in the left pane, select the report you want to run under **Product ads** .
1. In the **Choose your columns** section, add the **Channel** or **Channel exclusivity** attributes.
1. Click **Run** to generate the report, or **Download** to get the report as a .csv or .tsv file.


