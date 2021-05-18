---
title: What are keyword match types, and how do I use them?
description: Broad, phrase, exact.... Get help figuring out which ones are available in Microsoft Advertising and which ones are right for your campaigns and ad groups.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# What are keyword match types, and how do I use them?

![Match Types](../images/BA_Conc_MatchTypesIcons.svg)
Keyword match types help Microsoft Advertising determine how closely a search query or other input must **match** your keyword. Generally, the more precise your match type, the higher your click-through and conversion rates, and the lower your impression volume, tend to be. Finding the right balance between conversions and impressions can help maximize the ROI of your campaign.

## Keyword match type options
<table>
  <tr>
    <th scope="col">Broad match</th>
  </tr>
  <tr>
    <td>
      <para><strong>Syntax</strong> : <strong>keyword</strong></para>
      <para><strong>What it does</strong> : Broad match triggers the display of your ad when a user searches either the individual words in your keyword in <strong>any</strong> order, or words <strong>related</strong> to your keyword.</para>
      <para><strong>Why use it</strong> : Use broad match when you want to sell a wide set of products to a large group of customers. </para>
      <para><strong>Examples</strong> :
			  <table><tr><th scope="col">Broad match keyword</th><th scope="col">Trigger search terms</th></tr><tr><th scope="row" style="background: transparent">
          <strong>winter vacations</strong> 
        </th><td>winter vacation 
				vacations winter 
				tropical winter vacations 
				winter ski vacation 
				ski trips			
			</td></tr><tr><th scope="row" style="background: transparent">
          <strong>red flower</strong> </th><td>crimson poppies 
				buy crimson flower 
				red roses			
			</td></tr></table></para>
      <para><strong>Get more info</strong> : [About broad match](./hlp_BA_CONC_BroadMatch.md)</para>
    </td>
  </tr>
  <tr>
    <th scope="col">Broad match modifier</th>
  </tr>
  <tr>
    <td>
      <para><strong>Syntax</strong> : <strong>+keyword</strong></para>
      <para><strong>What it does</strong> : The broad match modifier makes it so that, in order to trigger your ads, specific words (or close variants) must be present in the search query.</para>
      <para><strong>Why use it</strong> : Use the broad match modifier if you feel that queries containing  terms <strong>related</strong> to your keyword are less likely to result in clicks or conversions.
		</para>
      <para><strong>Examples</strong> : Let's say you create the broad match keyword *Hawaii Hotels*. A query for <strong>Hawaii Rentals</strong> might also trigger your ads, since "rentals" is related to hotels. But you own a hotel and don't want traffic from searchers looking for rental properties.
			  <table><tr><th scope="col">Search term</th><th colspan="2" style="text-align:center" scope="col">Is ad eligible?</th></tr><tr><td></td><td><strong>Broad Match Keyword</strong> : <para><strong>Hawaii Hotels</strong></para></td><td><strong>Broad Match Modifier Keyword</strong> : <para><strong>Hawaii +Hotels</strong></para></td></tr><tr><th scope="row" style="background: transparent"><strong>Hawaii Hotels</strong></th><td style="text-align:center">
					![Yes](../images/Global_Icon_CheckMark.png)
				  </td><td style="text-align:center">
					![Yes](../images/Global_Icon_CheckMark.png)
				  </td></tr><tr><th scope="row" style="background: transparent"><strong>Hawaii Rentals</strong></th><td style="text-align:center">
					![Yes](../images/Global_Icon_CheckMark.png)
				  </td><td style="text-align:center">
					![No](../images/Global_Icon_Xmark.png)
				  </td></tr><tr><th scope="row" style="background: transparent"><strong>Maui Hotels</strong></th><td style="text-align:center">
					![Yes](../images/Global_Icon_CheckMark.png)
				  </td><td style="text-align:center">
					![Yes](../images/Global_Icon_CheckMark.png)
				  </td></tr><tr><th scope="row" style="background: transparent"><strong>Maui Rentals</strong></th><td style="text-align:center">
					![Yes](../images/Global_Icon_CheckMark.png)
				  </td><td style="text-align:center">
					![No](../images/Global_Icon_Xmark.png)
				  </td></tr><tr><th scope="row" style="background: transparent"><strong>Hotels Hawaii Maui</strong></th><td style="text-align:center">
					![Yes](../images/Global_Icon_CheckMark.png)
				  </td><td style="text-align:center">
					![Yes](../images/Global_Icon_CheckMark.png)
				  </td></tr><tr><th scope="row" style="background: transparent"><strong>Hotels Maui Rentals</strong></th><td style="text-align:center">
					![Yes](../images/Global_Icon_CheckMark.png)
				  </td><td style="text-align:center">
					![Yes](../images/Global_Icon_CheckMark.png)
				  </td></tr><tr><th scope="row" style="background: transparent"><strong>Rentals Hawaii Maui</strong> </th><td style="text-align:center">
					![Yes](../images/Global_Icon_CheckMark.png)
				  </td><td style="text-align:center">
					![No](../images/Global_Icon_Xmark.png)
				  </td></tr></table></para>
      <para><strong>Get more info</strong> : [Using the broad match modifier](./hlp_BA_CONC_BroadMatchModifier.md)</para>
    </td>
  </tr>
  <tr>
    <th scope="col">Phrase match</th>
  </tr>
  <tr>
    <td>
      <para><strong>Syntax</strong> : <strong>"keyword"</strong></para>
      <para><strong>What it does</strong> : Phrase match triggers your ad when all of the words in your keyword, or close variants, match words in a user's search query even if other words are present in that query. The words can be present in the search query in exactly the same order or re-ordered if the intent of the search query matches that of your keyword. </para>
      <para><strong>Why use it</strong> : Phrase match can increase the relevance of the matching queries compared to broad match. </para>
      <para><strong>Examples</strong> :
			  <table><tr><th scope="col">Phrase match keyword</th><th scope="col">Trigger search terms</th></tr><tr><th scope="row" style="background: transparent"><strong>winter vacations</strong> </th><td>ski winter vacations 
				ski vacations winter 
				winter vacations discount 
				Lake Tahoe winter vacations deals			
			</td></tr></table></para>
    </td>
  </tr>
  <tr>
    <th scope="col">Exact match</th>
  </tr>
  <tr>
    <td>
      <para><strong>Syntax</strong> : <strong>[keyword]</strong></para>
      <para><strong>What it does</strong> : Exact match triggers your ad when the exact words in your keyword appear in a customer's search query. Exact match can also match to search queries that are minor variations of the keyword. These are considered close variations. Close variant search queries can include singulars, plurals, abbreviations, misspellings, punctuations, accents, stemming, reordered words, synonyms, paraphrases, implied words, and same search intent. </para>
      <para><strong>Why use it</strong> : Choose exact match when you want to pair your ads and landing pages to a very targeted set of customers. </para>
      <para><strong>Examples</strong> :
			  <table><tr><th scope="col">Exact match keyword</th><th scope="col">Trigger search terms</th></tr><tr><th scope="row" style="background: transparent"><strong>winter vacations</strong> </th><td>winter vacations 
				winter vacation 
				vacations winter			
			</td></tr></table></para>
    </td>
  </tr>
  <tr>
    <th scope="col">Negative keywords</th>
  </tr>
  <tr>
    <td>
      <para><strong>Syntax</strong> : <strong>[keyword]</strong> or <strong>"keyword"</strong></para>
      <para><strong>What it does</strong> : Negative keywords define search queries that should <strong>not</strong> trigger your ad. Negative keywords can be exact or phrase matches.</para>
      <para><strong>Why use it</strong> : Negative keywords let you specify words that you want to ignore.</para>
      <para><strong>Examples</strong> : Let's say you have a broad match bid <strong>wide shoes</strong>, and you have a negative keyword with either exact match <strong>[womens shoes]</strong> or phrase match <strong>"womens shoes"</strong>.
		  <table><tr><th scope="col">Search term</th><th colspan="2" style="text-align:center">Is ad eligible?</th></tr><tr><td></td><td><strong>Negative EXACT</strong> </td><td><strong>Negative PHRASE</strong> </td></tr><tr><th scope="row" style="background: transparent">mens wide shoes</th><td style="text-align:center">
				![Yes](../images/Global_Icon_CheckMark.png)
			  </td><td style="text-align:center">
				![Yes](../images/Global_Icon_CheckMark.png)
			  </td></tr><tr><th scope="row" style="background: transparent">womens wide shoes</th><td style="text-align:center">
				![Yes](../images/Global_Icon_CheckMark.png)
			  </td><td style="text-align:center">
				![Yes](../images/Global_Icon_CheckMark.png)
			  </td></tr><tr><th scope="row" style="background: transparent">womens shoes</th><td style="text-align:center">
				![No](../images/Global_Icon_Xmark.png)
			  </td><td style="text-align:center">
				![No](../images/Global_Icon_Xmark.png)
			  </td></tr><tr><th scope="row" style="background: transparent">wide womens shoes</th><td style="text-align:center">
				![Yes](../images/Global_Icon_CheckMark.png)
			  </td><td style="text-align:center">
				![No](../images/Global_Icon_Xmark.png)
			  </td></tr></table></para>
      <para><strong>Get more info</strong> : [Learn about using negative keywords to get to the right customers](./hlp_BA_CONC_AboutNegativeKeywords.md)</para>
    </td>
  </tr>
