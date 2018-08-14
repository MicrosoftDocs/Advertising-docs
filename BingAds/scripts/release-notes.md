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


## August 17, 2018

Added support for shared budgets. Added the following fields to the [Budget](reference/Budget.md) object.

- getEntityType &mdash; Gets the object's type.
- getId &mdash; Gets the ID that uniquely identifies the shared budget.
- getName &mdash; Gets the shared budget's name.
- getStats &mdash; Gets the performance data for the campaigns that share this budget.
- isExplicitlyShared &mdash; Gets a Boolean value that indicates whether this budget is a shared budget.

The `getId`, `getName`, and `getStats` methods return data for only shared budgets; these methods return null for unshared (individual campaign) budgets.

Added the following field to the [BingAdsApp](reference/BingAdsApp.md) object.

- budgets &mdash; Gets all shared budgets in the account. Use the selector to filter the list of shared budgets.

Added the following objects used to filter and loop through a list of shared budgets. 

- [BudgetSelector](reference/BudgetSelector.md) &mdash; Contains the methods for filtering and ordering the list of shared budgets that you want to get.
- [BudgetIterator](reference/BudgetIterator.md) &mdash; Contains the methods for looping through the list of shared budgets. The selector's `get` method returns the iterator.

The selector returns only shared budgets, it does not include unshared (individual campaign) budgets. To determine if a campaign uses an individual budget, first get the budget by calling the campaign's `getBudget` method. Then, call the budget's `isExplicitlyShared` method to determine if the budget is shared.

## June 15, 2018

Closed beta release. This release of Bing Ads Scripts is available to select participants only. For information about participating in the preview release program, please contact your account manager. The Scripts classes and documentation are subject to change.
