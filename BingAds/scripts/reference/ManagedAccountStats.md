---
title: "ManagedAccountStats object"
description: "Contains the methods for accessing a managed account's performance data."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# ManagedAccountStats

Contains the methods for accessing a managed account's performance data.


Example usage:
```javascript
    var account = MccApp.accounts()
        .get()
        .forDateRange("LAST_WEEK")
        .next();
    var stats = account.getStats();
    var conversionRate = stats.getClickConversionRate();
    var convertedClicks = stats.getConvertedClicks();
    // etc.
```


## Methods
|Method Name|Return Type|Description|
|-|-|-
[getClickConversionRate](#getclickconversionrate)|double|Gets the conversion rate for clicks.
[getClicks](#getclicks)|long|Gets the number of clicks.
[getConvertedClicks](#getconvertedclicks)|long|Gets the number of clicks that converted.
[getCost](#getcost)|double|Gets the cost (spend) in the account's currency.
[getCtr](#getctr)|double|Gets the click through rate.
[getImpressions](#getimpressions)|long|Gets the number of impressions.


## <a name="getclickconversionrate"></a>getClickConversionRate
Gets the conversion rate for clicks.

### Returns
|Type|Description|
|-|-
double|The conversion rate for clicks, in the range 0..1.


## <a name="getclicks"></a>getClicks
Gets the number of clicks.

### Returns
|Type|Description|
|-|-
long|The number of clicks.


## <a name="getconvertedclicks"></a>getConvertedClicks
Gets the number of clicks that converted.

### Returns
|Type|Description|
|-|-
long|The number of clicks that converted.


## <a name="getcost"></a>getCost
Gets the cost (spend) in the account's currency.

### Returns
|Type|Description|
|-|-
double|The cost in the account's currency.


## <a name="getctr"></a>getCtr
Gets the click-through rate.

### Returns
|Type|Description|
|-|-
double|The click-through rate, in the range 0..1.


## <a name="getimpressions"></a>getImpressions
Gets the number of impressions.

### Returns
|Type|Description|
|-|-
long|The number of impressions.

