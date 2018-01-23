# AdGroupSelector
Provides methods to select ad groups by using filtering and sorting.

|Method|Return Type|Description|
|-|-|-
[forDateRange(String dateRange)]('#forDateRange-String-dateRange)')|[AdGroupSelector](./AdGroupSelector)|Returns a selector by filtering ad groups in this selector using the date range provided. Supported values for the date range include:<br />  <br /> `TODAY`,<br />  `YESTERDAY`,<br /> `LAST_7_DAYS`,<br /> `THIS_WEEK_SUN_TODAY`,<br /> `LAST_14_DAYS`,<br /> `LAST_30_DAYS`,<br /> `LAST_WEEK_SUN_SAT`,<br /> `THIS_MONTH`,<br /> `LAST_MONTH`,<br /> `ALL_TIME`<br /><br />
[forDateRange(Object dateFrom, Object dateTo)]('#forDateRange-Object-dateFrom_ Object dateTo)')|[AdGroupSelector](./AdGroupSelector)|Returns a selector by filtering ad groups in this selector using the beginning and ending dates provided.  The date parameters can be entered as a string in YYYYMMDD format or as an object with year, month and day fields.  An example for such an object is <code>{year: 2016, month: 5, day: 13}</code>.<br />
[get]('#get')|[AdGroupIterator](./AdGroupIterator)|Returns an iterator indexing the ad groups in this selector.<br />
[orderBy(String orderBy)]('#orderBy-String-orderBy)')|[AdGroupSelector](./AdGroupSelector)|Returns a selector by specifying the condition for ordering the ad groups in this selector. The format for the condition is "columnName orderDirection", for e.g., "Cost DESC". <br /> <br />         &nbsp;• columnName can only be one column which is supported by the withCondition method.<br /> &nbsp;• orderDirection can be either ASC for ascending or DESC for descending. If no order direction is specified, ASC is used by default.<br /> <br /> <code>orderBy()</code> can be invoked multiple times by calling it in sequence as shown by the following example:<br /> <br /> <code> agSelector = agSelector.orderBy("MaxCpc")<br /> &nbsp;&nbsp;.orderBy("Clicks ASC"); </code>"<br />
[withCondition(String condition)]('#withCondition-String-condition)')|[AdGroupSelector](./AdGroupSelector)|Returns a selector by specifying the filtering condition on the ad groups in this selector. The format for the condition string is "columnName operator value", for e.g., "AverageCpm > 0.35", where:<br /> <br /> &nbsp;•	columnName must be from the list of supported columns for ad groups (see table below).<br /> &nbsp;&nbsp;o	If a Stats column is used in withCondition, it must be preceded by a forDateRange() invocation in the call chain.<br /> &nbsp;•	operator must be from the list of standard operators supported by Bing Ads Scripts.<br /> &nbsp;•	value is a value that falls within the accepted range of values for the data type of the column represented by columnName.<br /> <br /> As with the <code>orderBy()</code> method, <code>withCondition()</code> can also be used multiple times.<br /><br />
[withIds(long[] ids)]('#withIds-long-ids)')|[AdGroupSelector](./AdGroupSelector)|Returns a selector by specifying the list of IDs to filter ad groups in this selector. The input argument can accept a maximum of 10,000 IDs. If any more IDs are provided, any subsequent get() call on this selector will fail with an error.<br />
[withLimit(int limit)]('#withLimit-int-limit)')|[AdGroupSelector](./AdGroupSelector)|Returns a selector with as many ad groups as specified by the limit argument selected from the beginning in this selector.<br />
Supported columns for ad group filtering. 

