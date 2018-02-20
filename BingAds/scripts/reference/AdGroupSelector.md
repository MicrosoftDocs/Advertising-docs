# AdGroupSelector
Provides methods to select ad groups by using filtering and sorting.

Example usage:
```javascript
var adGroupSelector = BingAdsApp
     .adGroups()
     .withCondition("Impressions > 100")
     .forDateRange("LAST_MONTH")
     .orderBy("Clicks DESC");

 var adGroupIterator = adGroupSelector.get();
 while (adGroupIterator.hasNext()) {
   var adGroup = adGroupIterator.next();
 }
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[forDateRange(String dateRange)](#fordaterange~string-daterange~)|[AdGroupSelector](./AdGroupSelector)|Returns a selector using the specified predefined date range.
[forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~)|[AdGroupSelector](./AdGroupSelector)|Returns a selector with the specified start and end dates.
[get](#get)|[AdGroupIterator](./AdGroupIterator)|Returns an iterator that you use to get the ad groups in this selector.
[orderBy(String orderBy)](#orderby~string-orderby~)|[AdGroupSelector](./AdGroupSelector)|Returns a selector with the specified ordering.
[withCondition(String condition)](#withcondition~string-condition~)|[AdGroupSelector](./AdGroupSelector)|Returns a selector with the specified filtering conditions.
[withIds(long[] ids)](#withids~long-ids~)|[AdGroupSelector](./AdGroupSelector)|Returns a selector that will return only ad groups with the specified IDs.
[withLimit(int limit)](#withlimit~int-limit~)|[AdGroupSelector](./AdGroupSelector)|Returns a selector with as many ad groups as specified by the limit argument selected from the beginning in this selector.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="fordaterange~string-daterange~"></a>forDateRange(String dateRange)
Returns a selector using the specified predefined date range.

Supported date range values:

- TODAY
- YESTERDAY
- LAST_7_DAYS
- THIS_WEEK_SUN_TODAY
- LAST_14_DAYS
- LAST_30_DAYS
- LAST_WEEK_SUN_SAT
- THIS_MONTH
- LAST_MONTH
- ALL_TIME


### Arguments:
|Name|Type|Description|
|-|-|-
dateRange|String|Date range to set onto the selector.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector)|The selector with date range applied.
&nbsp;|&nbsp;
## <a name="fordaterange~object-datefrom_-object-dateto~"></a>forDateRange(Object dateFrom, Object dateTo)
Returns a selector with the specified start and end dates.

You may specify the date parameters using strings or objects. To use strings, specify the date in the form, YYYYMMDD. If you use objects, create a JSON object with the following fields:  

- year
- month
- day

For example, {year: 2016, month: 5, day: 13}.

### Arguments:
|Name|Type|Description|
|-|-|-
dateFrom|Object|Start date of the date range.
dateTo|Object|End date of the date range.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector)|The selector with date range applied.
&nbsp;|&nbsp;
## <a name="get"></a>get
Returns an iterator that you use to get the ad groups in this selector.
### Returns:
|Type|Description|
|-|-
[AdGroupIterator](./AdGroupIterator)|Iterator used to get the ad groups in this selector.
&nbsp;|&nbsp;
## <a name="orderby~string-orderby~"></a>orderBy(String orderBy)
Returns a selector with the specified ordering.

The format for the condition is "&lt;columnName&gt; &lt;orderDirection&gt;", for example, "Cost DESC". 

- columnName can only be one column which is supported by the withCondition method.
- orderDirection can be either ASC for ascending or DESC for descending. If no order direction is specified, ASC is used by default.<br /> <br /> <code>orderBy()</code> can be invoked multiple times by calling it in sequence as shown by the following example:<br /> <br /> <code> agSelector = agSelector.orderBy("MaxCpc")<br /> &nbsp;&nbsp;.orderBy("Clicks ASC"); </code>

### Arguments:
|Name|Type|Description|
|-|-|-
orderBy|String|Ordering to apply.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector)|The selector with ordering applied.
&nbsp;|&nbsp;
## <a name="withcondition~string-condition~"></a>withCondition(String condition)
Returns a selector with the specified filtering conditions.

Specify the condition parameter in the form, "columnName operator value" where: 

- columnName must be from the list of supported columns for ad groups (see table below).
- operator is one of the supported [operators](#Operators).

### Operators
The operator that can be used in a condition depends on the type of column. 
For Integer and Long columns: 

```
<  <=  >  >=  =  !=
```
For Double columns: 
```
<  >
```
For String columns: 
```
=  !=  STARTS_WITH  STARTS_WITH_IGNORE_CASE  CONTAINS
 CONTAINS_IGNORE_CASE  DOES_NOT_CONTAIN  DOES_NOT_CONTAIN_IGNORE_CASE
