---
title: "MccApp object"
description: "Contains the methods used to get the list of accounts you have access to and to select the account to manage."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# MccApp

This is the top-level object that you use if you're managing accounts for others. Use it to get the list of accounts you have access to and to select the account to manage.


## Methods

|Method Name|Return Type|Description|
|-|-|-
[accounts](#accounts)|[ManagedAccountSelector](./ManagedAccountSelector.md)|Gets a [selector](../concepts/selectors.md) that returns all accounts that the user has access to.
[select(ManagedAccount account)](#select-managedaccount-account-)|void|Selects the account to manage in the script.


## <a name="accounts"></a>accounts

Gets a [selector](../concepts/selectors.md) that returns all accounts that the user has access to. 

### Returns

|Type|Description|
|-|-
[ManagedAccountSelector](./ManagedAccountSelector.md)|A selector that returns all accounts that the user has access to. Use the selector's methods to filter the list of accounts.


## <a name="select-managedaccount-account-"></a>select(ManagedAccount account)
Selects the account to manage in the script.

### Arguments
|Name|Type|Description|
|-|-|-
account|[ManagedAccount](./ManagedAccount.md)|The account to manage in the script.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