|Column|Type|Example|Bing Web UI filter|
|-|-|-|-
Stats|
AverageCpc|double|withCondition(&quot;AverageCpc &lt; 1.45&quot;)|Avg. CPC
AverageCpm|double|withCondition(&quot;AverageCpm &gt; 0.48&quot;)|Avg. CPM
AveragePageviews|double|withCondition(&quot;AveragePageviews &gt; 0&quot;)|
AveragePosition|double|withCondition(&quot;AveragePosition &gt; 7.5&quot;)|Avg. pos.
BounceRate|double|withCondition(&quot;BounceRate &lt; 0.5&quot;)|
ClickConversionRate|double|withCondition(&quot;ClickConversionRate &gt; 0.1&quot;)|Conv. Rate
Clicks|long|withCondition(&quot;Clicks &gt;&#x3D; 21&quot;)|Clicks
ConvertedClicks|long|withCondition(&quot;ConvertedClicks &lt;&#x3D; 4&quot;)|Conv.
Cost|double|withCondition(&quot;Cost &gt; 4.48&quot;). The value is in the currency of the account.|Spend
Ctr|double|withCondition(&quot;Ctr &gt; 0.01&quot;). Note that Ctr is returned in 0..1 range, so 5% Ctr is represented as 0.05.|CTR
Impressions|long|withCondition(&quot;Impressions !&#x3D; 0&quot;)|Impr.
Ad group attributes|
Status|Enumeration:<br />ENABLED&nbsp;<br />PAUSED&nbsp;<br />REMOVED|withCondition(&quot;Status &#x3D; PAUSED&quot;)|
Name|String|withCondition(&quot;Name CONTAINS_IGNORE_CASE &#x27;shoes&#x27;&quot;)|Ad group name
CampaignName|String|withCondition(&quot;CampaignName CONTAINS_IGNORE_CASE &#x27;promotion&#x27;&quot;)|Campaign name
KeywordMaxCpc|double|withCondition(&quot;KeywordMaxCpc &gt; 10.0&quot;). The value is in the currency of the account.|
CampaignStatus|Enumeration:<br />ENABLED&nbsp;<br />PAUSED&nbsp;<br />REMOVED|withCondition(&quot;CampaignStatus &#x3D; ENABLED&quot;). Use to return ad groups from only ENABLED campaigns.|

<a name="#forDateRange-String-dateRange)"></a>
## forDateRange(String dateRange)
Returns a selector by filtering ad groups in this selector using the date range provided. Supported values for the date range include:<br />  <br /> `TODAY`,<br />  `YESTERDAY`,<br /> `LAST_7_DAYS`,<br /> `THIS_WEEK_SUN_TODAY`,<br /> `LAST_14_DAYS`,<br /> `LAST_30_DAYS`,<br /> `LAST_WEEK_SUN_SAT`,<br /> `THIS_MONTH`,<br /> `LAST_MONTH`,<br /> `ALL_TIME`<br />


<a name="#forDateRange-Object-dateFrom_ Object dateTo)"></a>
## forDateRange(Object dateFrom, Object dateTo)
Returns a selector by filtering ad groups in this selector using the beginning and ending dates provided.  The date parameters can be entered as a string in YYYYMMDD format or as an object with year, month and day fields.  An example for such an object is <code>{year: 2016, month: 5, day: 13}</code>.


<a name="#get"></a>
## get
Returns an iterator indexing the ad groups in this selector.


<a name="#orderBy-String-orderBy)"></a>
## orderBy(String orderBy)
Returns a selector by specifying the condition for ordering the ad groups in this selector. The format for the condition is "columnName orderDirection", for e.g., "Cost DESC". <br /> <br />         &nbsp;• columnName can only be one column which is supported by the withCondition method.<br /> &nbsp;• orderDirection can be either ASC for ascending or DESC for descending. If no order direction is specified, ASC is used by default.<br /> <br /> <code>orderBy()</code> can be invoked multiple times by calling it in sequence as shown by the following example:<br /> <br /> <code> agSelector = agSelector.orderBy("MaxCpc")<br /> &nbsp;&nbsp;.orderBy("Clicks ASC"); </code>"


<a name="#withCondition-String-condition)"></a>
## withCondition(String condition)
Returns a selector by specifying the filtering condition on the ad groups in this selector. The format for the condition string is "columnName operator value", for e.g., "AverageCpm > 0.35", where:<br /> <br /> &nbsp;•	columnName must be from the list of supported columns for ad groups (see table below).<br /> &nbsp;&nbsp;o	If a Stats column is used in withCondition, it must be preceded by a forDateRange() invocation in the call chain.<br /> &nbsp;•	operator must be from the list of standard operators supported by Bing Ads Scripts.<br /> &nbsp;•	value is a value that falls within the accepted range of values for the data type of the column represented by columnName.<br /> <br /> As with the <code>orderBy()</code> method, <code>withCondition()</code> can also be used multiple times.<br />


<a name="#withIds-long-ids)"></a>
## withIds(long[] ids)
Returns a selector by specifying the list of IDs to filter ad groups in this selector. The input argument can accept a maximum of 10,000 IDs. If any more IDs are provided, any subsequent get() call on this selector will fail with an error.


<a name="#withLimit-int-limit)"></a>
## withLimit(int limit)
Returns a selector with as many ad groups as specified by the limit argument selected from the beginning in this selector.


