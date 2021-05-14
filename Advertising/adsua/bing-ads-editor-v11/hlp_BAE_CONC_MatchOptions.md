---
title: What are keyword match types, and how do I use them?
description: Broad, phrase, exact.... Get help figuring out which ones are available in Microsoft Advertising Editor and which ones are right for your campaigns and ad groups.
ms.service: "bing-ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# What are keyword match types, and how do I use them?

> [!IMPORTANT]
> Plurals and other close variations are considered an exact match or phrase match for English ads in the United States, United Kingdom, Australia, and Canada. For more details, see the Exact match information below.

Keyword match types help Microsoft Advertising determine how closely a search query or other input must **match** your keyword. Generally, the more precise you require the match to be, the higher conversion rates tend to be while impressions tend to decrease. Finding the right balance between conversions and impressions can help maximize the ROI of your campaign.

Here's an introduction to the different available match types:

<table>
  <tr>
    <th scope="col">Match Type</th>
    <th scope="col">Ad Distribution</th>
    <th scope="col">Syntax</th>
    <th scope="col">What Triggers Your Ad</th>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Broad match</th>
    <td>Search network</td>
    <td>
    <strong>keyword</strong>
   </td>
    <td>Search queries that contain the words in your keyword or close variations of your keyword.
    <para>Example: if your keyword is <strong>red flower</strong>, related searches like <strong>red flower</strong>, <strong>crimson poppies</strong>, and <strong>buy crimson flower</strong> might trigger your ad.</para><para>
      For more information, [learn about the power of the broad match modifier](./hlp_BAE_CONC_BroadMatchModifier.md).
     </para></td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Broad match modifier</th>
    <td>Search network</td>
    <td>
    <strong>+</strong><strong>keyword</strong>
   </td>
    <td>
    Search queries that contain the word with the broad match modifier ("+") or words with any close variations. 
    <para>
    Example: If your keyword is <strong>+red flower</strong>, searches for <strong>red flower</strong> and <strong>red rose</strong> will trigger your ad, but <strong>yellow flower</strong> won't.
   </para><para>For English ads in the United States, United Kingdom, Australia, and Canada, close variants and equivalent expressions (when, for example, the keyword <strong>+lodge deal near +Yosemite</strong> will match the query <strong>cabin in Yosemite</strong>) of words with the broad match modifier can also trigger your ad (see below for close variations). </para><para>
     If you find that close variations to your broad match modifier are triggering your ad incorrectly, add those close variations to your negative keywords.</para><para>
      For more information, [learn about the power of the broad match modifier](./hlp_BAE_CONC_BroadMatchModifier.md).
     </para></td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Phrase match</th>
    <td>Search network</td>
    <td>
    <strong>"</strong><strong>keyword</strong>
    <strong>"</strong>
   </td>
    <td>Search queries that contain all words in your keyword, in the same order - even if other words are present in that query.
    <para>Example: if your keyword is <strong>"red flower"</strong>, searches for <strong>big red flower</strong> and <strong>red flower dresses</strong> will trigger your ad, but <strong>yellow flower</strong> and <strong>red aromatic flower</strong> won't.</para></td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Exact match</th>
    <td>Search network</td>
    <td>
    <strong>[</strong><strong>keyword</strong>
    <strong>]</strong>
   </td>
    <td>Search queries that contain all words in your keyword.
    <para>Example: if your keyword is <strong>[red flower]</strong>, only searches for <strong>red flower</strong> will trigger your ad.</para></td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Negative match</th>
    <td>Search network</td>
    <td>
    
     <strong>[</strong><strong>keyword</strong><strong>]</strong>
   
     or 
    
     <strong>"</strong> <strong>keyword</strong><strong>"</strong>
   
   </td>
    <td>Search queries that do <strong>not</strong> match the word or phrase in your negative keyword.
    <para>
     Example: if your negative keyword is <strong>"red"</strong>, searches for <strong>red flower</strong> won't trigger your ad, but <strong>flower</strong> will. Negative keywords can be exact or phrase matches.
    </para><para>[Learn more about using negative keywords to get to the right customers](./hlp_BAE_CONC_AboutNegativeKeywords.md).</para></td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Content match</th>
    <td>Content network</td>
    <td>
    <strong>(</strong><strong>keyword</strong>
    <strong>)</strong>
   </td>
    <td>Search queries that contain any word in your keyword, ad title, or ad text, in any order, must match input from Windows apps that are part of the content network.
    <para>Example: if your keyword is <strong>red flower</strong> and a page on a website requests ads containing the word <strong>flower</strong>, your ad will be triggered.</para><para>
     <strong>Note</strong>: Devliery for content match only occurs in the United States on mobile apps and on Windows Media properties.
    </para></td>
  </tr>
</table>

> [!IMPORTANT]
> After June 30, 2017, Microsoft Advertising will stop serving ads on the content network. [Learn more](https://go.microsoft.com/fwlink?LinkId=853053)

## Close keyword variations

To maximize for English ads in the United States, United Kingdom, Australia, and Canada, minor variations, such as plurals, abbreviations, acronyms, spacing, and misspelling are also considered a **broad match**, **broad match modifier**, **phrase match**, and **exact match**. Here are some examples of close variants that are included:

- **Plurals**: The keyword **luxury +resorts** will match the query **luxury resort**.
- **Stemming**: The keyword **+swim team** will match the query **swimming team**.
- **Misspellings**: The keyword **Hawaii +vacation** will match the query **Hawaii vacaton**.
- **Abbreviations and acronyms**: The keyword **Redmond +Washington** will match the query **Redmond WA**.
- **Word blending and splitting**: The keyword **+super +market** will match the query **supermarket**.
- **Common spelling variations**: The keywords **community theatre** will match the query **community theater**.
- **Punctuation**: The keyword **real estate** will match the query **real-estate**.

To learn more, see [understanding where your ads will appear](https://go.microsoft.com/fwlink?LinkId=398369).

## Choosing the right match type

If you're not sure which match type to use, we suggest starting with broad match. You can then use keyword performance reports over time to see which keywords trigger your ad and optimize your keyword list.

- If a majority of the keywords in the report are not related to your ad, you might want to use one of the more precise match types.
- For keywords that you specifically want to continue triggering your ad, add them to your keyword list with a more specific match type (such as phrase or exact).
- For keywords that you don't want triggering your ad, add them to your keyword list as negative keywords.

## Which match type is used?

If you bid on multiple keywords with similar text but different match types, the most restrictive match type will take precedence when your ad is displayed. The order of precedence is:

(MOST RESTRICTIVE)

- Exact match
- Phrase match
- Broad match modifier
- Broad match

(LEAST RESTRICTIVE)

For example, if you bid on both the exact match keyword **[red flower]** and the broad match keyword **flower**, a search on **red flower** will trigger the exact match and not the broad match.

Clicks on the ad will be charged your exact match bid. Also, to avoid duplicate reporting, all reports, such as keyword performance reports, will report only the match type that took precedence. In this example, an impression would be reported for the exact match **[red flower]** and **not** the broad match **flower**.


