# Keyword
Represents a keyword in the Bing Ads system.

Example usage:
```javascript
 var stats = keyword.getStatsFor("THIS_MONTH");
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[adParams](#adparams)|[AdParamSelector](./AdParamSelector)|Returns a selector of all ad params under this keyword.<br />
[clearDestinationUrl](#cleardestinationurl)|void|Clears the destination URL of this keyword. <br />
[enable](#enable)|void|Enables this keyword.<br />
[getAdGroup](#getadgroup)|[AdGroup](AdGroup)|Returns the parent ad group of this keyword.<br />
[getApprovalStatus](#getapprovalstatus)|String|Returns the approval status of the keyword.
[getCampaign](#getcampaign)|[Campaign](./Campaign)|Returns the parent campaign of this keyword.<br />
[getEntityType](#getentitytype)|String|Returns the entity type of this keyword, which is "Keyword".<br />
[getFirstPageCpc](#getfirstpagecpc)|double|Returns the estimated first page bid for this keyword.<br />
[getId](#getid)|long|Returns the ID of this keyword.<br />
[getMatchType](#getmatchtype)|String|Returns the match type of this keyword. Supported values include:<br /> <br /> `BROAD`<br /> `PHRASE`<br /> `EXACT`<br /><br />
[getQualityScore](#getqualityscore)|int|Returns the quality score of this keyword, in the range 1…10.<br />
[getStatsFor(String dateRange)](#getstatsfor~string-daterange~)|[Stats](./Stats)|Returns a [Stats](./Stats) object for this keyword for the specified predefined date range.
[getStatsFor(Object dateFrom, Object dateTo)](#getstatsfor~object-datefrom_-object-dateto~)|[Stats](./Stats)|Returns a [Stats](./Stats) object for this keyword for the specified date range.
[getText](#gettext)|String|Returns the text of this keyword. The text will be returned in the format as follows, based on the match type of this keyword:<br /> <br /> &nbsp;•	books – broad match<br /> &nbsp;•	"books" – phrase match<br /> &nbsp;•	[origin of species] – exact match<br /><br />
[getTopOfPageCpc](#gettopofpagecpc)|double|Returns the estimated mainline bid for this keyword.<br />
[isEnabled](#isenabled)|boolean|Returns true if this keyword is enabled <br />
[isPaused](#ispaused)|boolean|Returns true if this keyword is paused. <br />
[pause](#pause)|void|Pauses this keyword.<br />
[remove](#remove)|void|Removes this keyword.<br />
[setAdParam(int index, String insertionText)](#setadparam~int-index_-string-insertiontext~)|void|Creates an ad param with the specified insertion text and at the index specified on this keyword. <br />
[urls](#urls)|[KeywordUrls](./KeywordUrls)|Returns the URL fields of this keyword.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="adparams"></a>adParams
Returns a selector of all ad params under this keyword.

### Returns:
|Type|Description|
|-|-
[AdParamSelector](./AdParamSelector)|Selector of all ad params belonging to this keyword.
&nbsp;|&nbsp;
## <a name="cleardestinationurl"></a>clearDestinationUrl
Clears the destination URL of this keyword. 

### Returns:
|Type|Description|
|-|-
void|The ad group to which this keyword belongs.
&nbsp;|&nbsp;
## <a name="enable"></a>enable
Enables this keyword.

### Returns:
|Type|Description|
|-|-
void|The ad group to which this keyword belongs.
&nbsp;|&nbsp;
## <a name="getadgroup"></a>getAdGroup
Returns the parent ad group of this keyword.

### Returns:
|Type|Description|
|-|-
[AdGroup](AdGroup)|The ad group to which this keyword belongs.
&nbsp;|&nbsp;
## <a name="getapprovalstatus"></a>getApprovalStatus
Returns the approval status of the keyword. 

Possible values:

- APPROVED
- PENDING_REVIEW
- UNDER_REVIEW
- DISAPPROVED

### Returns:
|Type|Description|
|-|-
String|The approval status of the keyword.
&nbsp;|&nbsp;
## <a name="getcampaign"></a>getCampaign
Returns the parent campaign of this keyword.

### Returns:
|Type|Description|
|-|-
[Campaign](./Campaign)|The campaign to which this keyword belongs.
&nbsp;|&nbsp;
## <a name="getentitytype"></a>getEntityType
Returns the entity type of this keyword, which is "Keyword".

### Returns:
|Type|Description|
|-|-
String|Type of this entity: "Keyword".
&nbsp;|&nbsp;
## <a name="getfirstpagecpc"></a>getFirstPageCpc
Returns the estimated first page bid for this keyword.

### Returns:
|Type|Description|
|-|-
double|The first page cpc for the keyword.
&nbsp;|&nbsp;
## <a name="getid"></a>getId
Returns the ID of this keyword.

### Returns:
|Type|Description|
|-|-
long|The ID of the keyword.
&nbsp;|&nbsp;
## <a name="getmatchtype"></a>getMatchType
Returns the match type of this keyword. Supported values include:<br /> <br /> `BROAD`<br /> `PHRASE`<br /> `EXACT`<br />

### Returns:
|Type|Description|
|-|-
String|The match type of the keyword.
&nbsp;|&nbsp;
## <a name="getqualityscore"></a>getQualityScore
Returns the quality score of this keyword, in the range 1…10.

### Returns:
|Type|Description|
|-|-
int|The quality score of the keyword.
&nbsp;|&nbsp;
## <a name="getstatsfor~string-daterange~"></a>getStatsFor(String dateRange)
Returns a [Stats](./Stats) object for this keyword for the specified predefined date range.

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
dateRange|String|Date range for which the stats are requested.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[Stats](./Stats)|The stats for the specified date range.
&nbsp;|&nbsp;
## <a name="getstatsfor~object-datefrom_-object-dateto~"></a>getStatsFor(Object dateFrom, Object dateTo)
Returns a [Stats](./Stats) object for this keyword for the specified date range.

You may specify the date parameters using strings or objects. To use strings, specify the date in the form, YYYYMMDD. If you use objects, create a JSON object with the following fields:

year
month
day
For example, {year: 2016, month: 5, day: 13}.

### Arguments:
|Name|Type|Description|
|-|-|-
dateFrom|Object|Start date of the date range. Must be either a string in <code>YYYYMMDD</code> form,<br />                 or an object with <code>year</code>, <code>month</code> and <code>day</code> properties.
dateTo|Object|End date of the date range. Must be either a string in <code>YYYYMMDD</code> form,<br />                 or an object with <code>year</code>, <code>month</code> and <code>day</code> properties.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[Stats](./Stats)|The stats for the specified date range.
&nbsp;|&nbsp;
## <a name="gettext"></a>getText
Returns the text of this keyword. The text will be returned in the format as follows, based on the match type of this keyword:<br /> <br /> &nbsp;•	books – broad match<br /> &nbsp;•	"books" – phrase match<br /> &nbsp;•	[origin of species] – exact match<br />

### Returns:
|Type|Description|
|-|-
String|The text of the keyword.
&nbsp;|&nbsp;
## <a name="gettopofpagecpc"></a>getTopOfPageCpc
Returns the estimated mainline bid for this keyword.

### Returns:
|Type|Description|
|-|-
double|The top of page cpc for the keyword.
&nbsp;|&nbsp;
## <a name="isenabled"></a>isEnabled
Returns true if this keyword is enabled 

### Returns:
|Type|Description|
|-|-
boolean|true if the keyword is enabled.
&nbsp;|&nbsp;
## <a name="ispaused"></a>isPaused
Returns true if this keyword is paused. 

### Returns:
|Type|Description|
|-|-
boolean|true if the keyword is paused.
&nbsp;|&nbsp;
## <a name="pause"></a>pause
Pauses this keyword.

### Returns:
|Type|Description|
|-|-
void|Access to this keyword's URL fields.
&nbsp;|&nbsp;
## <a name="remove"></a>remove
Removes this keyword.

### Returns:
|Type|Description|
|-|-
void|Access to this keyword's URL fields.
&nbsp;|&nbsp;
## <a name="setadparam~int-index_-string-insertiontext~"></a>setAdParam(int index, String insertionText)
Creates an ad param with the specified insertion text and at the index specified on this keyword. 

### Arguments:
|Name|Type|Description|
|-|-|-
index|int|Defines which parameterized snippet of ad text to replace. For example,<br />                      a value of <code>1</code> indicates a replacement for the <code>{param1:default-value} </code> token. This field equals either <code>1</code> and
                      <code>2</code>.
insertionText|String|Numeric value to insert into the ad text.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
void|Access to this keyword's URL fields.
&nbsp;|&nbsp;
## <a name="urls"></a>urls
Returns the URL fields of this keyword.

### Returns:
|Type|Description|
|-|-
[KeywordUrls](./KeywordUrls)|Access to this keyword's URL fields.
&nbsp;|&nbsp;
