# Keyword
Represents a keyword in the Bing Ads system.

Example usage:
```javascript
 var stats = keyword.getStatsFor(&quot;THIS_MONTH&quot;);
```

|Method|Return Type|Description|
|-|-|-
[adParams](#adparams)|[AdParamSelector](./AdParamSelector)|Returns a selector of all ad params under this keyword.<br />
[clearDestinationUrl](#cleardestinationurl)|void|Clears the destination URL of this keyword. <br />
[enable](#enable)|void|Enables this keyword.<br />
[getAdGroup](#getadgroup)|[AdGroup](AdGroup)|Returns the parent ad group of this keyword.<br />
[getApprovalStatus](#getapprovalstatus)|String|Returns the approval status of this keyword. Supported values include:<br /> <br /> APPROVED,<br /> PENDING_REVIEW,<br /> UNDER_REVIEW,<br /> DISAPPROVED<br /><br />
[getCampaign](#getcampaign)|[Campaign](./Campaign)|Returns the parent campaign of this keyword.<br />
[getEntityType](#getentitytype)|String|Returns the entity type of this keyword, which is "Keyword".<br />
[getFirstPageCpc](#getfirstpagecpc)|double|Returns the estimated first page bid for this keyword.<br />
[getId](#getid)|long|Returns the ID of this keyword.<br />
[getMatchType](#getmatchtype)|String|Returns the match type of this keyword. Supported values include:<br /> <br /> BROAD,<br /> PHRASE,<br /> EXACT<br /><br />
[getQualityScore](#getqualityscore)|int|Returns the quality score of this keyword, in the range 1…10.<br />
[getStatsFor(String dateRange)](#getstatsfor~string-daterange~)|String|Returns stats for this keyword for the given date range. Supported values include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH,<br /> ALL_TIME<br /><br />
[getStatsFor(Object dateFrom, Object dateTo)](#getstatsfor~object-datefrom_-object-dateto~)|String|Returns stats for this keyword for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified. <br />
[getText](#gettext)|String|Returns the text of this keyword. The text will be returned in the format as follows, based on the match type of this keyword:<br /> <br /> &nbsp;•	books – broad match<br /> &nbsp;•	"books" – phrase match<br /> &nbsp;•	[origin of species] – exact match<br /><br />
[getTopOfPageCpc](#gettopofpagecpc)|double|Returns the estimated mainline bid for this keyword.<br />
[isEnabled](#isenabled)|boolean|Returns true if this keyword is enabled <br />
[isPaused](#ispaused)|boolean|Returns true if this keyword is paused. <br />
[pause](#pause)|void|Pauses this keyword.<br />
[remove](#remove)|void|Removes this keyword.<br />
[setAdParam(int index, String insertionText)](#setadparam~int-index_-string-insertiontext~)|void|Creates an ad param with the specified insertion text and at the index specified on this keyword. <br />
[urls](#urls)|[KeywordUrls](./KeywordUrls)|Returns the URL fields of this keyword.<br />

## <a name="adparams"></a>adParams
Returns a selector of all ad params under this keyword.


## <a name="cleardestinationurl"></a>clearDestinationUrl
Clears the destination URL of this keyword. 


## <a name="enable"></a>enable
Enables this keyword.


## <a name="getadgroup"></a>getAdGroup
Returns the parent ad group of this keyword.


## <a name="getapprovalstatus"></a>getApprovalStatus
Returns the approval status of this keyword. Supported values include:<br /> <br /> APPROVED,<br /> PENDING_REVIEW,<br /> UNDER_REVIEW,<br /> DISAPPROVED<br />


## <a name="getcampaign"></a>getCampaign
Returns the parent campaign of this keyword.


## <a name="getentitytype"></a>getEntityType
Returns the entity type of this keyword, which is "Keyword".


## <a name="getfirstpagecpc"></a>getFirstPageCpc
Returns the estimated first page bid for this keyword.


## <a name="getid"></a>getId
Returns the ID of this keyword.


## <a name="getmatchtype"></a>getMatchType
Returns the match type of this keyword. Supported values include:<br /> <br /> BROAD,<br /> PHRASE,<br /> EXACT<br />


## <a name="getqualityscore"></a>getQualityScore
Returns the quality score of this keyword, in the range 1…10.


## <a name="getstatsfor~string-daterange~"></a>getStatsFor(String dateRange)
Returns stats for this keyword for the given date range. Supported values include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH,<br /> ALL_TIME<br />


## <a name="getstatsfor~object-datefrom_-object-dateto~"></a>getStatsFor(Object dateFrom, Object dateTo)
Returns stats for this keyword for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified. 


## <a name="gettext"></a>getText
Returns the text of this keyword. The text will be returned in the format as follows, based on the match type of this keyword:<br /> <br /> &nbsp;•	books – broad match<br /> &nbsp;•	"books" – phrase match<br /> &nbsp;•	[origin of species] – exact match<br />


## <a name="gettopofpagecpc"></a>getTopOfPageCpc
Returns the estimated mainline bid for this keyword.


## <a name="isenabled"></a>isEnabled
Returns true if this keyword is enabled 


## <a name="ispaused"></a>isPaused
Returns true if this keyword is paused. 


## <a name="pause"></a>pause
Pauses this keyword.


## <a name="remove"></a>remove
Removes this keyword.


## <a name="setadparam~int-index_-string-insertiontext~"></a>setAdParam(int index, String insertionText)
Creates an ad param with the specified insertion text and at the index specified on this keyword. 


## <a name="urls"></a>urls
Returns the URL fields of this keyword.


