# ExpandedTextAd
Represents an expanded text ad in the Bing Ads system.

|Method|Return Type|Description|
|-|-|-
asType|[AdViewSpace](./AdViewSpace)|Returns an AdViewSpace object, which provides access to properties specific to the type of this ad.<br />
enable|void|Enables the ad.<br />
getAdGroup|[AdGroup](./AdGroup)|Returns the parent ad group of this ad.<br />
getApprovalStatus|String|Returns the approval status of this ad. Supported values include:<br /> <br /> APPROVED,<br /> DISAPPROVED<br /><br />
getCampaign|[Campaign](./Campaign)|Returns the parent campaign of this ad.<br />
getDescription|String|Returns the description of this ad.<br />
getDisapprovalReasons|String[]|Returns an array containing the reasons for which this ad was disapproved. If it is not disapproved, the array will be empty.<br />
getEntityType|String|Returns the type of entity of this ad, which is “Ad”.<br />
getHeadlinePart1|String|Returns the first part of the headline (title) of this ad. <br />
getHeadlinePart2|String|Returns the second part of the headline (title) of this ad. <br />
getId|long|Returns the ID of this ad. In order to specify a unique ID for an ad, both its ad group ID and this ID need to be specified. <br />
getPath1|String|Returns the first path that appears with this ad's display URL.<br />
getPath2|String|Returns the second path that appears with this ad's display URL.<br />
getStatsFor(String dateRange)|String|Returns stats for this ad for the given date range. Supported values include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH,<br /> ALL_TIME<br /><br />
getStatsFor(Object dateFrom, Object dateTo)|String|Returns stats for this ad for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified. <br />
getType|String|Returns the type of this ad. Supported values include:<br /> <br /> EXPANDED_TEXT_AD and TEXT_AD<br /><br />
isEnabled|boolean|Returns true if this ad is enabled. <br />
isPaused|boolean|Returns true if this ad is paused <br />
isType|[AdTypeSpace](./AdTypeSpace)|Returns an AdTypeSpace object which provides more information on the type of this ad.<br />
pause|void|Pauses this ad.<br />
remove|void|Removes this ad.<br />
urls|[AdUrls](./AdUrls)|Returns an AdUrls object which provides access to the URL fields of this <br />
