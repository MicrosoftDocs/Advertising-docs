# CampaignSelector
Provides methods to select campaigns by using filtering and sorting.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[forDateRange(String dateRange)](#fordaterange~string-daterange~)|[CampaignSelector](./CampaignSelector)|Returns a selector using the specified predefined date range.
[forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~)|[CampaignSelector](CampaignSelector)|Returns a selector with the specified start and end dates.
[get](#get)|[CampaignIterator](./CampaignIterator)|Returns an iterator indexing the campaigns in this selector.<br />
[orderBy(String orderBy)](#orderby~string-orderby~)|[CampaignSelector](./CampaignSelector)|Returns a selector with the specified ordering.
[withCondition(String condition)](#withcondition~string-condition~)|[CampaignSelector](./CampaignSelector)|Returns a selector with the specified filtering conditions.
[withIds(long[] ids)](#withids~long-ids~)|[CampaignSelector](./CampaignSelector)|Returns a selector that will return only campaigns with the specified IDs.
[withLimit(int limit)](#withlimit~int-limit~)|[CampaignSelector](./CampaignSelector)|Returns a selector with as many campaigns as specified by the limit argument selected from the beginning in this selector.<br />
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
[CampaignSelector](./CampaignSelector)|The selector with date range applied.
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
[CampaignSelector](CampaignSelector)|The selector with date range applied.
&nbsp;|&nbsp;
## <a name="get"></a>get
Returns an iterator indexing the campaigns in this selector.

### Returns:
|Type|Description|
|-|-
[CampaignIterator](./CampaignIterator)|Iterator of the requested campaigns.
&nbsp;|&nbsp;
## <a name="orderby~string-orderby~"></a>orderBy(String orderBy)
Returns a selector with the specified ordering.

Specify the orderBy parameter in the form, "columnName [ASC|DESC]" where:

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
[CampaignSelector](./CampaignSelector)|The selector with ordering applied.
&nbsp;|&nbsp;
## <a name="withcondition~string-condition~"></a>withCondition(String condition)
Returns a selector with the specified filtering conditions.

Specify the condition parameter in the form, "columnName operator value" where: 

- columnName is the name of a performance metric to order the results by. For a list of possible values, see [Supported Columns](#supported-campaign-columns).  If you set columName to a performance metric column name, you must also specify a date range using [forDateRange(String dateRange)](#fordaterange~string-daterange~) or [forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~).
- operator is one of the supported [operators](#operators).

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

<a name="supported-campaign-columns"></a>
Supported columns for campaign filtering. 

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
Cost|double|`withCondition("Cost > 4.48"). The value is in the currency of the account.`|Spend
Ctr|double|`withCondition("Ctr > 0.01"). Ctr is returned in 0..1 range, so 5% Ctr is represented as 0.05.`|CTR
Impressions|long|`withCondition("Impressions != 0")`|Impr.
&nbsp;|&nbsp;|&nbsp;|&nbsp;
<strong>Campaign attributes</strong>|
Status|Enumeration:<br />&nbsp;`ENABLED`<br />&nbsp;`PAUSED`<br />&nbsp;`REMOVED`<br />&nbsp;`BUDGET_PAUSED`<br />&nbsp;`BUDGET_AND_USER_PAUSED`|`withCondition("Status = PAUSED")`|Campaign status
Name|String|`withCondition("Name CONTAINS_IGNORE_CASE 'promotion'")`|Campaign name
Budget|double|`withCondition("Budget > 10.0")`|Budget
Type|Enumeration:<br />&nbsp;`SEARCH_AND_CONTENT`<br />&nbsp;`SHOPPING`<br />&nbsp;`DYNAMIC_SEARCH_ADS`|`withCondition("Type = 'SEARCH_AND_CONTENT'")`|Bing-specific filter
BudgetType|Enumeration:<br />&nbsp;`STANDARD`<br />&nbsp;`ACCELERATED`|`withCondition("BudgetType = 'ACCELERATED'")`|Bing-specific filter
DeliveryStatus|Enumeration:<br />&nbsp;`ELIGIBLE`<br />&nbsp;`LIMITED_BY_BUDGET`<br />&nbsp;`HOLD`<br />&nbsp;`CAMPAIGN_OUT_OF_BUDGET`<br />&nbsp;`CAMPAIGN_SUSPENDED`<br />&nbsp;`CAMPAIGN_PAUSED`|`withCondition("DeliveryStatus NOT IN ['LIMITED_BY_BUDGET', 'HOLD', 'CAMPAIGN_OUT_OF_BUDGET']")`|Bing-specific filter
&nbsp;|&nbsp;|&nbsp;|&nbsp;


### Arguments:
|Name|Type|Description|
|-|-|-
condition|String|Condition to add to the selector.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector)|The selector with the condition applied.
&nbsp;|&nbsp;
## <a name="withids~long-ids~"></a>withIds(long[] ids)
Returns a selector that will return only campaigns with the specified IDs.

The maximum number of IDs that you may specify is 1,000. If you specify more than 1,000 IDs, calling the get method will fail.

### Arguments:
|Name|Type|Description|
|-|-|-
ids|long[]|Array of campaign IDs.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector)|The selector restricted to the given IDs.
&nbsp;|&nbsp;
## <a name="withlimit~int-limit~"></a>withLimit(int limit)
Returns a selector with as many campaigns as specified by the limit argument selected from the beginning in this selector.

### Arguments:
|Name|Type|Description|
|-|-|-
limit|int|How many entities to return.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector)|The selector with limit applied.
&nbsp;|&nbsp;