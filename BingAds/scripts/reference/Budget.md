# Budget
Represents a budget in the Bing Ads system.

|Method|Return Type|Description|
|-|-|-
[campaigns]('#campaigns')|[CampaignSelector](./CampaignSelector)|Returns the selector of all campaigns that share this budget.<br />
[getAmount]('#getamount')|double|Returns the amount of this budget, in the currency of the current account.<br />
[getDeliveryMethod]('#getdeliverymethod')|String|Returns the delivery method for this budget. Supported values include:<br /> <br /> STANDARD,<br /> ACCELERATED<br /><br />
[getEntityType]('#getentitytype')|String|Returns the entity type of this budget, in this case "Budget".<br />
[getId]('#getid')|long|Returns the ID of this budget.<br />
[getName]('#getname')|String|Returns the name of this budget.<br />
[getStatsFor(String dateRange)]('#getstatsfor~string-daterange~')|String|Returns stats for this budget for the given date range. Supported values include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH, ALL_TIME<br /><br />
[getStatsFor(Object dateFrom, Object dateTo)]('#getstatsfor~object-datefrom_-object-dateto~')|String|Returns stats for this budget for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified.<br />
[isExplicitlyShared]('#isexplicitlyshared')|boolean|Returns true if this budget is shared across two or more campaigns; false otherwise. <br />
[setAmount(double amount)]('#setamount~double-amount~')|void|Sets the amount of this budget to the specified value, in the currency of the current account.<br />

## <a name="campaigns"></a>campaigns
Returns the selector of all campaigns that share this budget.


## <a name="getamount"></a>getAmount
Returns the amount of this budget, in the currency of the current account.


## <a name="getdeliverymethod"></a>getDeliveryMethod
Returns the delivery method for this budget. Supported values include:<br /> <br /> STANDARD,<br /> ACCELERATED<br />


## <a name="getentitytype"></a>getEntityType
Returns the entity type of this budget, in this case "Budget".


## <a name="getid"></a>getId
Returns the ID of this budget.


## <a name="getname"></a>getName
Returns the name of this budget.


## <a name="getstatsfor~string-daterange~"></a>getStatsFor(String dateRange)
Returns stats for this budget for the given date range. Supported values include:<br /> <br /> TODAY,<br /> YESTERDAY,<br /> LAST_7_DAYS,<br /> THIS_WEEK_SUN_TODAY,<br /> LAST_14_DAYS,<br /> LAST_30_DAYS,<br /> LAST_WEEK_SUN_SAT,<br /> THIS_MONTH,<br /> LAST_MONTH, ALL_TIME<br />


## <a name="getstatsfor~object-datefrom_-object-dateto~"></a>getStatsFor(Object dateFrom, Object dateTo)
Returns stats for this budget for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified.


## <a name="isexplicitlyshared"></a>isExplicitlyShared
Returns true if this budget is shared across two or more campaigns; false otherwise. 


## <a name="setamount~double-amount~"></a>setAmount(double amount)
Sets the amount of this budget to the specified value, in the currency of the current account.


