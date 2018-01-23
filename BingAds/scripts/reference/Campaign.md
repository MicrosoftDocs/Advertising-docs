# Campaign
Represents a campaign in the Bing Ads system.

|Method|Return Type|Description|
|-|-|-
[adGroups]("#adgroups")|[AdGroupSelector](./AdGroupSelector)|Returns the selector of all ad groups under this campaign.<br />
[ads]("#ads")|[AdSelector](./AdSelector)|Returns the selector of all ads under this campaign.<br />
[enable]("#enable")|void|Enables this campaign.<br />
[getBudget]("#getbudget")|[Budget](./Budget)|Returns the budget for this campaign.<br />
[getEntityType]("#getentitytype")|String|Returns the entity type of this campaign, which is "Campaign".<br />
[getId]("#getid")|long|Returns the ID of this campaign.<br />
[getName]("#getname")|String|Returns the name of this campaign.<br />
[getStatsFor(String dateRange)]("#getstatsfor~string-daterange~")|String|Returns stats for this campaign for the given date range. Supported values include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH,<br /> ALL_TIME<br /><br />
[getStatsFor(Object dateFrom, Object dateTo)]("#getstatsfor~object-datefrom_-object-dateto~")|String|Returns stats for this campaign for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified. <br />
[isEnabled]("#isenabled")|boolean|Returns true if this campaign is enabled. <br />
[isPaused]("#ispaused")|boolean|Returns true if this campaign is enabled <br />
[isRemoved]("#isremoved")|boolean|Returns true if this campaign is removed. <br />
[keywords]("#keywords")|[KeywordSelector](./KeywordSelector)|Returns the selector of all keywords under this campaign.<br />
[newAdGroupBuilder]("#newadgroupbuilder")|[AdGroupBuilder](./AdGroupBuilder)|Returns the ad group builder for this campaign. After the build() method on the builder is called, the ad group will be created for this campaign.<br />
[pause]("#pause")|void|Pauses this campaign.<br />
[setName(String name)]("#setname~string-name~")|void|Sets the name of this campaign.<br />
[urls]("#urls")|[CampaignUrls](./CampaignUrls)|Returns the URL fields of this campaign.<br />

## <a name="adgroups"></a>adGroups
Returns the selector of all ad groups under this campaign.


## <a name="ads"></a>ads
Returns the selector of all ads under this campaign.


## <a name="enable"></a>enable
Enables this campaign.


## <a name="getbudget"></a>getBudget
Returns the budget for this campaign.


## <a name="getentitytype"></a>getEntityType
Returns the entity type of this campaign, which is "Campaign".


## <a name="getid"></a>getId
Returns the ID of this campaign.


## <a name="getname"></a>getName
Returns the name of this campaign.


## <a name="getstatsfor~string-daterange~"></a>getStatsFor(String dateRange)
Returns stats for this campaign for the given date range. Supported values include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH,<br /> ALL_TIME<br />


## <a name="getstatsfor~object-datefrom_-object-dateto~"></a>getStatsFor(Object dateFrom, Object dateTo)
Returns stats for this campaign for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified. 


## <a name="isenabled"></a>isEnabled
Returns true if this campaign is enabled. 


## <a name="ispaused"></a>isPaused
Returns true if this campaign is enabled 


## <a name="isremoved"></a>isRemoved
Returns true if this campaign is removed. 


## <a name="keywords"></a>keywords
Returns the selector of all keywords under this campaign.


## <a name="newadgroupbuilder"></a>newAdGroupBuilder
Returns the ad group builder for this campaign. After the build() method on the builder is called, the ad group will be created for this campaign.


## <a name="pause"></a>pause
Pauses this campaign.


## <a name="setname~string-name~"></a>setName(String name)
Sets the name of this campaign.


## <a name="urls"></a>urls
Returns the URL fields of this campaign.


