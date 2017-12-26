# AdGroup
Represents an ad group in the Bing Ads system.

|Method|Return Type|Description|
|-|-|-
ads|[AdSelector](./AdSelector)|Returns a selector of all the ads under this ad group.<br />
devices|[AdGroupDevices](./AdGroupDevices)|Returns an AdGroupDevices object associated with this ad group.<br />
enable|void|Enables this ad group.<br />
getCampaign|[Campaign](./Campaign)|Returns the parent campaign of this ad group.<br />
getEntityType|String|Returns the entity type of this ad group, which is “Ad Group”.<br />
getId|long|Returns the ID of this ad group.<br />
getName|String|Returns the name of this ad group.<br />
getStatsFor(String dateRange)|String|Returns stats for this ad group for the given date range. Supported values include:<br /> <br /> `TODAY`,<br /> `YESTERDAY`,<br /> `LAST_7_DAYS`,<br /> `THIS_WEEK_SUN_TODAY`,<br /> `LAST_14_DAYS`,<br /> `LAST_30_DAYS`,<br /> `LAST_WEEK_SUN_SAT`,<br /> `THIS_MONTH`,<br /> `LAST_MONTH`,<br /> `ALL_TIME`<br /><br />
getStatsFor(Object dateFrom, Object dateTo)|String|Returns stats for this ad group for the given custom date range. Both parameters can be either a string in `YYYYMMDD` format or an object with year, month and day properties. In either case, a full date must be specified <br />
isEnabled|boolean|Returns true if this ad group is enabled. <br />
isPaused|boolean|Returns true if this ad group is paused. <br />
isRemoved|boolean|Returns true if this ad group is removed. <br />
keywords|[KeywordSelector](./KeywordSelector)|Returns a selector of all the keywords under this ad group.<br />
newAd|[AdBuilderSpace](./AdBuilderSpace)|Returns a new ad builder space associated with this ad group, which can be used to construct the new ad.<br />
newKeywordBuilder|[KeywordBuilder](./KeywordBuilder)|Returns a new keyword builder associated with this ad group, which can be used to construct the new keyword.<br />
pause|void|Pauses this ad group.<br />
setName(String name)|void|Sets the name of this ad group.<br />
urls|[AdGroupUrls](./AdGroupUrls)|Returns an AdGroupUrls object which provides access to the URL fields of this ad group.<br />
