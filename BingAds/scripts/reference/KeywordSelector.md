# KeywordSelector
Provides methods to select keywords by using filtering and sorting.

|Method|Return Type|Description|
|-|-|-
[forDateRange(String dateRange)]('#fordaterange~string-daterange~')|[KeywordSelector](./KeywordSelector)|Returns a selector by filtering keywords in this selector using the date range provided. Supported values for the date range include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH,<br /> ALL_TIME<br /><br />
[forDateRange(Object dateFrom, Object dateTo)]('#fordaterange~object-datefrom_-object-dateto~')|[KeywordSelector](./KeywordSelector)|Returns a selector by filtering keywords in this selector using the beginning and ending dates provided. The date parameters can be entered as a string in YYYYMMDD format or as an object with year, month and day fields. An example for such an object is <code>{year: 2016, month: 5, day: 13}</code>.<br />
[get]('#get')|[KeywordIterator](./KeywordIterator)|Returns an iterator indexing the keywords in this selector.<br />
[orderBy(String orderBy)]('#orderby~string-orderby~')|[KeywordSelector](./KeywordSelector)|Returns a selector by specifying the condition for ordering the keywords in this selector. The format for the condition is "columnName orderDirection", for example, "Cost DESC".<br /> <br /> &nbsp;•	columnName can only be one column which is supported by the withCondition method.<br /> &nbsp;•	orderDirection can be either ASC for ascending or DESC for descending. If no order direction is specified, ASC is used by default.<br /> <br /> <code>orderBy()</code> can be invoked multiple times by calling it in sequence as shown by the following example:<br /> <br /> <code> keywordSelector = keywordSelector.orderBy(“MaxCpc”)<br /> &nbsp;&nbsp;.orderBy(“Clicks ASC”);<br /> </code><br />
[withCondition(String condition)]('#withcondition~string-condition~')|[KeywordSelector](./KeywordSelector)|Returns a selector by specifying the filtering condition on the keywords in this selector. The format for the condition string is "columnName operator value", for example., "AverageCpm > 0.35", where:<br /> <br /> &nbsp;•	columnName must be from the list of supported columns for keywords (see table below).<br /> &nbsp;&nbsp;o	If a Stats column is used in withCondition, it must be preceded by a forDateRange() invocation in the call chain.<br /> &nbsp;•	operator must be from the list of standard operators supported by Bing Ads Scripts.<br /> &nbsp;•	value is a value that falls within the accepted range of values for the data type of the column represented by columnName.<br /> <br /> As with the <code>orderBy()</code> method, <code>withCondition()</code> can also be used multiple times.<br /><br />
[withIds(long[] ids)]('#withids~long-ids~')|[KeywordSelector](./KeywordSelector)|Returns a selector by specifying the list of IDs to filter keywords in this selector. The input argument can accept a maximum of 10,000 IDs. If any more IDs are provided, any subsequent get() call on this selector will fail with an error.<br />
[withLimit(int limit)]('#withlimit~int-limit~')|[KeywordSelector](./KeywordSelector)|Returns a selector with as many keywords as specified by the limit argument selected from the beginning in this selector.<br />
Supported columns for keyword filtering. 

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
Keyword|
Status|Enumeration:<br />ENABLED&nbsp;<br />PAUSED&nbsp;<br />DISABLED|withCondition(&quot;Status &#x3D; PAUSED&quot;)|Status
Text|String|withCondition(&quot;Text STARTS_WITH &#x27;books&#x27;&quot;)|Keyword Text
KeywordMatchType|Enumeration:<br />BROAD&nbsp;<br />EXACT&nbsp;<br />PHRASE&nbsp;<br />CONTENT|withCondition(&quot;KeywordMatchType &#x3D; EXACT&quot;)|Match type
MaxCpc|double|withCondition(&quot;MaxCpc &gt; 0.40&quot;). The value specified is in the currency of the current account.|Bid
DestinationUrl|String|withCondition(&quot;DestinationUrl STARTS_WITH &#x27;http://www.example.com&#x27;&quot;)|Destination URL
FinalUrls|String|withCondition(&quot;FinalUrls CONTAINS &#x27;http://www.example.com&#x27;&quot;)|
QualityScore|int|withCondition(&quot;QualityScore &gt; 5&quot;)|Qual. score
FirstPageCpc|double|withCondition(&quot;FirstPageCpc &gt; 6.00&quot;). The value specified is in the currency of the current account.|Est. first page bid
TopOfPageCpc|double|withCondition(&quot;TopOfPageCpc &gt; 8.00&quot;). The value specified is in the currency of the current account.|Est. mainline bid

## <a name="fordaterange~string-daterange~"></a>forDateRange(String dateRange)
Returns a selector by filtering keywords in this selector using the date range provided. Supported values for the date range include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH,<br /> ALL_TIME<br />


## <a name="fordaterange~object-datefrom_-object-dateto~"></a>forDateRange(Object dateFrom, Object dateTo)
Returns a selector by filtering keywords in this selector using the beginning and ending dates provided. The date parameters can be entered as a string in YYYYMMDD format or as an object with year, month and day fields. An example for such an object is <code>{year: 2016, month: 5, day: 13}</code>.


## <a name="get"></a>get
Returns an iterator indexing the keywords in this selector.


## <a name="orderby~string-orderby~"></a>orderBy(String orderBy)
Returns a selector by specifying the condition for ordering the keywords in this selector. The format for the condition is "columnName orderDirection", for example, "Cost DESC".<br /> <br /> &nbsp;•	columnName can only be one column which is supported by the withCondition method.<br /> &nbsp;•	orderDirection can be either ASC for ascending or DESC for descending. If no order direction is specified, ASC is used by default.<br /> <br /> <code>orderBy()</code> can be invoked multiple times by calling it in sequence as shown by the following example:<br /> <br /> <code> keywordSelector = keywordSelector.orderBy(“MaxCpc”)<br /> &nbsp;&nbsp;.orderBy(“Clicks ASC”);<br /> </code>


## <a name="withcondition~string-condition~"></a>withCondition(String condition)
Returns a selector by specifying the filtering condition on the keywords in this selector. The format for the condition string is "columnName operator value", for example., "AverageCpm > 0.35", where:<br /> <br /> &nbsp;•	columnName must be from the list of supported columns for keywords (see table below).<br /> &nbsp;&nbsp;o	If a Stats column is used in withCondition, it must be preceded by a forDateRange() invocation in the call chain.<br /> &nbsp;•	operator must be from the list of standard operators supported by Bing Ads Scripts.<br /> &nbsp;•	value is a value that falls within the accepted range of values for the data type of the column represented by columnName.<br /> <br /> As with the <code>orderBy()</code> method, <code>withCondition()</code> can also be used multiple times.<br />


## <a name="withids~long-ids~"></a>withIds(long[] ids)
Returns a selector by specifying the list of IDs to filter keywords in this selector. The input argument can accept a maximum of 10,000 IDs. If any more IDs are provided, any subsequent get() call on this selector will fail with an error.


## <a name="withlimit~int-limit~"></a>withLimit(int limit)
Returns a selector with as many keywords as specified by the limit argument selected from the beginning in this selector.


