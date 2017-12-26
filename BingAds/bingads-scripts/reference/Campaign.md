# Campaign
Represents a campaign in the Bing Ads system.

|Method|Return Type|Description|
|-|-|-
adGroups|[AdGroupSelector](./AdGroupSelector)|Returns the selector of all ad groups under this campaign.<br />
ads|[AdSelector](./AdSelector)|Returns the selector of all ads under this campaign.<br />
enable|void|Enables this campaign.<br />
getBudget|[Budget](./Budget)|Returns the budget for this campaign.<br />
getEntityType|String|Returns the entity type of this campaign, which is "Campaign".<br />
getId|long|Returns the ID of this campaign.<br />
getName|String|Returns the name of this campaign.<br />
getStatsFor(String dateRange)|String|Returns stats for this campaign for the given date range. Supported values include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH,<br /> ALL_TIME<br /><br />
getStatsFor(Object dateFrom, Object dateTo)|String|Returns stats for this campaign for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified. <br />
isEnabled|boolean|Returns true if this campaign is enabled. <br />
isPaused|boolean|Returns true if this campaign is enabled <br />
isRemoved|boolean|Returns true if this campaign is removed. <br />
keywords|[KeywordSelector](./KeywordSelector)|Returns the selector of all keywords under this campaign.<br />
newAdGroupBuilder|[AdGroupBuilder](./AdGroupBuilder)|Returns the ad group builder for this campaign. After the build() method on the builder is called, the ad group will be created for this campaign.<br />
pause|void|Pauses this campaign.<br />
setName(String name)|void|Sets the name of this campaign.<br />
urls|[CampaignUrls](./CampaignUrls)|Returns the URL fields of this campaign.<br />