</table>

## Close keyword variations
For exact match and phrase match keywords, your ad may also show on queries that match minor variations of the keyword, so you can maximize relevant matches without having to add all of these variations yourself. Close variations are also considered for broad match modifier keywords. Close variation matching takes place in the United States, United Kingdom, Australia, Canada, France, Germany, Italy, Netherlands, Spain, Sweden, and Switzerland.

Examples of the types of close variations that are considered include:

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

## Choosing the right match type
If you're not sure which match type to use, we suggest starting with broad match. This will give you the best chance of reaching your target customers right off the bat. You can then [run a search term report](./hlp_BA_CONC_AboutSearchQueryReport.md) and use the results to refine your keyword list. Here are some quick tips on how to optimize your keyword lists:

- If a majority of the search terms in the report are not related to your ad, you might want to consider switching the relevant keyword to one of the more specific match types.
- For search terms that you want triggering your ad more often, add them to your keyword list with a more specific match type (such as phrase or exact).
- For keywords that you don't want triggering your ad, add them to your keyword list as negative keywords.

Some other best practices to keep in mind are:

- When you select a keyword match type, consider your advertising goals, as well as the audience you are targeting.
- Cross-reference your keywords with your bids and budgets.
- Always [run a search term report](./hlp_BA_CONC_AboutSearchQueryReport.md) to make sure you are covering the queries you want.