```
For Enumeration columns: 
```
=  !=  IN []  NOT_IN []
```

Operators are case-sensitive: `starts_with` won't work. 
If you set columnName to a performance metric column name, you must include the forDateRange method in the call chain.

Supported columns for ad group filtering. 

|Column|Type|Example|Bing Web UI filter|
|-|-|-|-
<strong>Stats</strong>|
AverageCpc|double|`withCondition("AverageCpc < 1.45")`|Avg. CPC
AverageCpm|double|`withCondition("AverageCpm > 0.48")`|Avg. CPM
AveragePageviews|double|`withCondition("AveragePageviews > 0")`|
AveragePosition|double|`withCondition("AveragePosition > 7.5")`|Avg. pos.
BounceRate|double|`withCondition("BounceRate < 0.5")`|
ClickConversionRate|double|`withCondition("ClickConversionRate > 0.1")`|Conv. Rate
Clicks|long|`withCondition("Clicks >= 21")`|Clicks
ConvertedClicks|long|`withCondition("ConvertedClicks <= 4")`|Conv.
Cost|double|`withCondition("Cost > 4.48")`. The value is in the currency of the account.|Spend
Ctr|double|`withCondition("Ctr > 0.01")`. Note that Ctr is returned in 0..1 range, so 5% Ctr is represented as 0.05.|CTR
Impressions|long|`withCondition("Impressions != 0")`|Impr.
&nbsp;|&nbsp;|&nbsp;|&nbsp;
<strong>Ad group attributes</strong>|
Status|Enumeration:<br />&nbsp;`ENABLED`<br />&nbsp;`PAUSED`<br />&nbsp;`REMOVED`|`withCondition("Status = PAUSED")`|
Name|String|`withCondition("Name CONTAINS_IGNORE_CASE 'shoes'")`|Ad group name
CampaignName|String|`withCondition("CampaignName CONTAINS_IGNORE_CASE 'promotion'")`|Campaign name
KeywordMaxCpc|double|`withCondition("KeywordMaxCpc > 10.0")`. The value is in the currency of the account.|
CampaignStatus|Enumeration:<br />&nbsp;`ENABLED`<br />&nbsp;`PAUSED`<br />&nbsp;`REMOVED`|`withCondition("CampaignStatus = ENABLED"). Use to return ad groups from only ENABLED campaigns.`|
&nbsp;|&nbsp;|&nbsp;|&nbsp;

### Arguments:
|Name|Type|Description|
|-|-|-
condition|String|Condition to add to the selector.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector)|The selector with the condition applied.
&nbsp;|&nbsp;
## <a name="withids~long-ids~"></a>withIds(long[] ids)
Returns a selector that will return only ad groups with the specified IDs.

The maximum number of IDs that you may specify is 10,000. If you specify more than 10,000 IDs, calling the get method will fail.

### Arguments:
|Name|Type|Description|
|-|-|-
ids|long[]|Array of ad group IDs.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector)|The selector restricted to the given IDs.
&nbsp;|&nbsp;
## <a name="withlimit~int-limit~"></a>withLimit(int limit)
Returns a selector with as many ad groups as specified by the limit argument selected from the beginning in this selector.

### Arguments:
|Name|Type|Description|
|-|-|-
limit|int|How many entities to return.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector)|The selector with limit applied.
&nbsp;|&nbsp;
