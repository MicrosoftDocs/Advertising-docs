---
title: "Stats object"
description: "Contains the methods for accessing the entity's performance data."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Stats

Contains the methods for accessing an entity's performance data.


Example usage:
```javascript
    var campaign = BingAdsApp.campaigns().get().next();
    var stats = campaign.getStats("LAST_WEEK");
    var conversionRate = stats.getClickConversionRate();
    var convertedClicks = stats.getConvertedClicks();
    // etc.
```

## Methods
|Method Name|Return Type|Description|
|-|-|-
[getAverageCpc](#getaveragecpc)|double|Gets the average cost per click.
[getAverageCpm](#getaveragecpm)|double|Gets the average cost per thousand impressions.
[getAveragePosition](#getaverageposition)|double|Gets the average position.
[getClickConversionRate](#getclickconversionrate)|double|Gets the conversion rate for clicks.
[getClicks](#getclicks)|long|Gets the number of clicks.
[getConvertedClicks](#getconvertedclicks)|long|Gets the number of clicks that converted.
[getCost](#getcost)|double|Gets the cost (spend) in the account's currency.
[getCtr](#getctr)|double|Gets the click through rate.
[getImpressions](#getimpressions)|long|Gets the number of impressions.

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
double|The average cost per thousand impressions.

## <a name="getaverageposition"></a>getAveragePosition
Gets the average position where ads were placed.

### Returns
|Type|Description|
|-|-
double|The average position where ads were placed.

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
Gets the click through rate.

### Returns
|Type|Description|
|-|-
double|The click through rate, in the range 0..1.

## <a name="getimpressions"></a>getImpressions
Gets the number of impressions.

### Returns
|Type|Description|
|-|-
long|The number of impressions.

