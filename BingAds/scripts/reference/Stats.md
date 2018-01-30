# Stats
Provides information about statistics related to the different entity types in Bing Ads.

Example usage:
```javascript
 var stats = campaign.getStatsFor("LAST_MONTH");
 var impressions = stats.getImpressions();
 var clicks = stats.getClicks();
 // etc.
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[getAverageCpc](#getaveragecpc)|double|Returns the average cost per click of the associated entity.<br />
[getAverageCpm](#getaveragecpm)|double|Returns the average cost per thousand impressions of the associated entity.<br />
[getAveragePosition](#getaverageposition)|double|Returns the average position of the associated entity.<br />
[getClickConversionRate](#getclickconversionrate)|double|Returns the conversion rate for clicks of the associated entity within the 0..1 range.<br />
[getClicks](#getclicks)|long|Returns the number of clicks of the associated entity.<br />
[getConvertedClicks](#getconvertedclicks)|long|Returns the number of clicks that converted of the associated entity.<br />
[getCost](#getcost)|double|Returns the cost (spend) of the associated entity in the currency of the current account.<br />
[getCtr](#getctr)|double|Returns the calick through rate of the associated entity within the 0..1 range. <br />
[getImpressions](#getimpressions)|long|Returns the number of impressions of the associated entity.<br />

## <a name="getaveragecpc"></a>getAverageCpc
Returns the average cost per click of the associated entity.


## <a name="getaveragecpm"></a>getAverageCpm
Returns the average cost per thousand impressions of the associated entity.


## <a name="getaverageposition"></a>getAveragePosition
Returns the average position of the associated entity.


## <a name="getclickconversionrate"></a>getClickConversionRate
Returns the conversion rate for clicks of the associated entity within the 0..1 range.


## <a name="getclicks"></a>getClicks
Returns the number of clicks of the associated entity.


## <a name="getconvertedclicks"></a>getConvertedClicks
Returns the number of clicks that converted of the associated entity.


## <a name="getcost"></a>getCost
Returns the cost (spend) of the associated entity in the currency of the current account.


## <a name="getctr"></a>getCtr
Returns the calick through rate of the associated entity within the 0..1 range. 


## <a name="getimpressions"></a>getImpressions
Returns the number of impressions of the associated entity.

