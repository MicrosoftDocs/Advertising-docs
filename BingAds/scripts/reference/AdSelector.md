# AdSelector
Provides methods to select ads by using filtering and sorting.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[forDateRange(String dateRange)](#fordaterange~string-daterange~)|[AdSelector](./AdSelector)|Returns a selector by filtering ads in this selector using the date range provided. Supported values for the date range include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH, ALL_TIME<br /><br />
[forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~)|[AdSelector](./AdSelector)|Returns a selector by filtering ads in this selector using the beginning and ending dates provided. The date parameters can be entered as a string in YYYYMMDD format or as an object with year, month and day fields. An example for such an object is <code>{year: 2016, month: 5, day: 13}</code>.<br />
[get](#get)|[AdIterator](./AdIterator)|Returns an iterator indexing the ads in this selector.<br />
[orderBy(String orderBy)](#orderby~string-orderby~)|[AdSelector](./AdSelector)|Returns a selector by specifying the condition for ordering the ads in this selector. The format for the condition is "columnName orderDirection", for e.g., "Cost DESC".<br /> <br /> &nbsp;•	columnName can only be one column which is supported by the withCondition method.<br /> &nbsp;•	orderDirection can be either ASC for ascending or DESC for descending. If no order direction is specified, ASC is used by default.<br /> <br /> <code>orderBy()</code> can be invoked multiple times by calling it in sequence as shown by the following example:<br /> <br /> <code>adSelector = adSelector.orderBy("MaxCpc")<br /> .orderBy("Clicks ASC");<br /> </code><br />
[withCondition(String condition)](#withcondition~string-condition~)|[AdSelector](./AdSelector)|Returns a selector by specifying the filtering condition on the ads in this selector. The format for the condition string is "columnName operator value", for e.g., "AverageCpm > 0.35", where:<br /> <br /> &nbsp;•	columnName must be from the list of supported columns for ads (see table below).<br /> &nbsp;&nbsp;o	If a Stats column is used in withCondition, it must be preceded by a forDateRange() invocation in the call chain.<br /> &nbsp;•	operator must be from the list of standard operators supported by Bing Ads Scripts.<br /> &nbsp;•	value is a value that falls within the accepted range of values for the data type of the column represented by columnName.<br /> <br /> As with the <code>orderBy()</code> method, <code>withCondition()</code> can also be used multiple times.<br /><br />
[withIds(long[] ids)](#withids~long-ids~)|[AdSelector](./AdSelector)|Returns a selector by specifying the list of IDs to filter ads in this selector. The input argument can accept a maximum of 10,000 IDs. If any more IDs are provided, any subsequent get() call on this selector will fail with an error<br />
[withLimit(int limit)](#withlimit~int-limit~)|[AdSelector](./AdSelector)|Returns a selector with as many ads as specified by the limit argument selected from the beginning in this selector.<br />
Supported columns for ad filtering. 

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
Ctr|double|withCondition(&quot;Ctr &gt; 0.01&quot;). Ctr is returned in 0..1 range, so 5% Ctr is represented as 0.05.|CTR
Impressions|long|withCondition(&quot;Impressions !&#x3D; 0&quot;)|Impr.
Ad attributes|
Status|Enumeration:<br />ENABLED&nbsp;<br />PAUSED&nbsp;<br />DISABLED|withCondition(&quot;Status &#x3D; PAUSED&quot;)|Status
ApprovalStatus|Enumeration:<br />APPROVED&nbsp;<br />DISAPPROVED&nbsp;<br />UNCHECKED|withCondition(&quot;ApprovalStatus NOT_IN [DISAPPROVED, UNCHECKED]&quot;)|Delivery
Type|Enumeration:<br />EXPANDED_TEXT_AD&nbsp;<br />MOBILE_AD&nbsp;<br />TEXT_AD|withCondition(&quot;Type NOT_IN [IMAGE_AD, RICH_MEDIA_AD]&quot;)|Ad type
Headline|String|withCondition(&quot;Headline CONTAINS_IGNORE_CASE &#x27;leather shoes&#x27;&quot;)|Ad title
Description1|String|withCondition(&quot;Description1 STARTS_WITH &#x27;Leather&#x27;&quot;)|Ad text
Description2|String|withCondition(&quot;Description2 &#x3D; &#x27;Hurry to buy&#x27;&quot;)|
DisplayUrl|String|withCondition(&quot;DisplayUrl STARTS_WITH &#x27;www.example.com&#x27;&quot;)|Display URL
DestinationUrl|String|withCondition(&quot;DestinationUrl STARTS_WITH &#x27;http://www.example.com&#x27;&quot;)|Destination URL
CreativeFinalUrls|String|withCondition(&quot;CreativeFinalUrls CONTAINS &#x27;http://www.example.com&#x27;&quot;)|
AdGroupName|String|withCondition(&quot;AdGroupName CONTAINS_IGNORE_CASE &#x27;shoes&#x27;&quot;)|Ad group name
AdGroupStatus|Enumeration:<br />ENABLED&nbsp;<br />PAUSED&nbsp;<br />REMOVED|withCondition(&quot;AdGroupStatus &#x3D; ENABLED&quot;). Use to fetch ads from only ENABLED ad groups.|
CampaignName|String|withCondition(&quot;CampaignName CONTAINS_IGNORE_CASE &#x27;promotion&#x27;&quot;)	Campaign name|
CampaignStatus|Enumeration:<br />ENABLED&nbsp;<br />PAUSED&nbsp;<br />REMOVED|withCondition(&quot;CampaignStatus &#x3D; ENABLED&quot;). Use to fetch ads from only ENABLED campaigns.|
DevicePreferenceType|Enumeration:<br />MOBILE&nbsp;<br />ALL|withCondition(&quot;DevicePreferenceType &#x3D; MOBILE&quot;). Use to fetch only mobile-preferred ads.|Device preference

## <a name="fordaterange~string-daterange~"></a>forDateRange(String dateRange)
Returns a selector by filtering ads in this selector using the date range provided. Supported values for the date range include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH, ALL_TIME<br />


## <a name="fordaterange~object-datefrom_-object-dateto~"></a>forDateRange(Object dateFrom, Object dateTo)
Returns a selector by filtering ads in this selector using the beginning and ending dates provided. The date parameters can be entered as a string in YYYYMMDD format or as an object with year, month and day fields. An example for such an object is <code>{year: 2016, month: 5, day: 13}</code>.


## <a name="get"></a>get
Returns an iterator indexing the ads in this selector.


## <a name="orderby~string-orderby~"></a>orderBy(String orderBy)
Returns a selector by specifying the condition for ordering the ads in this selector. The format for the condition is "columnName orderDirection", for e.g., "Cost DESC".<br /> <br /> &nbsp;•	columnName can only be one column which is supported by the withCondition method.<br /> &nbsp;•	orderDirection can be either ASC for ascending or DESC for descending. If no order direction is specified, ASC is used by default.<br /> <br /> <code>orderBy()</code> can be invoked multiple times by calling it in sequence as shown by the following example:<br /> <br /> <code>adSelector = adSelector.orderBy("MaxCpc")<br /> .orderBy("Clicks ASC");<br /> </code>


## <a name="withcondition~string-condition~"></a>withCondition(String condition)
Returns a selector by specifying the filtering condition on the ads in this selector. The format for the condition string is "columnName operator value", for e.g., "AverageCpm > 0.35", where:<br /> <br /> &nbsp;•	columnName must be from the list of supported columns for ads (see table below).<br /> &nbsp;&nbsp;o	If a Stats column is used in withCondition, it must be preceded by a forDateRange() invocation in the call chain.<br /> &nbsp;•	operator must be from the list of standard operators supported by Bing Ads Scripts.<br /> &nbsp;•	value is a value that falls within the accepted range of values for the data type of the column represented by columnName.<br /> <br /> As with the <code>orderBy()</code> method, <code>withCondition()</code> can also be used multiple times.<br />


## <a name="withids~long-ids~"></a>withIds(long[] ids)
Returns a selector by specifying the list of IDs to filter ads in this selector. The input argument can accept a maximum of 10,000 IDs. If any more IDs are provided, any subsequent get() call on this selector will fail with an error


## <a name="withlimit~int-limit~"></a>withLimit(int limit)
Returns a selector with as many ads as specified by the limit argument selected from the beginning in this selector.


