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


## Octoboer 2, 2018

Added the following objects and methods to support multi-accounts.

- Added the `currentAccount` method to [BingAdsApp](reference/BingAdsApp.md). Use this method to get the [Account](reference/Account.md) object, which contains information about the account that the script is currently processing.  
  
- Added the [AccountsApp](reference/AccountsApp.md) object. This is the top-level object that you use if you're managing accounts for others. Use it to get the list of accounts you have access to and to select the account to manage.  
  
- Added the [BingAdsAccount](reference/BingAdsAccount.md) object. Use it to get account information for a managed account such as name, customer ID, and account-level performance data.
  
- Added the [BingAdsAccountIterator](reference/BingAdsAccountIterator.md) object. Use it to iterate through the list of managed accounts that you selected.
  
- Added the [BingAdsAccountSelector](reference/BingAdsAccountSelector.md) object. Use it to select the the list of managed accounts that you want to get.
  
- Added the [BingAdsAccountStats](reference/BingAdsAccountStats.md) object. Use it to access the managed account's performance data.  
  
- Added the [ExecutionResult](reference/ExecutionResult.md) object. Use it to get the results and return value of the function you specify in the `executeInParallel` selector method (see [BingAdsAccountSelector](reference/BingAdsAccountSelector.md)). 


## October 1, 2018

Added the following method to the [Keyword](reference/Keyword.md) object.

- [getQualityScore](reference/Keyword.md#getqualityscore) &mdash; Gets the keyword's quality score. The score is in the range 1 through 10 (highest). The score shows you how competitive your ads are in the marketplace by measuring how relevant your keywords and landing pages are to customers' search terms. 


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

