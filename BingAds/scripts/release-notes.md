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


## August 7, 2018

Added support for ads.

- Added the `newAd` method to [AdGroup](reference/AdGroup.md). The method returns an [AdBuilderSpace](reference/AdBuilderSpace.md) object, which you use to get an ad builder.
  
- Added the [AdBuilderSpace](reference/AdBuilderSpace.md) object. The object contains methods for getting ad builders. For example, if you want to build an expanded text ad, you'd call the object's `expandedTextAdBuilder` method to get the [ExpandedTextAdBuilder](reference/ExpandedTextAdBuilder.md) object.

- Added the [ExpandedTextAdBuilder](reference/ExpandedTextAdBuilder.md) object, which you use to add an expanded text ad to the ad group.

- Added the [AdOperation](reference/AdOperation.md) object, which you use to determine whether Bing successfully added the ad.

- Added the [AdViewSpace](reference/AdViewSpace.md) object, which contains the methods used to cast an ad to a specific type. For example, cast the base ad object to an expanded text ad.

- Added the [AdTypeSpace](reference/AdTypeSpace.md) object, which contains the methods used to test if an ad is of the specified type. For example, to test whether the ad is an expanded text ad.

- Added the [Ad](reference/Ad.md) object, which is the base ad type.

- Added the [AdUrls](reference/AdUrls.md) object, which contains the methods for managing the ad's URLs.

- Added the [ExpandedTextAd](reference/ExpandedTextAd.md) object, which contains the ad's properties.

- Added the [AdSelector](reference/AdSelector.md) object, which you use to specify the filter criteria for selecting ads.

- Added the [AdIterator](reference/AdIterator.md) object, which you use to iterate through the filtered list of ads.




## June 15, 2018

Closed beta release. This release of Bing Ads Scripts is available to select participants only. For information about participating in the preview release program, please contact your account manager. The Scripts classes and documentation are subject to change.

This initial release includes the following capabilities:

- Core campaign management (campaigns, ad groups, keywords)
- Performance data at entity-level (campaigns, ad groups, keywords)
- Shared Negative Keyword Lists

