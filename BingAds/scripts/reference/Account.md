---
title: "Account object"
description: "Contains the methods used to get account information such as name, customer ID, and account-level performance data."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Account

Contains the methods used to get account information such as name, customer ID, and account-level performance data.


## Methods
|Method Name|Return Type|Description|
|-|-|-
[getAccountId](#getaccountid)|string|Gets this account's ID.
[getAccountNumber](#getaccountnumber)|string|Gets this account's account number.
[getCurrencyCode](#getcurrencycode)|string|Gets the currency code of the currency used by the account.
[getCustomerId](#getcustomerid)|string|Gets the customer ID of the owner that owns this account.
[getEntityType](#getentitytype)|string|Gets this entity's type.
[getName](#getname)|string|Gets this managed account's name.
[getTimeZone](#gettimezone)|string|Gets this account's time zone.

<!--
[getStats](#getstats)|[Stats](Stats.md)|Gets the performance data for this managed account.
-->

## <a name="getaccountid"></a>getAccountId
Gets this account's ID.

### Returns
|Type|Description|
|-|-
string|The ID that uniquely identifies this account.


## <a name="getaccountnumber"></a>getAccountNumber
Gets this account's account number.

### Returns
|Type|Description|
|-|-
string|The account's account number used to identify the account in the Bing Ads web application.


## <a name="getcurrencycode"></a>getCurrencyCode
Gets this account's currency code.

### Returns
|Type|Description|
|-|-
string|The currency currency that this account uses. For example, USD for United States dollar.


## <a name="getcustomerid"></a>getCustomerId
Gets the ID of the customer that owns this account.

### Returns
|Type|Description|
|-|-
string|The ID of the customer that owns this account.


## <a name="getentitytype"></a>getEntityType
Gets this entity's type.

### Returns
|Type|Description|
|-|-
string|This entity's type, which is *Account*.


## <a name="getname"></a>getName
Gets this account's name.

### Returns
|Type|Description|
|-|-
string|The name of this account.

<!--
## <a name="getstats"></a>getStats
Gets the performance data for this account. 

### Returns:
|Type|Description|
|-|-
[Stats](Stats.md)|The performance data for this account.
-->

## <a name="gettimezone"></a>getTimeZone
Gets this account's time zone.

### Returns
|Type|Description|
|-|-
string|The preferred time zone to use for campaigns in this account. For a list of time zones, see [Account time zones](../concepts/timezone-mapping.md).

