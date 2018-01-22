# Keyword
Represents a keyword in the Bing Ads system.

|Method|Return Type|Description|
|-|-|-
[adParams]('#adParams}')|[AdParamSelector](./AdParamSelector)|Returns a selector of all ad params under this keyword.<br />
[clearDestinationUrl]('#clearDestinationUrl}')|void|Clears the destination URL of this keyword. <br />
[enable]('#enable}')|void|Enables this keyword.<br />
[getAdGroup]('#getAdGroup}')|[AdGroup](AdGroup)|Returns the parent ad group of this keyword.<br />
[getApprovalStatus]('#getApprovalStatus}')|String|Returns the approval status of this keyword. Supported values include:<br /> <br /> APPROVED,<br /> PENDING_REVIEW,<br /> UNDER_REVIEW,<br /> DISAPPROVED<br /><br />
[getCampaign]('#getCampaign}')|[Campaign](./Campaign)|Returns the parent campaign of this keyword.<br />
[getEntityType]('#getEntityType}')|String|Returns the entity type of this keyword, which is "Keyword".<br />
[getFirstPageCpc]('#getFirstPageCpc}')|double|Returns the estimated first page bid for this keyword.<br />
[getId]('#getId}')|long|Returns the ID of this keyword.<br />
[getMatchType]('#getMatchType}')|String|Returns the match type of this keyword. Supported values include:<br /> <br /> BROAD,<br /> PHRASE,<br /> EXACT<br /><br />
[getQualityScore]('#getQualityScore}')|int|Returns the quality score of this keyword, in the range 1…10.<br />
[getStatsFor(String dateRange)]('#getStatsFor-String-dateRange)}')|String|Returns stats for this keyword for the given date range. Supported values include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH,<br /> ALL_TIME<br /><br />
[getStatsFor(Object dateFrom, Object dateTo)]('#getStatsFor-Object-dateFrom_ Object dateTo)}')|String|Returns stats for this keyword for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified. <br />
[getText]('#getText}')|String|Returns the text of this keyword. The text will be returned in the format as follows, based on the match type of this keyword:<br /> <br /> &nbsp;•	books – broad match<br /> &nbsp;•	"books" – phrase match<br /> &nbsp;•	[origin of species] – exact match<br /><br />
[getTopOfPageCpc]('#getTopOfPageCpc}')|double|Returns the estimated mainline bid for this keyword.<br />
[isEnabled]('#isEnabled}')|boolean|Returns true if this keyword is enabled <br />
[isPaused]('#isPaused}')|boolean|Returns true if this keyword is paused. <br />
[pause]('#pause}')|void|Pauses this keyword.<br />
[remove]('#remove}')|void|Removes this keyword.<br />
[setAdParam(int index, String insertionText)]('#setAdParam-int-index_ String insertionText)}')|void|Creates an ad param with the specified insertion text and at the index specified on this keyword. <br />
[urls]('#urls}')|[KeywordUrls](./KeywordUrls)|Returns the URL fields of this keyword.<br />

<a name="#adParams"></a>
## adParams
Returns a selector of all ad params under this keyword.


<a name="#clearDestinationUrl"></a>
## clearDestinationUrl
Clears the destination URL of this keyword. 


<a name="#enable"></a>
## enable
Enables this keyword.


<a name="#getAdGroup"></a>
## getAdGroup
Returns the parent ad group of this keyword.


<a name="#getApprovalStatus"></a>
## getApprovalStatus
Returns the approval status of this keyword. Supported values include:<br /> <br /> APPROVED,<br /> PENDING_REVIEW,<br /> UNDER_REVIEW,<br /> DISAPPROVED<br />


<a name="#getCampaign"></a>
## getCampaign
Returns the parent campaign of this keyword.


<a name="#getEntityType"></a>
## getEntityType
Returns the entity type of this keyword, which is "Keyword".


<a name="#getFirstPageCpc"></a>
## getFirstPageCpc
Returns the estimated first page bid for this keyword.


<a name="#getId"></a>
## getId
Returns the ID of this keyword.


<a name="#getMatchType"></a>
## getMatchType
Returns the match type of this keyword. Supported values include:<br /> <br /> BROAD,<br /> PHRASE,<br /> EXACT<br />


<a name="#getQualityScore"></a>
## getQualityScore
Returns the quality score of this keyword, in the range 1…10.


<a name="#getStatsFor-String-dateRange)"></a>
## getStatsFor(String dateRange)
Returns stats for this keyword for the given date range. Supported values include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH,<br /> ALL_TIME<br />


<a name="#getStatsFor-Object-dateFrom_ Object dateTo)"></a>
## getStatsFor(Object dateFrom, Object dateTo)
Returns stats for this keyword for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified. 


<a name="#getText"></a>
## getText
Returns the text of this keyword. The text will be returned in the format as follows, based on the match type of this keyword:<br /> <br /> &nbsp;•	books – broad match<br /> &nbsp;•	"books" – phrase match<br /> &nbsp;•	[origin of species] – exact match<br />


<a name="#getTopOfPageCpc"></a>
## getTopOfPageCpc
Returns the estimated mainline bid for this keyword.


<a name="#isEnabled"></a>
## isEnabled
Returns true if this keyword is enabled 


<a name="#isPaused"></a>
## isPaused
Returns true if this keyword is paused. 


<a name="#pause"></a>
## pause
Pauses this keyword.


<a name="#remove"></a>
## remove
Removes this keyword.


<a name="#setAdParam-int-index_ String insertionText)"></a>
## setAdParam(int index, String insertionText)
Creates an ad param with the specified insertion text and at the index specified on this keyword. 


<a name="#urls"></a>
## urls
Returns the URL fields of this keyword.


