# Keyword
Represents a keyword in the Bing Ads system.

|Method|Return Type|Description|
|-|-|-
adParams|[AdParamSelector](./AdParamSelector)|Returns a selector of all ad params under this keyword.<br />
clearDestinationUrl|void|Clears the destination URL of this keyword. <br />
enable|void|Enables this keyword.<br />
getAdGroup|[AdGroup](AdGroup)|Returns the parent ad group of this keyword.<br />
getApprovalStatus|String|Returns the approval status of this keyword. Supported values include:<br /> <br /> APPROVED,<br /> PENDING_REVIEW,<br /> UNDER_REVIEW,<br /> DISAPPROVED<br /><br />
getCampaign|[Campaign](./Campaign)|Returns the parent campaign of this keyword.<br />
getEntityType|String|Returns the entity type of this keyword, which is "Keyword".<br />
getFirstPageCpc|double|Returns the estimated first page bid for this keyword.<br />
getId|long|Returns the ID of this keyword.<br />
getMatchType|String|Returns the match type of this keyword. Supported values include:<br /> <br /> BROAD,<br /> PHRASE,<br /> EXACT<br /><br />
getQualityScore|int|Returns the quality score of this keyword, in the range 1…10.<br />
getStatsFor(String dateRange)|String|Returns stats for this keyword for the given date range. Supported values include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH,<br /> ALL_TIME<br /><br />
getStatsFor(Object dateFrom, Object dateTo)|String|Returns stats for this keyword for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified. <br />
getText|String|Returns the text of this keyword. The text will be returned in the format as follows, based on the match type of this keyword:<br /> <br /> &nbsp;•	books – broad match<br /> &nbsp;•	"books" – phrase match<br /> &nbsp;•	[origin of species] – exact match<br /><br />
getTopOfPageCpc|double|Returns the estimated mainline bid for this keyword.<br />
isEnabled|boolean|Returns true if this keyword is enabled <br />
isPaused|boolean|Returns true if this keyword is paused. <br />
pause|void|Pauses this keyword.<br />
remove|void|Removes this keyword.<br />
setAdParam(int index, String insertionText)|void|Creates an ad param with the specified insertion text and at the index specified on this keyword. <br />
urls|[KeywordUrls](./KeywordUrls)|Returns the URL fields of this keyword.<br />
