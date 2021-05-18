---
title: Using the broad match modifier
description: Learn about the broad match modifier, how to use it, and how it will impact the eligibility of ads to serve.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Using the broad match modifier

If you find that some of your [broad match](./hlp_BA_CONC_BroadMatch.md) keywords are matching on search terms that aren't relevant to your business, you can use the broad match modifier to fine-tune or restrict how the broad match is being applied.

## What are broad match modifiers?

Let's say you create the broad match keyword *Used 4x4 Truck*. A query for **Used 4x4 SUV** might also trigger your ads, since "SUV" is related to trucks. But you own a truck and don't want traffic from searchers looking for SUVs. The solution? Simply add the "+" **broad match modifier** to your keyword to make it *Used 4x4 + Truck*. This tells Microsoft Advertising that the word **Truck** (or one of its close variations) must be in the query in order for your ads to be eligible to be served.

Here are some examples of how your ad might show:

<table>
  <tr>
    <th scope="col">
        Search term
      </th>
    <th colspan="2" style="text-align:center" scope="col">
        Is ad eligible?</th>
  </tr>
  <tr>
    <td></td>
    <td><strong>Broad Match Keyword</strong> : <para><strong>Used 4x4 Truck</strong></para></td>
    <td><strong>Broad Match Modifier Keyword</strong> : <para><strong>Used 4x4 +Truck</strong></para></td>
  </tr>
  <tr>
    <th style="background: transparent" scope="row">
        <strong>Used 4x4 Truck</strong>
        </th>
    <td style="text-align:center">
        ![Yes](../images/Global_Icon_CheckMark.png)
      </td>
    <td style="text-align:center">
        ![Yes](../images/Global_Icon_CheckMark.png)
      </td>
  </tr>
  <tr>
    <th style="background: transparent" scope="row">
        <strong>Used 4x4 SUV</strong>
      </th>
    <td style="text-align:center">
        ![Yes](../images/Global_Icon_CheckMark.png)
      </td>
    <td style="text-align:center">
        ![No](../images/Global_Icon_Xmark.png)
      </td>
  </tr>
  <tr>
    <th style="background: transparent" scope="row">
        <strong>Previously Owned Truck</strong>
        </th>
    <td style="text-align:center">
        ![Yes](../images/Global_Icon_CheckMark.png)
      </td>
    <td style="text-align:center">
        ![Yes](../images/Global_Icon_CheckMark.png)
      </td>
  </tr>
  <tr>
    <th style="background: transparent" scope="row">
        <strong>Previously Owned SUV</strong>
      </th>
    <td style="text-align:center">
        ![Yes](../images/Global_Icon_CheckMark.png)
      </td>
    <td style="text-align:center">
        ![No](../images/Global_Icon_Xmark.png)
      </td>
  </tr>
  <tr>
    <th style="background: transparent" scope="row">
        <strong>Truck Used 4x4 Previously Owned</strong>
      </th>
    <td style="text-align:center">
        ![Yes](../images/Global_Icon_CheckMark.png)
      </td>
    <td style="text-align:center">
        ![Yes](../images/Global_Icon_CheckMark.png)
      </td>
  </tr>
  <tr>
    <th style="background: transparent" scope="row">
        <strong>Truck Previously Owned SUV</strong>
      </th>
    <td style="text-align:center">
        ![Yes](../images/Global_Icon_CheckMark.png)
      </td>
    <td style="text-align:center">
        ![Yes](../images/Global_Icon_CheckMark.png)
      </td>
  </tr>
  <tr>
    <th style="background: transparent" scope="row">
        <strong>SUV Used 4x4 Previously Owned</strong> 
      </th>
    <td style="text-align:center">
        ![Yes](../images/Global_Icon_CheckMark.png)
      </td>
    <td style="text-align:center">
        ![No](../images/Global_Icon_Xmark.png)
      </td>
  </tr>
  <tr>
    <th style="background: transparent" scope="row">
        <strong>Used 4x4 Pickup</strong>
      </th>
    <td style="text-align:center">
        ![Yes](../images/Global_Icon_CheckMark.png)
      </td>
    <td style="text-align:center">
        ![no](../images/Global_Icon_CheckMark.png)
      </td>
  </tr>
</table>

For English, French, and German ads in the United States, United Kingdom, Australia, Canada, France, Germany, and India, close variations of words with the broad match modifier can also trigger your ad. Examples of the types of close variations that are considered include:

- **Plurals** : The keyword **luxury +resorts** will match the query **luxury resort**.
- **Stemming** : The keyword **+swim team** will match the query **swimming team**.
- **Misspellings** : The keyword **Hawaii +vacation** will match the query **Hawaii vacaton**.
- **Abbreviations and acronyms** : The keyword **Redmond +Washington** will match the query **Redmond WA**.
- **Word blending and splitting** : The keyword **+super +market** will match the query **supermarket**.
- **Common spelling variations** : The keyword **community theatre** will match the query **community theater**.
- **Punctuation** : The keyword **real estate** will match the query **real-estate**.
- **Accents** : The keyword **+café** will match the query **cafe**. Accents are not considered for close variations for English ads in the United States and Canada.
- **Reordering** : The keyword **chicken teriyaki** will match **teriyaki chicken**. Reordering occurs only if it doesn't change the meaning of the query.
- **Stop/function words** : The keyword **tv schedule tonight** will match **tv schedule for tonight**. Stop/function words (for example: is, a, the, on, for, in) may be ignored if they don’t impact the intent behind a query.
- **Synonyms and paraphrases** : The keyword **glucose levels normal range** will match **normal range for blood sugar**.
- **Implied words and same search intent** : The keyword **Contoso airlines** will match **Contoso flights airlines**.

If you find that close variations to your broad match modifier are triggering your ad incorrectly, add those close variations to your [negative keywords](./hlp_BA_CONC_AboutNegativeKeywords.md).

[Learn more about your options for keyword match type](./hlp_BA_CONC_MatchOptions.md)


