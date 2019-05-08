---
title: "Stats object"
description: "Contains the methods for accessing the entity's performance data."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Stats

Contains the methods for accessing an entity's performance data.


Example usage:
```javascript
    var campaign = AdsApp.campaigns()
        .forDateRange("LAST_WEEK")
        .get()
        .next();
    var stats = campaign.getStats();
    var conversionRate = stats.getConversionRate();
    var convertedClicks = stats.getConversions();
    // etc.
```

## Methods
|Method Name|Return Type|Description|
|-|-|-
[getAverageCpc](#getaveragecpc)|double|Gets the average cost per click.
[getAverageCpm](#getaveragecpm)|double|Gets the average cost per thousand impressions.
[getAveragePosition](#getaverageposition)|double|Gets the average position.
[getClickConversionRate](#getclickconversionrate)|double|(Use the **getConverionRate**() method instead.)
[getClicks](#getclicks)|long|Gets the number of clicks.
[getConversionRate](#getconversionrate)|double|Gets the conversion rate for clicks.
[getConversions](#getconversions)|long|Gets the number of clicks that converted.
[getConvertedClicks](#getconvertedclicks)|long|(Use the **getConverions**() method instead.)
[getCost](#getcost)|double|Gets the cost (spend) in the account's currency.
[getCtr](#getctr)|double|Gets the click through rate.
[getImpressions](#getimpressions)|long|Gets the number of impressions.
[getReturnOnAdSpend](#getreturnonadspend)|long|Gets the return on ad spend.
[getRevenue](#getrevenue)|long|Gets the advertiser-reported revenue.



## <a name="getaveragecpc"></a>getAverageCpc
Gets the average cost per click.

### Returns
|Type|Description|
|-|-
double|The average cost per click.


## <a name="getaveragecpm"></a>getAverageCpm
Gets the average cost per thousand impressions.

### Returns
|Type|Description|
|-|-
double|The average cost per one-thousand impressions.


## <a name="getaverageposition"></a>getAveragePosition
Gets the average position where ads were placed.

### Returns
|Type|Description|
|-|-
double|The average position where ads were placed.


## <a name="getclickconversionrate"></a>getClickConversionRate
Gets the conversion rate for clicks.

> [!NOTE]
> Because this method may be deprecated in a future release, use the [getConversionRate](#getconversionrate) method instead.

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


## <a name="getconversionrate"></a>getConversionRate
Gets the conversion rate for clicks.

### Returns
|Type|Description|
|-|-
double|The conversion rate for clicks, in the range 0..1.


## <a name="getconversions"></a>getConversions
Gets the number of clicks that were converted.

### Returns
|Type|Description|
|-|-
long|The number of clicks that were converted.


## <a name="getconvertedclicks"></a>getConvertedClicks
Gets the number of clicks that converted.

> [!NOTE]
> Because this method may be deprecated in a future release, use the [getConversions](#getconversions) method instead.

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


## <a name="getreturnonadspend"></a>getReturnOnAdSpend
Gets the return on ad spend.

### Returns
|Type|Description|
|-|-
double|The return on ad spend, which is calculated as (revenue / spend) * 100.


## <a name="getrevenue"></a>getRevenue
Gets the advertiser-reported revenue.

### Returns
|Type|Description|
|-|-
double|The revenue reported by the advertiser.
