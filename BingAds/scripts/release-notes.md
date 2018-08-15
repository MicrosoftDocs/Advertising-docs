---
title: "Bing Ads Scripts release notes"
description: "Describes the changes that were included with each release."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Release Notes

For information about changes that were included with each release, see the following sections.


## September 21, 2018

Added support for shared budgets. Added the following fields to the [Budget](reference/Budget.md) object.

- campaigns &mdash; Gets a selector that returns all campaigns that share this budget.
- getEntityType &mdash; Gets the object's type.
- getId &mdash; Gets the ID that uniquely identifies the shared budget.
- getName &mdash; Gets the shared budget's name.
- getStats &mdash; Gets the performance data for the campaigns that share this budget.
- isExplicitlyShared &mdash; Gets a Boolean value that indicates whether this budget is a shared budget.

The `getId`, `getName`, and `getStats` methods return data for only shared budgets; the `getId` and `getName` methods return null for unshared (individual campaign) budgets.

Added the following field to the [BingAdsApp](reference/BingAdsApp.md) object.

- budgets &mdash; Gets all shared budgets in the account. Use the selector to filter the list of shared budgets.

Added the following objects that you use to filter and loop through a list of shared budgets. 

- [BudgetSelector](reference/BudgetSelector.md) &mdash; Contains the methods for filtering and ordering the list of shared budgets.  
  
- [BudgetIterator](reference/BudgetIterator.md) &mdash; Contains the methods for looping through the list of shared budgets. The selector's `get` method returns the iterator.

The selector returns only shared budgets, it does not include unshared (individual campaign) budgets. To determine if a campaign uses an individual budget, get the budget by calling the campaign's `getBudget` method. Then, call the budget's `isExplicitlyShared` method to determine if the budget is shared. The budget is shared if `isExplicitlyShared` returns **true**.


## September 12, 2018

Added the following methods for getting an entity's parent and child entities. 

- [AdGroup.getCampaign](reference/AdGroup.md#getcampaign) &mdash; Gets the campaign that the ad group belongs to.
- [AdGroup.keywords](reference/AdGroup.md#keywords) &mdash; Gets a selector used to filter the ad group's list of keywords.
- [AdParam.getAdGroup](reference/AdParam.md#getadgroup) &mdash; Gets the ad group that the keyword associated with this substitution parameter belongs to.
- [AdParam.getKeyword](reference/AdParam.md#getkeyword) &mdash; Gets the keyword that the substitution parameter applies to.
- [Campaign.adGroups](reference/Campaign.md#adgroups) &mdash; Gets a selector used to filter the campaign's list of ad groups.
- [Campaign.keywords](reference/Campaign.md#keywords) &mdash; Gets a selector used to filter the campaign's list of keywords.
- [Keyword.getCampaign](reference/Keyword.md#getcampaign) &mdash; Gets the campaign that the keyword belongs to.
- [Keyword.getAdGroup](reference/Keyword.md#getadgroup) &mdash; Gets the ad group that the keyword belongs to.
- [NegativeKeywordList.campaigns](reference/Campaign.md#adgroups) &mdash; Gets a selector used to filter the list of campaigns that the negative keyword list is associated with.


## September 9, 2018

Added support for ads.

- Added the `newAd` method to [AdGroup](reference/AdGroup.md). The method returns an [AdBuilderSpace](reference/AdBuilderSpace.md) object, which you use to get an ad builder.
  
- Added the [AdBuilderSpace](reference/AdBuilderSpace.md) object. The object contains methods for getting ad builders. For example, if you want to build an expanded text ad, you'd call the object's `expandedTextAdBuilder` method to get the [ExpandedTextAdBuilder](reference/ExpandedTextAdBuilder.md) object.
  
- Added the [ExpandedTextAdBuilder](reference/ExpandedTextAdBuilder.md) object, which you use to add an expanded text ad to the ad group.
  
- Added the [AdOperation](reference/AdOperation.md) object, which you use to determine whether Bing successfully added the ad.
  
- Added the [AdViewSpace](reference/AdViewSpace.md) object, which contains the methods used to cast an ad to a specific type. For example, cast the base ad object to an expanded text ad.
  
- Added the [AdTypeSpace](reference/AdTypeSpace.md) object, which contains the methods used to test whether an ad is of the specified type. For example, to test whether the ad is an expanded text ad.
  
- Added the [Ad](reference/Ad.md) object, which is the base ad type. It also defines a text ad. 
  
- Added the [AdUrls](reference/AdUrls.md) object, which contains the methods for getting the ad's URLs, tracking template, and custom parameters.
  
- Added the [ExpandedTextAd](reference/ExpandedTextAd.md) object, which defines an expanded text ad.
  
- Added the [AdSelector](reference/AdSelector.md) object, which you use to specify the filter criteria for selecting ads.
  
- Added the [AdIterator](reference/AdIterator.md) object, which you use to iterate through the filtered list of ads.
  
- Added the `ads` method to [BingAdsApp](reference/BingAdsApp.md). The method returns the [AdSelector](reference/AdSelector.md) object, which you use to specify the filter criteria for selecting ads in the account.
  
- Added the `ads` method to [AdGroup](reference/AdGroup.md). The method returns the [AdSelector](reference/AdSelector.md) object, which you use to specify the filter criteria for selecting ads in the ad group.
  
- Added the `ads` method to [Campaign](reference/Campaign.md). The method returns the [AdSelector](reference/AdSelector.md) object, which you use to specify the filter criteria for selecting ads in the campaign.


## June 15, 2018

Closed beta release. This release of Bing Ads Scripts is available to select participants only. For information about participating in the preview release program, please contact your account manager. The Scripts classes and documentation are subject to change.

This initial release includes the following capabilities:

- Core campaign management (campaigns, ad groups, keywords)
- Performance data at entity-level (campaigns, ad groups, keywords)
- Shared Negative Keyword Lists

