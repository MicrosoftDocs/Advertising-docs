---
title: About duplicate keywords
description: How punctuation can result in duplicate keywords.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# About duplicate keywords

A keyword is considered a duplicate if it is the same as another keyword, but its punctuation varies. This is called keyword normalization, a process where extraneous characters like punctuation marks and accents are removed from keywords and customer queries. Microsoft Advertising will allow you to add keywords that are duplicates after normalization, though they won’t impact your keyword coverage.

For example, let's say you type **bike-repair** as one of your keywords, and then also add  **bike repair**. Your second entry (**bike repair**) would be marked as a duplicate. When someone searches for **bike-repair**, Microsoft Advertising automatically removes the hyphen and displays ads for the search query **bike repair**, including yours, regardless of which variation you used (**bike repair** or **bike-repair**).

Below is the list of extra characters that Microsoft Advertising looks for and will ignore. If you use any of the characters below, and have a similar keyword without those characters, you can safely remove either the duplicate or original keyword. Doing so can simplify your keyword management without ever negatively impacting performance. [How to add, edit or delete keywords](./hlp_BA_PROC_AddKeywordsOrder.md)

<table type="type2" style="width:100%">
  <tr>
    <td>quotation mark (")</td>
    <td>ampersand (&amp;)</td>
    <td>hyphen (-)</td>
  </tr>
  <tr>
    <td>asterisk (*)</td>
    <td>percentage sign (%)</td>
    <td>parentheses (( ))</td>
  </tr>
  <tr>
    <td>brackets ([ ])</td>
    <td>curly brackets ({ })</td>
    <td>period (.)</td>
  </tr>
  <tr>
    <td>comma (,)</td>
    <td>question mark (?)</td>
    <td>slash mark (/)</td>
  </tr>
  <tr>
    <td>backslash (\)</td>
    <td>colon (:)</td>
    <td>semicolon (;)</td>
  </tr>
  <tr>
    <td>exclamation point (!)</td>
    <td>apostrophe ('), except for 's and 't</td>
    <td>angle brackets (&lt; &nbsp;&gt;)</td>
  </tr>
  <tr>
    <td>plus sign (+)</td>
    <td>number sign (#)</td>
    <td>equal sign (=)</td>
  </tr>
  <tr>
    <td>vertical bar (|)</td>
    <td>underline (_)</td>
    <td>tilde (~)</td>
  </tr>
  <tr>
    <td>at sign (@)</td>
    <td>dollar sign ($)</td>
    <td>caret (^)</td>
  </tr>
  <tr>
    <td>grave accent (`)</td>
    <td></td>
    <td></td>
  </tr>
</table>

While normalizing keywords helps save you time in managing your keyword lists, this approach can limit certain highly specific keywords’ performances. As such, enhanced normalization logic is incorporated into our auction process. Here are our normalization categories:

<table>
  <tr>
    <th scope="col">Normalization category</th>
    <th scope="col">Normalization process</th>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Stop words</th>
    <td>The following words will not be removed: is, a, what, the, and, at, to, of, in, or, about, for, with, on, from, by, 've (e.g. should've), an</td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Special characters</th>
    <td>Accents (é) will not be removed.</td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Apostrophes</th>
    <td>Apostrophes 's at the end of words will not be removed. Note, 't is already retained.</td>
  </tr>
</table>

&nbsp;

> [!NOTE]
> Normalization is not case sensitive; **bike repair** and **Bike Repair** are treated as the same phrase. You'll see that if you enter a keyword with a capital letter, the capital letter is simply changed to lower-case.
> It’s possible to add keywords to your ad group that after normalization are duplicates for matching purposes. While they will not negatively impact your campaign, you may see both keywords appear in your reports. If you receive a click on one of these keywords, only one of the keywords – typically the one with the highest bid – will report the click.
> Normalization does not treat  singular and plural forms of words as duplicates. For example, **bike** and **bikes** would be separate keywords.  If you want to use both the plural and singular form of a keyword, bid on each separately. Similarly, normalization does not impact spaces within or between words, or apostrophes that are a part of a name. For example, **bikerepair** is not a duplicate of **bike repair**.
> As you create your keywords, you'll need to make sure they adhere to [Microsoft Advertising policies](./hlp_BA_CONC_EditorialGuidelines.md).


