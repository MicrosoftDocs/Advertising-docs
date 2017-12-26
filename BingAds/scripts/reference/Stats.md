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
&nbsp;|&nbsp;|&nbsp;

## <a name="getaveragecpc"></a>getAverageCpc
Returns the average cost per click of the associated entity.

### Returns:
|Type|Description|
|-|-
double|The average cost per click.
&nbsp;|&nbsp;
## <a name="getaveragecpm"></a>getAverageCpm
Returns the average cost per thousand impressions of the associated entity.

### Returns:
|Type|Description|
|-|-
double|The average cost per thousand impressions.
&nbsp;|&nbsp;
## <a name="getaverageposition"></a>getAveragePosition
Returns the average position of the associated entity.

### Returns:
|Type|Description|
|-|-
double|The average position.
&nbsp;|&nbsp;
## <a name="getclickconversionrate"></a>getClickConversionRate
Returns the conversion rate for clicks of the associated entity within the 0..1 range.

### Returns:
|Type|Description|
|-|-
double|
&nbsp;|&nbsp;
## <a name="getclicks"></a>getClicks
Returns the number of clicks of the associated entity.

### Returns:
|Type|Description|
|-|-
long|The number of clicks.
&nbsp;|&nbsp;
## <a name="getconvertedclicks"></a>getConvertedClicks
Returns the number of clicks that converted of the associated entity.

### Returns:
|Type|Description|
|-|-
long|
&nbsp;|&nbsp;
## <a name="getcost"></a>getCost
Returns the cost (spend) of the associated entity in the currency of the current account.

### Returns:
|Type|Description|
|-|-
double|The cost in the default currency of the account.
&nbsp;|&nbsp;
## <a name="getctr"></a>getCtr
Returns the calick through rate of the associated entity within the 0..1 range. 

### Returns:
|Type|Description|
|-|-
double|The click through rate.
&nbsp;|&nbsp;
## <a name="getimpressions"></a>getImpressions
Returns the number of impressions of the associated entity.

### Returns:
|Type|Description|
|-|-
long|The number of impressions.
&nbsp;|&nbsp;
