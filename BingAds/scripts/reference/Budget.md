# Budget
Represents a budget in the Bing Ads system.

|Method|Return Type|Description|
|-|-|-
campaigns|[CampaignSelector](./CampaignSelector)|Returns the selector of all campaigns that share this budget.<br />
getAmount|double|Returns the amount of this budget, in the currency of the current account.<br />
getDeliveryMethod|String|Returns the delivery method for this budget. Supported values include:<br /> <br /> STANDARD,<br /> ACCELERATED<br /><br />
getEntityType|String|Returns the entity type of this budget, in this case "Budget".<br />
getId|long|Returns the ID of this budget.<br />
getName|String|Returns the name of this budget.<br />
getStatsFor(String dateRange)|String|Returns stats for this budget for the given date range. Supported values include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH, ALL_TIME<br /><br />
getStatsFor(Object dateFrom, Object dateTo)|String|Returns stats for this budget for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified.<br />
isExplicitlyShared|boolean|Returns true if this budget is shared across two or more campaigns; false otherwise. <br />
setAmount(double amount)|void|Sets the amount of this budget to the specified value, in the currency of the current account.<br />
