# KeywordSelector
Provides methods to select keywords by using filtering and sorting.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[forDateRange(String dateRange)](#fordaterange~string-daterange~)|[KeywordSelector](./KeywordSelector)|Returns a selector using the specified predefined date range.
[forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~)|[KeywordSelector](./KeywordSelector)|Returns a selector with the specified start and end dates.
[get](#get)|[KeywordIterator](./KeywordIterator)|Returns an iterator indexing the keywords in this selector.<br />
[orderBy(String orderBy)](#orderby~string-orderby~)|[KeywordSelector](./KeywordSelector)|Returns a selector with the specified ordering.
[withCondition(String condition)](#withcondition~string-condition~)|[KeywordSelector](./KeywordSelector)|Returns a selector by specifying the filtering condition on the keywords in this selector. The format for the condition string is "columnName operator value", for example., "AverageCpm > 0.35", where:<br /> <br /> &nbsp;•	columnName must be from the list of supported columns for keywords (see table below).<br /> &nbsp;&nbsp;o	If a Stats column is used in withCondition, it must be preceded by a forDateRange() invocation in the call chain.<br /> &nbsp;•	operator must be from the list of standard operators supported by Bing Ads Scripts.<br /> &nbsp;•	value is a value that falls within the accepted range of values for the data type of the column represented by columnName.<br /> <br /> As with the <code>orderBy()</code> method, <code>withCondition()</code> can also be used multiple times.<br /><br />
[withIds(long[] ids)](#withids~long-ids~)|[KeywordSelector](./KeywordSelector)|Returns a selector by specifying the list of IDs to filter keywords in this selector. The input argument can accept a maximum of 10,000 IDs. If any more IDs are provided, any subsequent get() call on this selector will fail with an error.<br />
[withLimit(int limit)](#withlimit~int-limit~)|[KeywordSelector](./KeywordSelector)|Returns a selector with as many keywords as specified by the limit argument selected from the beginning in this selector.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="fordaterange~string-daterange~"></a>forDateRange(String dateRange)
Returns a selector using the specified predefined date range.

Supported values for the date range are: 

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
[KeywordSelector](./KeywordSelector)|The selector with date range applied.
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
[KeywordSelector](./KeywordSelector)|The selector with date range applied.
&nbsp;|&nbsp;
## <a name="get"></a>get
Returns an iterator indexing the keywords in this selector.

### Returns:
|Type|Description|
|-|-
[KeywordIterator](./KeywordIterator)|Iterator of the requested keywords.
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
[KeywordSelector](./KeywordSelector)|The selector with ordering applied.
&nbsp;|&nbsp;
## <a name="withcondition~string-condition~"></a>withCondition(String condition)
Returns a selector by specifying the filtering condition on the keywords in this selector. The format for the condition string is "columnName operator value", for example., "AverageCpm > 0.35", where:<br /> <br /> &nbsp;•	columnName must be from the list of supported columns for keywords (see table below).<br /> &nbsp;&nbsp;o	If a Stats column is used in withCondition, it must be preceded by a forDateRange() invocation in the call chain.<br /> &nbsp;•	operator must be from the list of standard operators supported by Bing Ads Scripts.<br /> &nbsp;•	value is a value that falls within the accepted range of values for the data type of the column represented by columnName.<br /> <br /> As with the <code>orderBy()</code> method, <code>withCondition()</code> can also be used multiple times.<br />


Supported columns for keyword filtering. 

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
Ctr|double|`withCondition("Ctr > 0.01"). Note that Ctr is returned in 0..1 range, so 5% Ctr is represented as 0.05.`|CTR
Impressions|long|`withCondition("Impressions != 0")`|Impr.
&nbsp;|&nbsp;|&nbsp;|&nbsp;
<strong>Keyword</strong>|
Status|Enumeration:<br />&nbsp;`ENABLED`<br />&nbsp;`PAUSED`<br />&nbsp;`DISABLED`|`withCondition("Status = PAUSED")`|Status
Text|String|`withCondition("Text STARTS_WITH 'books'")`|Keyword Text
KeywordMatchType|Enumeration:<br />&nbsp;`BROAD`<br />&nbsp;`EXACT`<br />&nbsp;`PHRASE`<br />&nbsp;`CONTENT`|`withCondition("KeywordMatchType = EXACT")`|Match type
MaxCpc|double|`withCondition("MaxCpc > 0.40"). The value specified is in the currency of the current account.`|Bid
DestinationUrl|String|`withCondition("DestinationUrl STARTS_WITH 'http://www.example.com'")`|Destination URL
FinalUrls|String|`withCondition("FinalUrls CONTAINS 'http://www.example.com'")`|
QualityScore|int|`withCondition("QualityScore > 5")`|Qual. score
FirstPageCpc|double|`withCondition("FirstPageCpc > 6.00"). The value specified is in the currency of the current account.`|Est. first page bid
TopOfPageCpc|double|`withCondition("TopOfPageCpc > 8.00"). The value specified is in the currency of the current account.`|Est. mainline bid
&nbsp;|&nbsp;|&nbsp;|&nbsp;


### Arguments:
|Name|Type|Description|
|-|-|-
condition|String|Condition to add to the selector.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector)|The selector with the condition applied.
&nbsp;|&nbsp;
## <a name="withids~long-ids~"></a>withIds(long[] ids)
Returns a selector by specifying the list of IDs to filter keywords in this selector. The input argument can accept a maximum of 10,000 IDs. If any more IDs are provided, any subsequent get() call on this selector will fail with an error.

### Arguments:
|Name|Type|Description|
|-|-|-
ids|long[][]|Array of keyword IDs.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector)|The selector restricted to the given IDs.
&nbsp;|&nbsp;
## <a name="withlimit~int-limit~"></a>withLimit(int limit)
Returns a selector with as many keywords as specified by the limit argument selected from the beginning in this selector.

### Arguments:
|Name|Type|Description|
|-|-|-
limit|int|How many entities to return.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector)|The selector with limit applied.
&nbsp;|&nbsp;
