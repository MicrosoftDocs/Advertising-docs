---
title: Ad Insight Service Operations
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Service operations reference for the AdInsight service.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Ad Insight Service Operations
The Ad Insight service defines the following service operations.

|Service Operation|Description|Request Limits|
|---|---|---|
|[GetAuctionInsightData](getauctioninsightdata.md)|Reserved for future use.|Not applicable.|
|[GetBidLandscapeByAdGroupIds](getbidlandscapebyadgroupids.md)|Given a list of existing ad groups, this operation returns for each a list of suggested bids and estimated performance statistics.|1,000 *AdGroupBidLandscapeInput*|
|[GetBidLandscapeByKeywordIds](getbidlandscapebykeywordids.md)|Given a list of existing keywords, this operation returns for each a list of suggested bids and estimated performance statistics from 1 to  7 days.|1,000 *KeywordIds*|
|[GetBidOpportunities](getbidopportunities.md)|Gets the keyword bid opportunities of the specified ad group.|1 *AdGroupId*<br />1 *CampaignId*|
|[GetBudgetOpportunities](getbudgetopportunities.md)|Gets the campaign budget opportunities of the specified campaign.|1 *CampaignId*|
|[GetDomainCategories](getdomaincategories.md)|Gets the list of categories available for the website domain and language.|1 *DomainName*<br/>1 *Language*|
|[GetEstimatedBidByKeywordIds](getestimatedbidbykeywordids.md)|Gets the estimated bid value of one or more keywords - specified by keyword identifier - that could have resulted in an ad appearing in the targeted position in the search results in the last  7 days.|1,000 *KeywordIds*|
|[GetEstimatedBidByKeywords](getestimatedbidbykeywords.md)|Gets the estimated bid value of one or more keywords that could result in an ad appearing in the targeted position in the search results.|1 *AdGroupId*<br />1,000 *Keywords*|
|[GetEstimatedPositionByKeywordIds](getestimatedpositionbykeywordids.md)|Gets the estimated position in the search results if the specified bid value had been used for the keywords in the last 7 days.|1,000 *KeywordIds*|
|[GetEstimatedPositionByKeywords](getestimatedpositionbykeywords.md)|Gets the estimated position in the search results if the specified bid value would be used for the specified keywords.|1 *AdGroupId*<br />1,000 *Keywords*|
|[GetHistoricalKeywordPerformance](gethistoricalkeywordperformance.md)|Gets the historical performance of the normalized search term.|1,000 *Keywords*|
|[GetHistoricalSearchCount](gethistoricalsearchcount.md)|Gets the number of times the normalized term was used in a search during the specified time period.|1,000 *Keywords*|
|[GetKeywordCategories](getkeywordcategories.md)|Gets the keyword categories to which the specified keywords belong.|1,000 *Keywords*<br />5 *MaxCategories*|
|[GetKeywordDemographics](getkeyworddemographics.md)|Gets the age and gender of users who have searched for the specified keywords.|1,000 *Keywords*|
|[GetKeywordIdeaCategories](getkeywordideacategories.md)|Gets the list of keyword idea categories.|Not applicable|
|[GetKeywordIdeas](getkeywordideas.md)|Gets the list of keyword ideas.|Maximum 1 of each [SearchParameter](searchparameter.md) type within *SearchParameters*|
|[GetKeywordLocations](getkeywordlocations.md)|Gets the geographical locations of users who have searched for the specified keywords.|1,000 *Keywords*<br />10 *MaxLocations*|
|[GetKeywordOpportunities](getkeywordopportunities.md)|Gets a list of keyword suggestions that are relevant to the specified ad group.|1 *AdGroupId*<br />1 *CampaignId*|
|[GetKeywordTrafficEstimates](getkeywordtrafficestimates.md)|Provides traffic estimates for keywords e.g., average CPC, average position, clicks, CTR, impressions, and total cost.|N/A.|
|[SuggestKeywordsForUrl](suggestkeywordsforurl.md)|Suggests the possible keywords for the content located at the specified URL.|200 *MaxKeywords*<br />1 *Url*|
|[SuggestKeywordsFromExistingKeywords](suggestkeywordsfromexistingkeywords.md)|Suggests keywords that could perform better than the specified keywords.|1,000 *Keywords*<br />100 *MaxSuggestionsPerKeyword*|
