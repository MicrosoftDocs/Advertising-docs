---
title: Using broad match and broad match modifier
description: Learn about the broad match modifier in Microsoft Advertising Editor , how to use it with the broad match type, and how it will impact the eligibility of ads to serve.
ms.service: "bing-ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Using broad match and broad match modifier

Using the match type**broad match** for a keyword makes your ad eligible to be displayed when a search query or other input includes either the individual words in your keyword in **any** order, or words **related** to your keyword. Then, to make sure you're getting just the right search queries, you can use the broad match modifier to fine-tune or restrict how the broad match is applied. Here's [more information on broad match and other match types](./hlp_BAE_CONC_MatchOptions.md).

## How broad match can help you

So, what are the benefits of setting your search keywords to broad match?

- **Spend less time building keyword lists**. Trying to figure out seemingly endless variations of keywords is time consuming. With broad match, Microsoft Advertising does the work for you! This way, you don’t have to worry about creating keyword lists to try to cover all relevant searches.
- **Spend money on keywords that work**. Not all keyword variations will lead to clicks for your ads, so Microsoft Advertising will stop showing your ads for those specific keyword variations. Doing so will allow you to focus on the keywords that do work and not accrue click charges for keyword variations that don’t.

Here's an example of how broad match might work:

<table>
  <tr>
    <th scope="col">Broad match keyword</th>
    <th scope="col">Ads may show on searches for:</th>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Hawaii hotels</th>
    <td>Hawaii rentals  
   Honolulu Hawaii hotels  
  Hawaii Maui hotels  
  Maui hotels  
  </td>
  </tr>
</table>

Keep in mind that there will be times when different options might be more helpful. For example:

- Your quality score shows you how competitive your ads are in the marketplace. A low quality score means that your competitors’ campaigns are performing better than yours – in other words, their ads are probably showing more often and more prominently on the search results page. Broad match keywords may affect the quality score, because your keywords will appear relevant for too many searches.
- Improve your click-through rate (CTR) by using exact and phrase match. While this means that your ads will only show for the exact terms customers are searching for, having a higher CTR means that your ads are being clicked more.

## What are broad match modifiers?

Let's say you create the broad match keyword *Hawaii Hotels*. A query for **Hawaii Rentals** might also trigger your ads, since "rentals" is related to hotels. But you own a hotel and don't want traffic from searchers looking for rental properties. Your solution? Simply add the "+" **broad match modifier** to your keyword to make it *Hawaii +Hotels*. This tells Microsoft Advertising that the word **Hotels** must be in the query in order for your ads to be eligible to be served.

Here are some examples of how your ad might show:

<table>
  <tr>
    <th scope="col">Search term</th>
    <th colspan="2" style="text-align:center" scope="col">Is ad eligible?</th>
  </tr>
  <tr>
    <table_subhead_cell></table_subhead_cell>
    <table_subhead_cell style="width:200 px">Broad Match Keyword: <para>Hawaii Hotels</para></table_subhead_cell>
    <table_subhead_cell>Broad Match Modifier Keyword: <para>Hawaii +Hotels</para></table_subhead_cell>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Hawaii Hotels</th>
    <td style="text-align:center">
    ![image alt text](../images/Global_Icon_CheckMark.png)
   </td>
    <td style="text-align:center">
    ![image alt text](../images/Global_Icon_CheckMark.png)
   </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Hawaii Rentals</th>
    <td style="text-align:center">
    ![image alt text](../images/Global_Icon_CheckMark.png)
   </td>
    <td style="text-align:center">
    ![image alt text](../images/Global_Icon_Xmark.png)
   </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Maui Hotels</th>
    <td style="text-align:center">
    ![image alt text](../images/Global_Icon_CheckMark.png)
   </td>
    <td style="text-align:center">
    ![image alt text](../images/Global_Icon_CheckMark.png)
   </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Maui Rentals</th>
    <td style="text-align:center">
    ![image alt text](../images/Global_Icon_CheckMark.png)
   </td>
    <td style="text-align:center">
    ![image alt text](../images/Global_Icon_Xmark.png)
   </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Hotels Hawaii Maui</th>
    <td style="text-align:center">
    ![image alt text](../images/Global_Icon_CheckMark.png)
   </td>
    <td style="text-align:center">
    ![image alt text](../images/Global_Icon_CheckMark.png)
   </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Hotels Maui Rentals</th>
    <td style="text-align:center">
    ![image alt text](../images/Global_Icon_CheckMark.png)
   </td>
    <td style="text-align:center">
    ![image alt text](../images/Global_Icon_CheckMark.png)
   </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Rentals Hawaii Maui </th>
    <td style="text-align:center">
    ![image alt text](../images/Global_Icon_CheckMark.png)
   </td>
    <td style="text-align:center">
    ![image alt text](../images/Global_Icon_Xmark.png)
   </td>
  </tr>
</table>

For English ads in the United States, United Kingdom, Australia, and Canada, any close variations of words with the broad match modifier can also trigger your ad. Here are some examples of close variations that are included:

- **Plurals**: The keyword **luxury +resorts** will match the query **luxury resort**.
- **Stemming**: The keyword **+swim team** will match the query **swimming team**.
- **Misspellings**: The keyword **Hawaii +vacation** will match the query **Hawaii vacaton**.
- **Abbreviations and acronyms**: The keyword **Redmond +Washington** will match the query **Redmond WA**.
- **Word blending and splitting**: The keyword **+super +market** will match the query **supermarket**.
- **Equivalent expressions**: The keyword **+lodge deal near +Yosemite** will match the query **cabin in Yosemite**.
- **Accents**: The keyword **homes in +Andre** will match the query **homes in André**.

If you find that close variations to your broad match modifier are triggering your ad incorrectly, add those close variations to your negative keywords.

> [!IMPORTANT]
> Broad match modifiers only affect search ads. On the content network, broad match modifiers serve as broad match keywords.


