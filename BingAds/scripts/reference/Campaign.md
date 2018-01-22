# Campaign
Represents a campaign in the Bing Ads system.

|Method|Return Type|Description|
|-|-|-
[adGroups]('#adGroups}')|[AdGroupSelector](./AdGroupSelector)|Returns the selector of all ad groups under this campaign.<br />
[ads]('#ads}')|[AdSelector](./AdSelector)|Returns the selector of all ads under this campaign.<br />
[enable]('#enable}')|void|Enables this campaign.<br />
[getBudget]('#getBudget}')|[Budget](./Budget)|Returns the budget for this campaign.<br />
[getEntityType]('#getEntityType}')|String|Returns the entity type of this campaign, which is "Campaign".<br />
[getId]('#getId}')|long|Returns the ID of this campaign.<br />
[getName]('#getName}')|String|Returns the name of this campaign.<br />
[getStatsFor(String dateRange)]('#getStatsFor-String-dateRange)}')|String|Returns stats for this campaign for the given date range. Supported values include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH,<br /> ALL_TIME<br /><br />
[getStatsFor(Object dateFrom, Object dateTo)]('#getStatsFor-Object-dateFrom_ Object dateTo)}')|String|Returns stats for this campaign for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified. <br />
[isEnabled]('#isEnabled}')|boolean|Returns true if this campaign is enabled. <br />
[isPaused]('#isPaused}')|boolean|Returns true if this campaign is enabled <br />
[isRemoved]('#isRemoved}')|boolean|Returns true if this campaign is removed. <br />
[keywords]('#keywords}')|[KeywordSelector](./KeywordSelector)|Returns the selector of all keywords under this campaign.<br />
[newAdGroupBuilder]('#newAdGroupBuilder}')|[AdGroupBuilder](./AdGroupBuilder)|Returns the ad group builder for this campaign. After the build() method on the builder is called, the ad group will be created for this campaign.<br />
[pause]('#pause}')|void|Pauses this campaign.<br />
[setName(String name)]('#setName-String-name)}')|void|Sets the name of this campaign.<br />
[urls]('#urls}')|[CampaignUrls](./CampaignUrls)|Returns the URL fields of this campaign.<br />

<a name="#adGroups"></a>
## adGroups
Returns the selector of all ad groups under this campaign.


<a name="#ads"></a>
## ads
Returns the selector of all ads under this campaign.


<a name="#enable"></a>
## enable
Enables this campaign.


<a name="#getBudget"></a>
## getBudget
Returns the budget for this campaign.


<a name="#getEntityType"></a>
## getEntityType
Returns the entity type of this campaign, which is "Campaign".


<a name="#getId"></a>
## getId
Returns the ID of this campaign.


<a name="#getName"></a>
## getName
Returns the name of this campaign.


<a name="#getStatsFor-String-dateRange)"></a>
## getStatsFor(String dateRange)
Returns stats for this campaign for the given date range. Supported values include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH,<br /> ALL_TIME<br />


<a name="#getStatsFor-Object-dateFrom_ Object dateTo)"></a>
## getStatsFor(Object dateFrom, Object dateTo)
Returns stats for this campaign for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified. 


<a name="#isEnabled"></a>
## isEnabled
Returns true if this campaign is enabled. 


<a name="#isPaused"></a>
## isPaused
Returns true if this campaign is enabled 


<a name="#isRemoved"></a>
## isRemoved
Returns true if this campaign is removed. 


<a name="#keywords"></a>
## keywords
Returns the selector of all keywords under this campaign.


<a name="#newAdGroupBuilder"></a>
## newAdGroupBuilder
Returns the ad group builder for this campaign. After the build() method on the builder is called, the ad group will be created for this campaign.


<a name="#pause"></a>
## pause
Pauses this campaign.


<a name="#setName-String-name)"></a>
## setName(String name)
Sets the name of this campaign.


<a name="#urls"></a>
## urls
Returns the URL fields of this campaign.


