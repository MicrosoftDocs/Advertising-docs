# Budget
Represents a budget in the Bing Ads system.

|Method|Return Type|Description|
|-|-|-
[campaigns]('#campaigns')|[CampaignSelector](./CampaignSelector)|Returns the selector of all campaigns that share this budget.<br />
[getAmount]('#getAmount')|double|Returns the amount of this budget, in the currency of the current account.<br />
[getDeliveryMethod]('#getDeliveryMethod')|String|Returns the delivery method for this budget. Supported values include:<br /> <br /> STANDARD,<br /> ACCELERATED<br /><br />
[getEntityType]('#getEntityType')|String|Returns the entity type of this budget, in this case "Budget".<br />
[getId]('#getId')|long|Returns the ID of this budget.<br />
[getName]('#getName')|String|Returns the name of this budget.<br />
[getStatsFor(String dateRange)]('#getStatsFor-String-dateRange)')|String|Returns stats for this budget for the given date range. Supported values include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH, ALL_TIME<br /><br />
[getStatsFor(Object dateFrom, Object dateTo)]('#getStatsFor-Object-dateFrom_ Object dateTo)')|String|Returns stats for this budget for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified.<br />
[isExplicitlyShared]('#isExplicitlyShared')|boolean|Returns true if this budget is shared across two or more campaigns; false otherwise. <br />
[setAmount(double amount)]('#setAmount-double-amount)')|void|Sets the amount of this budget to the specified value, in the currency of the current account.<br />

<a name="campaigns"></a>
## campaigns
Returns the selector of all campaigns that share this budget.


<a name="getAmount"></a>
## getAmount
Returns the amount of this budget, in the currency of the current account.


<a name="getDeliveryMethod"></a>
## getDeliveryMethod
Returns the delivery method for this budget. Supported values include:<br /> <br /> STANDARD,<br /> ACCELERATED<br />


<a name="getEntityType"></a>
## getEntityType
Returns the entity type of this budget, in this case "Budget".


<a name="getId"></a>
## getId
Returns the ID of this budget.


<a name="getName"></a>
## getName
Returns the name of this budget.


<a name="getStatsFor-String-dateRange)"></a>
## getStatsFor(String dateRange)
Returns stats for this budget for the given date range. Supported values include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH, ALL_TIME<br />


<a name="getStatsFor-Object-dateFrom_ Object dateTo)"></a>
## getStatsFor(Object dateFrom, Object dateTo)
Returns stats for this budget for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified.


<a name="isExplicitlyShared"></a>
## isExplicitlyShared
Returns true if this budget is shared across two or more campaigns; false otherwise. 


<a name="setAmount-double-amount)"></a>
## setAmount(double amount)
Sets the amount of this budget to the specified value, in the currency of the current account.


