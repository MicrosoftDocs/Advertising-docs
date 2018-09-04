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


## September 15, 2018

Added the following objects and methods to support managed accounts.

- Added the `currentAccount` method to [BingAdsApp](reference/BingAdsApp.md). Use this method to get the [Account](reference/Account.md) object, which contains information about the current account that the script is processing.  
  
- Added the [MccApp](reference/MccApp.md) object. This is the top-level object that you use if you're managing accounts for others. Use it to get the list of accounts you have access to and to select the account to manage.  
  
- Added the [ManagedAccount](reference/ManagedAccount.md) object. Use it to get account information such as name, customer ID, and account-level performance data.
  
- Added the [ManagedAccountIterator](reference/ManagedAccountIterator.md) object. Use it to iterate through the list of managed accounts that you selected.
  
- Added the [ManagedAccountSelector](reference/ManagedAccountSelector.md) object. Use it to select the the list of managed accounts that you want to get.
  
- Added the [ManagedAccountStats](reference/ManagedAccountStats.md) object. Use it to access the managed account's performance data.  
  
- Added the [ExecutionResult](reference/ExecutionResult.md) object. Use it to get the results and return value of the function you specify in the `executeInParallel` selector method (see [ManagedAccountSelector](reference/ManagedAccountSelector.md)). 





## June 15, 2018

Closed beta release. This release of Bing Ads Scripts is available to select participants only. For information about participating in the preview release program, please contact your account manager. The Scripts classes and documentation are subject to change.
