---
title: "ManagedAccount object"
description: "Contains the methods used to get account information such as name, customer ID, and account-level performance data."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# ManagedAccount

Contains the methods used to get account information such as name, customer ID, and account-level performance data.


## Methods
|Method Name|Return Type|Description|
|-|-|-
[getCurrencyCode](#getcurrencycode)|string|Gets the currency code of the currency used by the account.
[getCustomerId](#getcustomerid)|string|Gets the customer ID of the owner that owns this account.
[getEntityType](#getentitytype)|string|Gets this entity's type.
[getName](#getname)|string|Gets this managed account's name.
[getStats](#getstats)|[ManagedAccountStats](ManagedAccountStats.md)|Gets the performance data for this managed account.


## <a name="getcurrencycode"></a>getCurrencyCode
Gets the currency code of the currency used by the account.

### Returns
|Type|Description|
|-|-
string|The currency code of the currency used by the account. For example, USD for United States dollar.


## <a name="getcustomerid"></a>getCustomerId
Gets the customer ID of the owner that owns this account.

### Returns
|Type|Description|
|-|-
string|The customer ID of the owner that owns this account.


## <a name="getentitytype"></a>getEntityType
Gets this entity's type.

### Returns
|Type|Description|
|-|-
string|This entity's type, which is *ManagedAccount*.


## <a name="getname"></a>getName
Gets this managed account's name.

### Returns
|Type|Description|
|-|-
string|The name of this managed account.


## <a name="getstats"></a>getStats
Gets the performance data for this managed account. 

### Returns:
|Type|Description|
|-|-
[ManagedAccountStats](ManagedAccountStats.md)|The performance data for this managed account.


