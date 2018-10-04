---
title: "AccountsApp object"
description: "Contains the methods used to get the list of managed accounts you have access to, and to select the account to manage."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# AccountsApp

This is the top-level object that you use if you're managing accounts for others. You use this object in multi-account scripts to get the list of accounts you have access to, and to select the account to manage. After getting the managed account, use the [BingAdsApp](BingAdsApp.md) object to access its entities.

This object is available for scripts run from the Scripts editor accessed from **Accounts Summary** in the Bing Ads web application.


## Methods

|Method Name|Return Type|Description|
|-|-|-
[accounts](#accounts)|[BingAdsAccountSelector](./BingAdsAccountSelector.md)|Gets a [selector](../concepts/selectors.md) that returns all accounts that the user has access to.
[select(BingAdsAccount account)](#select-bingadsaccount-account-)|void|Selects the account to process in the script.


## <a name="accounts"></a>accounts

Gets a [selector](../concepts/selectors.md) that returns all accounts that the user has access to. 

### Returns

|Type|Description|
|-|-
[BingAdsAccountSelector](./BingAdsAccountSelector.md)|A selector that returns all accounts that the user has access to. Use the selector's methods to filter the list of accounts.


## <a name="select-bingadsaccount-account-"></a>select(BingAdsAccount account)
Selects the account to process in the script.

The following example shows how to change the current account that the script is processing with another account.

```javascript
    // Get the account that the script is currently processing.
    var oldAccount = BingAdsApp.currentAccount();

    // Get another account that the user manages.
    var newAccount = AccountsApp.accounts()
        .withIds(["123456789"])
        .get()
        .next();

    // Make the new account the current account that the script processes.
    AccountsApp.select(newAccount);

    // Do something with the new account

    // Change the current account back to the old account
    AccountsApp.select(oldAccount);
```

### Arguments
|Name|Type|Description|
|-|-|-
account|[BingAdsAccount](./BingAdsAccount.md)|The account to process in the script.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## See also

[Multi-account access](../guides/multi-account-access.md)