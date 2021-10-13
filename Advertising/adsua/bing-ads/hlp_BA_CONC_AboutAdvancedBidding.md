---
title: How to target my customers by adjusting my bids
description: Use bid adjustments to increase your bid for the demographics (e.g. gender, age, location, time of day) that are most important to your advertising campaign.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How to target my customers by adjusting my bids

![Target](../images/BA_Conc_Target.svg)
Bid adjustments increase or decrease your bid for specifically targeted customers.

For example, let's say you want to improve the odds of showing your ads to customers who are 25-34 years old. Your bid on the keyword "shoes" is $1.00. You add a 20% bid adjustment for the age group 25-34. Now, when a search user of the targeted age searches for "shoes", your bid is $1.20 and you're more likely to have a winning bid that gets your ads displayed. To learn how to apply targets and add bid adjustments, see [How to target customers](./hlp_BA_PROC_TargetingAgeGender.md).

## Multiple bid adjustments

If more than one of your target criterion is met and your ad is clicked, you pay for each of the bid adjustments that match (but not for those that don't match). For example, let's say you have set up the following bids and targeting:

- Keyword bid = $3.00
- Target location = Chicago, Bid adjustment = Bid + 20%
- Target days = Saturday, Bid adjustment = Bid + 10%
- Target device = Tablet, Bid adjustment = Bid - 20%

Given the above data, the potential maximum amount for your bid using the new method is as follows:

<table>
  <tr>
    <th scope="col">Search user #1</th>
  </tr>
  <tr>
    <td>
      <para><strong>Targets:</strong></para>
      <ul>
        <li>Lives in Chicago (multiply by 120%)</li>
        <li>Searching on Saturday (multiply by 110%)</li>
      </ul>
      <para><strong>Max bid:</strong></para>
      <ul>
        <li>$3.00 × 1.20 × 1.10 = <strong>$3.96</strong></li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="col">Search user #2</th>
  </tr>
  <tr>
    <td>
      <para><strong>Targets:</strong></para>
      <ul>
        <li>Searching on Saturday (multiply by 110%)</li>
      </ul>
      <para><strong>Max bid:</strong></para>
      <ul>
        <li>$3.00 × 1.10 = <strong>$3.30</strong></li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="col">Search user #3</th>
  </tr>
  <tr>
    <td>
      <para><strong>Targets:</strong></para>
      <ul>
        <li>Lives in Chicago (multiply by 120%)</li>
        <li>Using a tablet device (multiply by 80%)</li>
      </ul>
      <para><strong>Max bid:</strong></para>
      <ul>
        <li>$3.00 × 1.20 × 0.80 = <strong>$2.88</strong></li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="col">Search user #4</th>
  </tr>
  <tr>
    <td>
      <para><strong>Targets:</strong></para>
      <ul>
        <li>No matches</li>
      </ul>
      <para><strong>Max bid:</strong></para>
      <ul>
        <li><strong>$3.00</strong></li>
      </ul>
    </td>
  </tr>
</table>

Some items to be aware of when using bid adjustments:

- Bid adjustments are rounded down to the nearest cent.
- Bid adjustments for most variables can range, in 1% increments, from -90% to + 900%.
- As per above, negative bid adjustments for most targets can go to -90%. However, if you are using a negative bid adjustment for a device, you can go to -100%. Using -100% for one of these devices would effectively opt you out of displaying your ads on that device.
- When you place a bid adjustment for geographical location, day of the week, or time of day, you can use targeting to choose whether to display your ads only to target customers or to all customers. When you place a bid adjustment for age or gender, your ads are displayed to all customers, but your adjusted bid can increase the likelihood of your ad being displayed to the specified gender and age segments. In all cases, you pay the adjusted bid only when one or more of the target criterion is met and your ad is clicked.
- If a customer's criterion is unknown — for example, if we don't know whether the customer is a man or a woman — then no bid adjustment for this criterion will be applied.
- By default, bid adjustments of 15% will be applied to new targeting associations. Existing associations in the ad groups will not be changed.
- If you use an automated [bid strategy](./hlp_BA_CONC_BidStrategy.md), it will be informed by any bid adjustments you set.
- [LinkedIn profile targeting](./hlp_BA_CONC_LinkedInTargeting.md) bids will multiply if a customer is included in multiple segments. For example, if you target Industry=Financial services with a bid adjustment of 10%, and also target Job function=Consulting with a bid adjustment of 20%, the resulting bid adjustment for a customer matching both targets will be 32% (1.10 x 1.20 = 1.32).

> [!NOTE]
> Want expert advice on your ads? [Schedule a no-cost session with a personal Microsoft Advertising consultant](https://go.microsoft.com/fwlink?LinkId=837456).


