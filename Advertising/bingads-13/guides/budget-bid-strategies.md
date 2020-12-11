---
title: "Budget and Bid Strategies"
ms.service: "bing-ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Setup bid and budget strategies.
---
# Budget and Bid Strategies
Before your ads can run, you need to set your campaign's budget. You'll also need to choose a bid strategy type, and optionally set keyword level match type bids. Depending on the type of campaign you are running, see the following sections for more details.

|Exact Match Bid Value|Campaign Types|
|-------------------------|--------------------------|
|[Budget Types](#budgettypes)|All|
|[Bid Strategy Types](#bidstrategytypes)|All|
|[Keyword Match Types](#keywordmatchtypes)|Search|

## <a name="budgettypes"></a>Budget Types
Your budget tells Microsoft Advertising how much you want to spend on your campaign. You can set a daily budget for each campaign and when you reach your budget, Microsoft Advertising will stop displaying your ads until the next day or month. Keep your advertising costs under control by keeping track of your budget. 

> [!WARNING]
> Your budget is a target; your actual spend might be higher or lower. Variations are caused by a number of factors, such as different traffic volumes in different days of the week, or automatic detection and refunding of fraud clicks that can give money back to a campaign within a few hours of the click. Microsoft Advertising anticipates and automatically compensates for the fluctuations, and usually keeps overspend to less than 100% above your daily limit.
> 
> Also note that Microsoft Advertising does not require your campaign budget to be higher than the ad group and keyword bids. In other words ad group and keyword bids are validated independently of the campaign budget. 

With shared budgets you can set a single daily budget that can be used by any campaign within the same account. This enables you to efficiently distribute a single daily budget across all campaigns or across a defined group of campaigns within your Microsoft Advertising account. 

> [!IMPORTANT]
> You might need to code for shared budgets in the Microsoft Advertising platform, even if you do not use shared budgets. To determine whether the campaign uses a shared budget, check the value of the [BudgetId](../campaign-management-service/campaign.md#budgetid) element (via Campaign Management service) or [Budget Id](../bulk-service/campaign.md#budgetid) field (via Bulk service).

The Bing Ads API supports the *DailyBudgetAccelerated*  and *DailyBudgetStandard* values as defined in the [BudgetLimitType](../campaign-management-service/budgetlimittype.md) value set.  

### <a name="dailyaccelerated"></a>DailyBudgetAccelerated
Show your ads for every relevant search, spending at an accelerated rate until you run out of budget for the day. When the daily budget limit is reached, your ads will stop displaying until the next calendar day.

> [!IMPORTANT]
> The accelerated budget type is deprecated for DynamicSearchAds, Shopping, and Search campaigns. There are no budget delivery changes planned at this time for Audience campaigns. Please see [Deprecating Accelerated Budget Delivery](#deprecating-accelerated-budget) for more information. 

### <a name="dailystandard"></a>DailyBudgetStandard
Show your ads evenly every day throughout the month so you don't run out of budget early in the month. If the click rate is higher than expected, the rate of spend may be slowed to ensure that the budget is available until the end of the day; however, you won't exceed the estimated monthly budget.

This is a great option if you have a limited budget and want your ads to show evenly throughout the day. This way, your ads won't show all at once in the morning, using up your limited budget early in the day. You will also be able to monitor your budget on a daily basis, making adjustments as necessary, to maximize your budget.

### <a name="deprecating-accelerated-budget"></a>Deprecating Accelerated Budget Delivery 
Prior to November 1st, 2019 the budget types for shared and unshared budgets were configurable by advertisers for all campaign types. Please note the following changes in effect as of November 1st, 2019 and additional changes in effect as of January 2020.  

As of November 1st, 2019 the budget type for shared and unshared budgets is no longer configurable by advertisers for DynamicSearchAds, Shopping, and Search campaigns. Between November 1st, 2019 and January 2020 you could continue to get and set DailyBudgetAccelerated for these campaign types, although it will not have an effect on budget delivery. For DynamicSearchAds, Shopping, and Search campaigns regardless of the budget type that you set (whether DailyBudgetAccelerated or DailyBudgetStandard), Microsoft Advertising will deliver as DailyBudgetStandard. This will help advertisers spend for optimized performance based on products/services targeted by the campaign and the availability of corresponding user searches during the day. There are no budget delivery changes planned at this time for Audience campaigns, including no changes to the original definition of DailyBudgetStandard. For Audience campaigns, DailyBudgetStandard will continue to distribute ad impressions for your campaign across the entire month, and optimizes your budget to show your ads evenly throughout each day. If a budget is shared with different campaign types, its usage and delivery will vary for each campaign type. For example, if an accelerated budget is shared with both Audience and Search campaigns, the DailyBudgetAccelerated budget type setting will remain in effect for the Audience campaign while the Search campaign budget delivery will be optimized by Microsoft Advertising as described above.

As of January 2020 the budget type for shared and unshared budgets are read-only for all DynamicSearchAds, Shopping, and Search campaigns, and any budget type value that you attempt to set will be ignored without returning an error. Previous budget settings will be migrated from accelerated to standard, and the API will only return "DailyBudgetStandard" for DynamicSearchAds, Shopping, and Search campaigns, as well as for all shared budgets. You can still use accelerated budgets with Audience campaigns. The budget type data is not migrated for Audience campaign level unshared budgets. However, the budget delivery might change as described above if the Audience campaign uses a shared budget.

### <a name="budget_rules"></a>Budget Rules
Before you can submit your ad campaign, you need to set a campaign budget amount and select a budget type. Don't worry, you can change your budget amount and budget types at any time. Changes to your budget generally take effect within an hour or so. For a high level introduction to campaign budgets, see [What are my budget options?](https://help.ads.microsoft.com/#apex/3/en/51006/1) 

If you create a campaign and specify a daily budget, the service calculates the monthly budget limit by multiplying the daily budget by the number of days in the month. The service calculates the new monthly budget at midnight (in the campaign's time zone) on the first day of each month. If the daily budget amount or calculated monthly budget amount is depleted, the campaign is paused automatically. The calculated monthly budget must be within the allowed range for the currency. For more information about minimum and maximum budgets allowed, see [Currencies](currencies.md).

If you update a campaign that specifies a daily budget on the first day of the month, the service also calculates the monthly budget limit by multiplying the daily budget by the number of days in the month. However, if you update the daily budget after the first day of the month, the service uses the following formula to calculate the monthly budget.

Monthly budget = month-to-date spend + daily budget &#42; (days remaining in the month, including today)

For example, if you change the daily budget to $10 on July 15th, and you have spent $250 of the $400 budget, the new budget will be $420, which is calculated as $250 + $10(17).

The service will use the new monthly budget for the remainder of the current month, but for subsequent months, it will calculate the monthly budget by multiplying the daily budget amount by the number of days in the month.

The service will update the monthly budget of an existing campaign by using the new formula only if you update the campaign's budget; otherwise, the monthly budget remains unchanged and is enforced.

## <a name="bidstrategytypes"></a>Bid Strategy Types
Your bid strategy setting tells Microsoft Advertising how you want to manage your bids. Whichever bid strategy you use, Microsoft Advertising will always respect your budget limit. 

> [!NOTE]
> The Microsoft Advertising web application uses the term *Bid strategy*, the Bulk API uses the *Bid Strategy Type* column for upload and download, and the Campaign Management API derives several bid strategy objects from the [BiddingScheme](../campaign-management-service/biddingscheme.md) object.

The following bid strategy types are available per campaign type. For more information see the [Let Microsoft Advertising manage your bids with bid strategies](https://help.ads.microsoft.com/#apex/3/en/56786/1) help article.

|Bid Strategy Type|Campaign Types|
|-------------------------|--------------------------|
|[EnhancedCpc](#enhancedcpc)|DynamicSearchAds<br/>Search<br/>Shopping|
|[ManualCpc](#manualcpc)|Audience<br/>DynamicSearchAds<br/>Search<br/>Shopping|
|[MaxClicks](#maxclicks)|DynamicSearchAds<br/>Search|
|[MaxConversions](#maxconversions)|DynamicSearchAds<br/>Search|
|[TargetCpa](#targetcpa)|DynamicSearchAds<br/>Search|
|[TargetRoas](#targetroas)|DynamicSearchAds<br/>Search<br/>Shopping|

When you use the Bing Ads API, the default value for Search and DynamicSearchAds campaigns is [EnhancedCpc](#enhancedcpc). The default value for most Shopping campaigns is [EnhancedCpc](#enhancedcpc); however, the only supported bid strategy type for [smart shopping campaigns](smart-shopping-campaigns.md) is MaxConversionValue. The only supported value for Audience campaigns is [ManualCpc](#manualcpc).

> [!IMPORTANT] 
> For some bid strategy types your bid and ad rotation settings are ignored and conversion tracking (via [Universal Event Tracking](universal-event-tracking.md) tag and a conversion goal) is required. For more information including supported locations, see [Let Microsoft Advertising manage your bids with bid strategies](https://help.ads.microsoft.com/#apex/3/en/56786/1). 

> [!TIP] 
> You can set your campaign's bid strategy to EnhancedCpc, MaxClicks, MaxConversions, TargetCpa, or TargetRoas and then, at any time, set an individual ad group's or keyword's bid strategy to ManualCpc.  

### <a name="enhancedcpc"></a>EnhancedCpc
With the EnhancedCpc (enhanced cost per click) bid strategy, you set your ad group and keyword bids, and Microsoft Advertising will automatically adjust your bids in real time to increase your chances for a conversion. Your bid will go higher on searches that are more likely to convert and lower on searches less likely to convert (up or down, this change will be made after we apply any bid adjustments you have set). Over the long haul, though, we will try to make sure that your average CPC is not higher than your bid. If you haven't optimized your campaign yet, Enhanced CPC should reduce your cost per conversion and increase your total conversion count while respecting your current budget.  

Differing from the MaxClicks, MaxConversions, and TargetCpa bid strategies, with the EnhancedCpc bid strategy, Microsoft Advertising will not actually change your stored ad group or keyword bid settings. You can continue to set new bids, and we will use the new values as a starting point next opportunity.

> [!NOTE]
> For search ad and dynamic search ad campaigns, the EnhancedCpc bid strategy is available to all advertisers worldwide. 
> 
> For Microsoft Shopping Campaigns, the EnhancedCpc bid strategy is available wherever Microsoft Shopping Campaigns are available.

### <a name="manualcpc"></a>ManualCpc
With the ManualCpc (manual cost per click) bid strategy, you set your ad group and keyword bids, and Microsoft Advertising uses these bids every time.  

### <a name="maxclicks"></a>MaxClicks
With the MaxClicks bid strategy, you don't need to set ad group or keyword bids. Microsoft Advertising automatically sets your bids in real time to get as many clicks as possible within your budget.

Microsoft Advertising will always respect your overall budget limit, but if you want greater control over your bids while using Maximize Clicks, you can also set a maximum CPC (cost per click). This is an optional limit you can set to make sure that Microsoft Advertising never pays more than a certain amount for each individual click.  

> [!NOTE]
> The MaxClicks bid strategy is available for Dynamic Search Ads, Search, and Shopping campaigns. 

### <a name="maxconversions"></a>MaxConversions
With the MaxConversions bid strategy, you don't need to set ad group or keyword bids. Microsoft Advertising automatically sets your bids in real time to get as many conversions as possible within your budget.

Microsoft Advertising will always respect your overall budget limit, but if you want greater control over your bids while using Maximize Conversions, you can also set a maximum CPC (cost per click). This is an optional limit you can set to make sure that Microsoft Advertising never pays more than a certain amount for each individual click.

You need to have conversion tracking (a UET tag and a conversion goal) set up (offline conversions are supported too) in order to use the Maximize Conversions bid strategy. If your campaign falls below 15 conversions over any 30-day period, Maximize Conversions will stop optimizing your bids. If this happens with regularity, we recommend switching to a different bid strategy.

> [!NOTE]
> The MaxConversions bid strategy is available for Dynamic Search Ads and Search campaigns. All of your target locations must be within Australia, Canada, France, Germany, Italy, Netherlands, Spain, Sweden, Switzerland, United Kingdom, and/or United States. 

### <a name="targetcpa"></a>TargetCpa
With the TargetCpa (cost per acquisition) bid strategy, you don't need to set ad group or keyword bids. You set your budget and your target 30-day average CPA, and Microsoft Advertising automatically sets your bids in real time to get you to this average. Some conversions may cost more than your target and some may cost less, but Microsoft Advertising will try to make sure your average cost per conversion is in line with your target.

Microsoft Advertising will always respect your overall budget limit, but if you want greater control over your bids while using Target CPA, you can also set a maximum CPC (cost per click). This is an optional limit you can set to make sure that Microsoft Advertising never pays more than a certain amount for each individual click.

You need to have conversion tracking (a UET tag and a conversion goal) set up (offline conversions are supported too) in order to use the Target CPA bid strategy. If your campaign falls below 15 conversions over any 30-day period, Target CPA will stop optimizing your bids. If this happens with regularity, we recommend switching to a different bid strategy.

> [!NOTE]
> The TargetCpa bid strategy is available for Dynamic Search Ads and Search campaigns. All of your target locations must be within Australia, Canada, France, Germany, Italy, Netherlands, Spain, Sweden, Switzerland, United Kingdom, and/or United States. 

### <a name="targetroas"></a>TargetRoas
With the TargetRoas (return on ad spend) bid strategy, you don't need to set ad group or keyword bids. You set your budget and your target 30-day average ROAS, and Microsoft Advertising automatically sets your bids in real time to get you to this average. Some conversions may cost more than your target and some may cost less, but Microsoft Advertising will try to make sure your return on ad spend is in line with your target.

Microsoft Advertising will always respect your overall budget limit, but if you want greater control over your bids while using Target ROAS, you can also set a maximum CPC (cost per click). This is an optional limit you can set to make sure that Microsoft Advertising never pays more than a certain amount for each individual click.

You need to have conversion tracking (a UET tag and a conversion goal) set up (offline conversions are supported too) in order to use the Target ROAS bid strategy. Also you must be tracking revenue and have non-zero revenue over the last 30 days. If your campaign falls below 15 conversions or has zero revenue over any 30-day period, Target ROAS will stop optimizing your bids. If this happens with regularity, we recommend switching to a different bid strategy.

> [!NOTE]
> The target ROAS bid strategy is available for Dynamic Search Ads, Search, and Shopping campaigns for customers.

## <a name="keywordmatchtypes"></a>Keyword Match Types
Match type bids help Microsoft Advertising determine how closely you want a search term or other input to match your keyword. The keyword that you bid on is compared to the user's search term in the order of *Exact*, *Phrase*, and then *Broad*.

### <a name="exactmatchtype"></a>Exact
An exact match results when all of the words in the keyword exactly match the user's search term.

If the plural form is not in your keyword list, the plural form of a keyword is also used in an exact match comparison. For example, if you specify an exact-match bid for the keyword, *car*, both *car* and *cars* will match. To prevent plural form of a keyword from matching, add the plural form to the campaign or ad group's negative keyword list.

If your keyword list does not contain the plural form of the keyword, all search results for the plural form will be included in the singular form of the keyword in the keyword performance report.

### <a name="phrasematchtype"></a>Phrase
A phrase match results when all of the words in the keyword phrase are present in the user's search term and are in the same order. For example, the keyword phrase "red flower" will match the search term "big red flower" and "red flower", but not "yellow or blue flower" or "flower red".

### <a name="broadmatchtype"></a>Broad
A broad match results when words in the keyword phrase are present in the user's search term; however, the order of the words can vary. For example, the keyword *red flower* will match the search term *red flower*, *flower is red*, and other variations. It will also match the query *red* and the query *flower*.

Broad match can also match on synonyms and other semantic variations of the queries. For example, a search term for *red carnation* might result in your ad being displayed because carnation is a type of flower.
    
Because the search engine can vary its algorithms to expand queries to find broader matches by looking for synonyms and other meanings of the queries, the outcome can sometimes result in keywords being matched to irrelevant queries.

To reduce the chance of irrelevant ads being served to users and the quality score of those ads being affected due to low CTR, you can add any irrelevant queries to your list of negative keywords. To determine the irrelevant queries, see the [Report Types](report-types.md).

You can also use the broad match modifier to require that specific terms in your keyword be present in the search term. To implement the broad match modifier, include a plus sign (+) in front of every term in the keyword that must be present in the search term. For example, if you bid on "Hawaii hotels", your ad could be served for the search queries, "Hawaii beach hotels" and "Hawaii rentals." However, if you changed the keyword to "+Hawaii +hotel", the keyword would match only "Hawaii beach hotels."

If you include the broad match modifier on a keyword that specifies a phrase or exact match-type bid, the plus sign will be treated as part of the keyword and not as a modifier.

### <a name="deliveredmatchtypes"></a>Bid and Delivered Match Types
You should set the ad group *Search Bid* that will be used as the default bid for *Exact*, *Phrase*, and *Broad* match types. You can then override the default by setting individual keyword level match types. Generally, the more precise you require the match to be, the higher conversion rates tend to be while impressions tend to decrease. Finding the right balance between conversions and impressions can help maximize the return on investment (ROI) of your campaign. If you're not sure which match type to use, we suggest starting with broad match. You can then use keyword performance reports over time to see which keywords lead to ad clicks and optimize your keyword list.
- If a majority of the keywords in the report are not related to your ad, you might want to use one of the more precise match types. 
- For keywords that you want to continue leading to clicks, add them to your keyword list with a more specific match type such as Phrase or Exact. 
- For keywords that you don't want leading to clicks, add them to your keyword list as negative keywords. For more information, see [Negative Keywords](negative-keywords.md). 

Exact match is the most restrictive and broad match is the least restrictive match type. If the keyword matches by using the more restrictive match type, it will also match using the less restrictive match types. If the exact match comparison succeeds, the exact-match bid value is used if it exists; otherwise, it gets the bid value from the first less-restrictive match type that has a bid value (set at the keyword or ad group level).

If there is not an exact match, the phrase-match type comparison is used. If there is a match, the phrase-match bid value is used if it exists; otherwise, the broad-match bid value is used (set at the keyword broad match bid or ad group level search bid). If there is not a phrase match, the broad-match type comparison is used. If there is a match, the broad-match bid value is used (set at the keyword broad match bid or ad group level search bid).

The following table shows example keyword bid values for each match type, as well as the bid value that would be used based on the delivered match type if the keyword participated in the auction. The delivered match type (exact, phrase, or broad) identifies the comparison used to match the keyword to the user's query. For example, if the keyword is "red shoes" and the user's query is "pretty red shoes," the delivered match type would be phrase. The delivered match type may differ from the match type you bid, for example if you bid on a broad match and the search term was an exact match.

|Exact Match Bid Value|Phrase Match Bid Value|Broad Match Bid Value|Delivered Match Type|Bid Value Used|
|-------------------------|--------------------------|-------------------------|------------------------|------------------|
|No bid|0.10|0.20|Exact|0.10|
|No bid|0.20|0.10|Exact|0.20|
|No bid|No bid|0.10|Exact|0.10|
|No bid|No bid|0.10|Phrase|0.10|
|0.10|0.30|0.20|Exact|0.10|
|0.10|0.30|0.20|Phrase|0.30|
|0.20|No bid|No bid|Exact|0.20|
|0.20|No bid|No bid|Phrase|None. Would not participate in auction.|

For Search and Content campaigns, take a look at the keywords you've created for your ad group. Are they all closely related? Do you want to add any others? Are you using a mix of match types? Consider using the [Ad Insight Service](../ad-insight-service/ad-insight-service-reference.md) to get ideas for additional keywords you might want to include in this ad group, and for suggested starting bids. For more information, see [Budget and Bid Opportunities](budget-bid-opportunities.md). You should create a keyword for each match type that you want to bid on. For example, to bid on exact-match and phrase-match for the keyword *car*, you must create two Keyword objects. Keep in mind that you cannot change a keyword's match type from one match-type bid to another match-type bid. For example, you cannot update a keyword from exact match to phrase match. Instead, you must add a new keyword that specifies a bid amount for the new match type. Optionally you may delete the original keyword if you do not want to bid on its match type.

You can also use negative keywords to prevent you ads from being served if the user's search query contains one of your negative keywords. For more information about negative keywords, see [Negative Keywords](negative-keywords.md).

### <a name="normalization"></a>Keyword Normalization
A keyword is considered a duplicate if it is the same as another keyword, but its punctuation varies. This is called keyword normalization, a process where extraneous characters like punctuation marks and accents are removed from keywords and customer queries. Keywords are normalized when you add them to an ad group to avoid duplicates of keywords that normalize into the same form. Microsoft Advertising flags duplicate keywords so you can remove them. Removing the duplicate keywords will save you time while still giving you thorough keyword coverage. If one of your keywords is marked as a duplicate, there is no reason to manage both of them. You can remove either the duplicate or the original keyword without impacting your campaign.

For example, let's say you add *bike-repair* as one of your keywords, and then also add *bike repair*. Your second entry (bike repair) would be marked as a duplicate. When someone searches for *bike-repair*, Microsoft Advertising automatically removes the hyphen and displays ads for the search query bike repair, including yours, regardless of which variation you used (*bike repair* or *bike-repair*).

For a detailed list of normalized characters, see the Microsoft Advertising help topic [About duplicate keywords](https://help.ads.microsoft.com/#apex/3/en/normalization).

Please also note the following validation rules.
- Normalization is not case sensitive; *bike repair* and *Bike Repair* are treated as the same phrase. You'll see that if you enter a keyword with a capital letter, the capital letter is simply changed to lower-case. 
- Normalization does not treat singular and plural forms of words as duplicates. For example, *bike* and *bikes* would be separate keywords. If you want to use both the plural and singular form of a keyword, bid on each separately. Similarly, normalization does not impact spaces within or between words, or apostrophes that are a part of a name. For example, *bikerepair* is not a duplicate of *bike repair*. 
- As you create your keywords, also be aware of the rules they must follow. Here's some more information: [Microsoft Advertising policies](https://help.ads.microsoft.com/#apex/3/en/52023/1). 

## See Also
[Bing Ads API Web Service Addresses](web-service-addresses.md)

