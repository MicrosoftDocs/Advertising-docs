# Budget
Represents a budget in the Bing Ads system.

Example usage:
```javascript
 var stats = budget.getStatsFor("THIS_MONTH");
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[campaigns](#campaigns)|[CampaignSelector](./CampaignSelector)|Returns the selector of all campaigns that share this budget.<br />
[getAmount](#getamount)|double|Returns the amount of this budget, in the currency of the current account.<br />
[getDeliveryMethod](#getdeliverymethod)|String|Returns the delivery method for this budget. Supported values include:<br /> <br /> `STANDARD`<br /> `ACCELERATED`<br /><br />
[getEntityType](#getentitytype)|String|Returns the entity type of this budget, in this case "Budget".<br />
[getId](#getid)|long|Returns the ID of this budget.<br />
[getName](#getname)|String|Returns the name of this budget.<br />
[getStatsFor(String dateRange)](#getstatsfor~string-daterange~)|String|Returns stats for this budget for the given date range. Supported values include:<br /> <br /> `TODAY`<br /> `YESTERDAY`<br /> `LAST_7_DAYS`<br /> `THIS_WEEK_SUN_TODAY`<br /> `LAST_14_DAYS`<br /> `LAST_30_DAYS`<br /> `LAST_WEEK_SUN_SAT`<br /> `THIS_MONTH`<br /> `LAST_MONTH`<br /> `ALL_TIME`<br /><br />
[getStatsFor(Object dateFrom, Object dateTo)](#getstatsfor~object-datefrom_-object-dateto~)|String|Returns stats for this budget for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified.<br />
[isExplicitlyShared](#isexplicitlyshared)|boolean|Returns true if this budget is shared across two or more campaigns; false otherwise. <br />
[setAmount(double amount)](#setamount~double-amount~)|void|Sets the amount of this budget to the specified value, in the currency of the current account.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="campaigns"></a>campaigns
Returns the selector of all campaigns that share this budget.

### Returns:
|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector)|Selector of all campaigns that share this budget.
&nbsp;|&nbsp;
## <a name="getamount"></a>getAmount
Returns the amount of this budget, in the currency of the current account.

### Returns:
|Type|Description|
|-|-
double|Amount of the budget.
&nbsp;|&nbsp;
## <a name="getdeliverymethod"></a>getDeliveryMethod
Returns the delivery method for this budget. Supported values include:<br /> <br /> `STANDARD`<br /> `ACCELERATED`<br />

### Returns:
|Type|Description|
|-|-
String|Delivery method of the budget.
&nbsp;|&nbsp;
## <a name="getentitytype"></a>getEntityType
Returns the entity type of this budget, in this case "Budget".

### Returns:
|Type|Description|
|-|-
String|Type of this entity: "Budget".
&nbsp;|&nbsp;
## <a name="getid"></a>getId
Returns the ID of this budget.

### Returns:
|Type|Description|
|-|-
long|The ID of the budget.
&nbsp;|&nbsp;
## <a name="getname"></a>getName
Returns the name of this budget.

### Returns:
|Type|Description|
|-|-
String|Name of the budget.
&nbsp;|&nbsp;
## <a name="getstatsfor~string-daterange~"></a>getStatsFor(String dateRange)
Returns stats for this budget for the given date range. Supported values include:<br /> <br /> `TODAY`<br /> `YESTERDAY`<br /> `LAST_7_DAYS`<br /> `THIS_WEEK_SUN_TODAY`<br /> `LAST_14_DAYS`<br /> `LAST_30_DAYS`<br /> `LAST_WEEK_SUN_SAT`<br /> `THIS_MONTH`<br /> `LAST_MONTH`<br /> `ALL_TIME`<br />

### Arguments:
|Name|Type|Description|
|-|-|-
dateRange|String|Date range for which the stats are requested.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
String|The stats for the specified date range.
&nbsp;|&nbsp;
## <a name="getstatsfor~object-datefrom_-object-dateto~"></a>getStatsFor(Object dateFrom, Object dateTo)
Returns stats for this budget for the given custom date range. Both parameters can be either a string in YYYYMMDD format or an object with year, month and day properties. In either case, a full date must be specified.

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
## <a name="isexplicitlyshared"></a>isExplicitlyShared
Returns true if this budget is shared across two or more campaigns; false otherwise. 

### Returns:
|Type|Description|
|-|-
boolean|true if the budget is explicitly shared.
&nbsp;|&nbsp;
## <a name="setamount~double-amount~"></a>setAmount(double amount)
Sets the amount of this budget to the specified value, in the currency of the current account.

### Arguments:
|Name|Type|Description|
|-|-|-
amount|double|The amount of the budget.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
void|
&nbsp;|&nbsp;
