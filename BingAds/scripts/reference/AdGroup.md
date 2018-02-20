# AdGroup
Represents an ad group in the Bing Ads system.

Example usage:
```javascript
 var stats = adGroup.getStatsFor("THIS_MONTH");
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[ads](#ads)|[AdSelector](./AdSelector)|Returns a selector of all the ads under this ad group.<br />
[devices](#devices)|[AdGroupDevices](./AdGroupDevices)|Returns an AdGroupDevices object associated with this ad group.<br />
[enable](#enable)|void|Enables this ad group.<br />
[getCampaign](#getcampaign)|[Campaign](./Campaign)|Returns the parent campaign of this ad group.<br />
[getEntityType](#getentitytype)|String|Returns the entity type of this ad group, which is “Ad Group”.<br />
[getId](#getid)|long|Returns the ID of this ad group.<br />
[getName](#getname)|String|Returns the name of this ad group.<br />
[getStatsFor(String dateRange)](#getstatsfor~string-daterange~)|[Stats](./Stats)|Returns a [Stats](./Stats) object for this ad group for the specified predefined date range.
[getStatsFor(Object dateFrom, Object dateTo)](#getstatsfor~object-datefrom_-object-dateto~)|String|Returns stats for this ad group for the given custom date range. Both parameters can be either a string in `YYYYMMDD` format or an object with year, month and day properties. In either case, a full date must be specified <br />
[isEnabled](#isenabled)|boolean|Returns true if this ad group is enabled. <br />
[isPaused](#ispaused)|boolean|Returns true if this ad group is paused. <br />
[isRemoved](#isremoved)|boolean|Returns true if this ad group is removed. <br />
[keywords](#keywords)|[KeywordSelector](./KeywordSelector)|Returns a selector of all the keywords under this ad group.<br />
[newAd](#newad)|[AdBuilderSpace](./AdBuilderSpace)|Returns a new ad builder space associated with this ad group, which can be used to construct the new ad.<br />
[newKeywordBuilder](#newkeywordbuilder)|[KeywordBuilder](./KeywordBuilder)|Returns a new keyword builder associated with this ad group, which can be used to construct the new keyword.<br />
[pause](#pause)|void|Pauses this ad group.<br />
[setName(String name)](#setname~string-name~)|void|Sets the name of this ad group.<br />
[urls](#urls)|[AdGroupUrls](./AdGroupUrls)|Returns an AdGroupUrls object which provides access to the URL fields of this ad group.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="ads"></a>ads
Returns a selector of all the ads under this ad group.


### Returns:
|Type|Description|
|-|-
[AdSelector](./AdSelector)|The selector of all ads in the ad group.
&nbsp;|&nbsp;
## <a name="devices"></a>devices
Returns an AdGroupDevices object associated with this ad group.


### Returns:
|Type|Description|
|-|-
[AdGroupDevices](./AdGroupDevices)|An AdGroupDevices instance associated with the ad group.
&nbsp;|&nbsp;
## <a name="enable"></a>enable
Enables this ad group.


### Returns:
|Type|Description|
|-|-
void|Access to this ad group's extensions.
&nbsp;|&nbsp;
## <a name="getcampaign"></a>getCampaign
Returns the parent campaign of this ad group.


### Returns:
|Type|Description|
|-|-
[Campaign](./Campaign)|The campaign to which this ad group belongs.
&nbsp;|&nbsp;
## <a name="getentitytype"></a>getEntityType
Returns the entity type of this ad group, which is “Ad Group”.


### Returns:
|Type|Description|
|-|-
String|Type of this entity: "AdGroup".
&nbsp;|&nbsp;
## <a name="getid"></a>getId
Returns the ID of this ad group.


### Returns:
|Type|Description|
|-|-
long|The ID of the ad group.
&nbsp;|&nbsp;
## <a name="getname"></a>getName
Returns the name of this ad group.


### Returns:
|Type|Description|
|-|-
String|Name of the ad group.
&nbsp;|&nbsp;
## <a name="getstatsfor~string-daterange~"></a>getStatsFor(String dateRange)
Returns a [Stats](./Stats) object for this ad group for the specified predefined date range.

Supported values for the date range include:<br />  <br /> `TODAY`<br />  `YESTERDAY`<br /> `LAST_7_DAYS`<br /> `THIS_WEEK_SUN_TODAY`<br /> `LAST_14_DAYS`<br /> `LAST_30_DAYS`<br /> `LAST_WEEK_SUN_SAT`<br /> `THIS_MONTH`<br /> `LAST_MONTH`<br /> `ALL_TIME`<br />


### Arguments:
|Name|Type|Description|
|-|-|-
dateRange|String|Predefined date range for which the stats are requested.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[Stats](./Stats)|The [Stats](./Stats) object for the specified predefined date range.
&nbsp;|&nbsp;
## <a name="getstatsfor~object-datefrom_-object-dateto~"></a>getStatsFor(Object dateFrom, Object dateTo)
Returns stats for this ad group for the given custom date range. Both parameters can be either a string in `YYYYMMDD` format or an object with year, month and day properties. In either case, a full date must be specified 


### Arguments:
|Name|Type|Description|
|-|-|-
dateFrom|Object|Start date of the date range. Must be either a string in <code>YYYYMMDD</code> form,<br />                 or an object with <code>year</code>, <code>month</code> and <code>day</code> properties.
dateTo|Object|End date of the date range. Must be either a string in <code>YYYYMMDD</code> form,<br />                 or an object with <code>year</code>, <code>month</code> and <code>day</code> properties.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
String|The stats for the specified date range.
&nbsp;|&nbsp;
## <a name="isenabled"></a>isEnabled
Returns true if this ad group is enabled. 


### Returns:
|Type|Description|
|-|-
boolean|true if the ad group is enabled.
&nbsp;|&nbsp;
## <a name="ispaused"></a>isPaused
Returns true if this ad group is paused. 


### Returns:
|Type|Description|
|-|-
boolean|true if the ad group is paused.
&nbsp;|&nbsp;
## <a name="isremoved"></a>isRemoved
Returns true if this ad group is removed. 


### Returns:
|Type|Description|
|-|-
boolean|true if the ad group is removed.
&nbsp;|&nbsp;
## <a name="keywords"></a>keywords
Returns a selector of all the keywords under this ad group.


### Returns:
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector)|The selector of all keywords in the ad group.
&nbsp;|&nbsp;
## <a name="newad"></a>newAd
Returns a new ad builder space associated with this ad group, which can be used to construct the new ad.


### Returns:
|Type|Description|
|-|-
[AdBuilderSpace](./AdBuilderSpace)|A new ad builder space associated with this ad group.
&nbsp;|&nbsp;
## <a name="newkeywordbuilder"></a>newKeywordBuilder
Returns a new keyword builder associated with this ad group, which can be used to construct the new keyword.


### Returns:
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder)|A new keyword builder associated with this ad group.
&nbsp;|&nbsp;
## <a name="pause"></a>pause
Pauses this ad group.


### Returns:
|Type|Description|
|-|-
void|Access to certain kinds of targeting criteria in this ad group.
&nbsp;|&nbsp;
## <a name="setname~string-name~"></a>setName(String name)
Sets the name of this ad group.


### Arguments:
|Name|Type|Description|
|-|-|-
name|String|The new name for the ad group.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
void|Access to certain kinds of targeting criteria in this ad group.
&nbsp;|&nbsp;
## <a name="urls"></a>urls
Returns an AdGroupUrls object which provides access to the URL fields of this ad group.


### Returns:
|Type|Description|
|-|-
[AdGroupUrls](./AdGroupUrls)|Access to this ad group's URL fields.
&nbsp;|&nbsp;
