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

Contains the methods for accessing the entity's performance data.


Example usage:
```javascript
 var campaign = BingAdsApp.campaigns().get().next();
 var stats = campaign.getStats("LAST_MONTH");
 var impressions = stats.getImpressions();
 var clicks = stats.getClicks();
 // etc.
```

## Methods
|Method Name|Return Type|Description|
|-|-|-
[getAverageCpc](#getaveragecpc)|double|Returns the average cost per click.
[getAverageCpm](#getaveragecpm)|double|Returns the average cost per thousand impressions.
[getAveragePosition](#getaverageposition)|double|Returns the average position.
[getClickConversionRate](#getclickconversionrate)|double|Returns the conversion rate for clicks within the range 0..1.
[getClicks](#getclicks)|long|Returns the number of clicks.
[getConvertedClicks](#getconvertedclicks)|long|Returns the number of clicks that converted.
[getCost](#getcost)|double|Returns the cost (spend) in the currency of the current account.
[getCtr](#getctr)|double|Returns the click through rate in the range 0..1.
[getImpressions](#getimpressions)|long|Returns the number of impressions.

## <a name="getaveragecpc"></a>getAverageCpc
Returns the average cost per click.

### Returns
|Type|Description|
|-|-
double|The average cost per click.

## <a name="getaveragecpm"></a>getAverageCpm
Returns the average cost per thousand impressions.

### Returns
|Type|Description|
|-|-
double|The average cost per thousand impressions.

## <a name="getaverageposition"></a>getAveragePosition
Returns the average position ads were placed.

### Returns
|Type|Description|
|-|-
double|The average position ads were placed.

## <a name="getclickconversionrate"></a>getClickConversionRate
Returns the conversion rate for clicks within the range 0..1.

### Returns
|Type|Description|
|-|-
double|The conversion rate for clicks within the range 0..1.

## <a name="getclicks"></a>getClicks
Returns the number of clicks.

### Returns
|Type|Description|
|-|-
long|The number of clicks.

## <a name="getconvertedclicks"></a>getConvertedClicks
Returns the number of clicks that converted.

### Returns
|Type|Description|
|-|-
long|The number of clicks that converted.

## <a name="getcost"></a>getCost
Returns the cost (spend) in the currency of the current account.

### Returns
|Type|Description|
|-|-
double|The cost in the currency of the account.

## <a name="getctr"></a>getCtr
Returns the click through rate in the range 0..1.

### Returns
|Type|Description|
|-|-
double|The click through rate.

## <a name="getimpressions"></a>getImpressions
Returns the number of impressions.

### Returns
|Type|Description|
|-|-
long|The number of impressions.

