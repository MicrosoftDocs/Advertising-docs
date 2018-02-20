# Campaign
Represents a campaign in the Bing Ads system.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[adGroups](#adgroups)|[AdGroupSelector](./AdGroupSelector)|Returns the selector of all ad groups under this campaign.<br />
[ads](#ads)|[AdSelector](./AdSelector)|Returns the selector of all ads under this campaign.<br />
[enable](#enable)|void|Enables this campaign.<br />
[getBudget](#getbudget)|[Budget](./Budget)|Returns the budget for this campaign.<br />
[getEntityType](#getentitytype)|String|Returns the entity type of this campaign, which is "Campaign".<br />
[getId](#getid)|long|Returns the ID of this campaign.<br />
[getName](#getname)|String|Returns the name of this campaign.<br />
[getStatsFor(String dateRange)](#getstatsfor~string-daterange~)|[Stats](./Stats)|Returns stats for this campaign for the given date range. Supported values include:<br /> <br /> `TODAY`<br /> `YESTERDAY`<br /> `LAST_7_DAYS`<br /> `THIS_WEEK_SUN_TODAY`<br /> `LAST_14_DAYS`<br /> `LAST_30_DAYS`<br /> `LAST_WEEK_SUN_SAT`<br /> `THIS_MONTH`<br /> `LAST_MONTH`<br /> `ALL_TIME`<br /><br />
[getStatsFor(Object dateFrom, Object dateTo)](#getstatsfor~object-datefrom_-object-dateto~)|String|Returns stats for this campaign for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified. <br />
[isEnabled](#isenabled)|boolean|Returns true if this campaign is enabled. <br />
[isPaused](#ispaused)|boolean|Returns true if this campaign is enabled <br />
[isRemoved](#isremoved)|boolean|Returns true if this campaign is removed. <br />
[keywords](#keywords)|[KeywordSelector](./KeywordSelector)|Returns the selector of all keywords under this campaign.<br />
[newAdGroupBuilder](#newadgroupbuilder)|[AdGroupBuilder](./AdGroupBuilder)|Returns the ad group builder for this campaign. After the build() method on the builder is called, the ad group will be created for this campaign.<br />
[pause](#pause)|void|Pauses this campaign.<br />
[setName(String name)](#setname~string-name~)|void|Sets the name of this campaign.<br />
[urls](#urls)|[CampaignUrls](./CampaignUrls)|Returns the URL fields of this campaign.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="adgroups"></a>adGroups
Returns the selector of all ad groups under this campaign.

### Returns:
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector)|The selector of all ad groups in the campaign.
&nbsp;|&nbsp;
## <a name="ads"></a>ads
Returns the selector of all ads under this campaign.

### Returns:
|Type|Description|
|-|-
[AdSelector](./AdSelector)|The selector of all ads in the campaign.
&nbsp;|&nbsp;
## <a name="enable"></a>enable
Enables this campaign.

### Returns:
|Type|Description|
|-|-
void|The associated excluded location operation.
&nbsp;|&nbsp;
## <a name="getbudget"></a>getBudget
Returns the budget for this campaign.

### Returns:
|Type|Description|
|-|-
[Budget](./Budget)|Budget of the campaign.
&nbsp;|&nbsp;
## <a name="getentitytype"></a>getEntityType
Returns the entity type of this campaign, which is "Campaign".

### Returns:
|Type|Description|
|-|-
String|Type of this entity: "Campaign".
&nbsp;|&nbsp;
## <a name="getid"></a>getId
Returns the ID of this campaign.

### Returns:
|Type|Description|
|-|-
long|The ID of the campaign.
&nbsp;|&nbsp;
## <a name="getname"></a>getName
Returns the name of this campaign.

### Returns:
|Type|Description|
|-|-
String|Name of the campaign.
&nbsp;|&nbsp;
## <a name="getstatsfor~string-daterange~"></a>getStatsFor(String dateRange)
Returns stats for this campaign for the given date range. Supported values include:<br /> <br /> `TODAY`<br /> `YESTERDAY`<br /> `LAST_7_DAYS`<br /> `THIS_WEEK_SUN_TODAY`<br /> `LAST_14_DAYS`<br /> `LAST_30_DAYS`<br /> `LAST_WEEK_SUN_SAT`<br /> `THIS_MONTH`<br /> `LAST_MONTH`<br /> `ALL_TIME`<br />

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
Returns stats for this campaign for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified. 

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
Returns true if this campaign is enabled. 

### Returns:
|Type|Description|
|-|-
boolean|true if the campaign is enabled.
&nbsp;|&nbsp;
## <a name="ispaused"></a>isPaused
Returns true if this campaign is enabled 

### Returns:
|Type|Description|
|-|-
boolean|true if the campaign is paused.
&nbsp;|&nbsp;
## <a name="isremoved"></a>isRemoved
Returns true if this campaign is removed. 

### Returns:
|Type|Description|
|-|-
boolean|true if the campaign is removed.
&nbsp;|&nbsp;
## <a name="keywords"></a>keywords
Returns the selector of all keywords under this campaign.

### Returns:
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector)|The selector of all keywords in the campaign.
&nbsp;|&nbsp;
## <a name="newadgroupbuilder"></a>newAdGroupBuilder
Returns the ad group builder for this campaign. After the build() method on the builder is called, the ad group will be created for this campaign.

### Returns:
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder)|Ad group builder.
&nbsp;|&nbsp;
## <a name="pause"></a>pause
Pauses this campaign.

### Returns:
|Type|Description|
|-|-
void|Access to certain kinds of targeting criteria in this campaign.
&nbsp;|&nbsp;
## <a name="setname~string-name~"></a>setName(String name)
Sets the name of this campaign.

### Arguments:
|Name|Type|Description|
|-|-|-
name|String|The new name for the campaign.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
void|Access to certain kinds of targeting criteria in this campaign.
&nbsp;|&nbsp;
## <a name="urls"></a>urls
Returns the URL fields of this campaign.

### Returns:
|Type|Description|
|-|-
[CampaignUrls](./CampaignUrls)|Access to this campaign's URL fields.
&nbsp;|&nbsp;