## Which match type is used?
If you bid on the same keyword on exact and broad match, exact match will take precedence when your ad is 	displayed. For example, if you bid on both the exact match keyword [red flower] and the broad match keywords **red flower** or **flower**, a search on **red flower** will trigger the exact match and not the broad match. Additionally, exact match is preferred over exact match close variants.

To avoid duplicate reporting, all reports, such as keyword performance reports, will only report the match type that took precedence. In this example, an impression would be reported for the exact match **[red flower]** and **not** the broad match **flower**.

## How bids are inherited from one match type to another
Match types are on a spectrum from least restrictive (broad match) to most restrictive (exact match), in this order: **Broad match &gt; Broad match modifier &gt; Phrase match &gt; Exact match** .

If you do not specify bids for all match types, bids are inherited from less restrictive match types. So, while bidding on broad match is convenient and easy to manage, bidding on each match type independently gives you greater control and allows performance data to be broken out by match type.

In the absence of a bid, the next less restrictive bid is inherited by the match type without a bid. This means exact match inherits the phrase match bid, and the phrase match inherits the broad match bid. If neither exact match nor phrase match bids are specified, then both match types inherit the broad match bid. This is never reversed: Exact match bids are never applied to a phrase match, and phrase match bids are never applied to a broad match.

> [!NOTE]
> Are you a new advertiser? Would you like some [free Microsoft Advertising coaching](https://go.microsoft.com/fwlink?LinkId=398320)?


