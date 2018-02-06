# CampaignSelector
Provides methods to select campaigns by using filtering and sorting.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[forDateRange(String dateRange)](#fordaterange~string-daterange~)|[CampaignSelector](./CampaignSelector)|Returns a selector by filtering campaigns in this selector using the date range provided. Supported values for the date range include:<br /> <br /> `TODAY`<br /> `YESTERDAY`<br /> `LAST_7_DAYS`<br /> `THIS_WEEK_SUN_TODAY`<br /> `LAST_14_DAYS`<br /> `LAST_30_DAYS`<br /> `LAST_WEEK_SUN_SAT`<br /> `THIS_MONTH`<br /> `LAST_MONTH`<br /> `ALL_TIME`<br /><br />
[forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~)|[CampaignSelector](CampaignSelector)|Returns a selector by filtering campaigns in this selector using the beginning and ending dates provided. The date parameters can be entered as a string in YYYYMMDD format or as an object with year, month and day fields. An example for such an object is <code>{year: 2016, month: 5, day: 13}</code>.<br />
[get](#get)|[CampaignIterator](./CampaignIterator)|Returns an iterator indexing the campaigns in this selector.<br />
[orderBy(String orderBy)](#orderby~string-orderby~)|[CampaignSelector](./CampaignSelector)|Returns a selector by specifying the condition for ordering the campaigns in this selector. The format for the condition is "columnName orderDirection", for example, "Cost DESC".<br /> <br /> &nbsp;•	columnName can only be one column which is supported by the withCondition method.<br /> &nbsp;•	orderDirection can be either ASC for ascending or DESC for descending. If no order direction is specified, ASC is used by default.<br /> <br /> <code>orderBy()</code> can be invoked multiple times by calling it in sequence as shown by the following example:<br /> <br /> <code> campaignSelector = campaignSelector.orderBy("MaxCpc") &nbsp;&nbsp;.orderBy("Clicks ASC"); </code><br />
[withCondition(String condition)](#withcondition~string-condition~)|[CampaignSelector](./CampaignSelector)|Returns a selector by specifying the filtering condition on the campaigns in this selector. The format for the condition string is "columnName operator value", for e.g., "AverageCpm > 0.35", where:<br /> <br /> &nbsp;•	columnName must be from the list of supported columns for campaigns (see table below).<br /> &nbsp;&nbsp;o	If a Stats column is used in withCondition, it must be preceded by a forDateRange() invocation in the call chain.<br /> &nbsp;•	operator must be from the list of standard operators supported by Bing Ads Scripts.<br /> &nbsp;•	value is a value that falls within the accepted range of values for the data type of the column represented by columnName.<br /> <br /> As with the <code>orderBy()</code> method, <code>withCondition()</code> can also be used multiple times.<br />
[withIds(long[] ids)](#withids~long-ids~)|[CampaignSelector](./CampaignSelector)|Returns a selector by specifying the list of IDs to filter campaigns in this selector. The input argument can  accept a maximum of 10,000 IDs. If any more IDs are provided, any subsequent get() call on this selector will fail with an error.<br />
[withLimit(int limit)](#withlimit~int-limit~)|[CampaignSelector](./CampaignSelector)|Returns a selector with as many campaigns as specified by the limit argument selected from the beginning in this selector.<br />
&nbsp;|&nbsp;|&nbsp;

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

## <a name="fordaterange~string-daterange~"></a>forDateRange(String dateRange)
Returns a selector by filtering campaigns in this selector using the date range provided. Supported values for the date range include:<br /> <br /> `TODAY`<br /> `YESTERDAY`<br /> `LAST_7_DAYS`<br /> `THIS_WEEK_SUN_TODAY`<br /> `LAST_14_DAYS`<br /> `LAST_30_DAYS`<br /> `LAST_WEEK_SUN_SAT`<br /> `THIS_MONTH`<br /> `LAST_MONTH`<br /> `ALL_TIME`<br />

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
Returns a selector by filtering campaigns in this selector using the beginning and ending dates provided. The date parameters can be entered as a string in YYYYMMDD format or as an object with year, month and day fields. An example for such an object is <code>{year: 2016, month: 5, day: 13}</code>.

### Arguments:
|Name|Type|Description|
|-|-|-
dateFrom|Object|Start date of the date range.dateTo|Object|End date of the date range.
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
Returns a selector by specifying the condition for ordering the campaigns in this selector. The format for the condition is "columnName orderDirection", for example, "Cost DESC".<br /> <br /> &nbsp;•	columnName can only be one column which is supported by the withCondition method.<br /> &nbsp;•	orderDirection can be either ASC for ascending or DESC for descending. If no order direction is specified, ASC is used by default.<br /> <br /> <code>orderBy()</code> can be invoked multiple times by calling it in sequence as shown by the following example:<br /> <br /> <code> campaignSelector = campaignSelector.orderBy("MaxCpc") &nbsp;&nbsp;.orderBy("Clicks ASC"); </code>

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
Returns a selector by specifying the filtering condition on the campaigns in this selector. The format for the condition string is "columnName operator value", for e.g., "AverageCpm > 0.35", where:<br /> <br /> &nbsp;•	columnName must be from the list of supported columns for campaigns (see table below).<br /> &nbsp;&nbsp;o	If a Stats column is used in withCondition, it must be preceded by a forDateRange() invocation in the call chain.<br /> &nbsp;•	operator must be from the list of standard operators supported by Bing Ads Scripts.<br /> &nbsp;•	value is a value that falls within the accepted range of values for the data type of the column represented by columnName.<br /> <br /> As with the <code>orderBy()</code> method, <code>withCondition()</code> can also be used multiple times.

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
Returns a selector by specifying the list of IDs to filter campaigns in this selector. The input argument can  accept a maximum of 10,000 IDs. If any more IDs are provided, any subsequent get() call on this selector will fail with an error.

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
