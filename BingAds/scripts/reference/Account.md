# Account
Provides information about an account. This is always the current account in which the script is running.

Example usage:
```javascript
var customerId = account.getCustomerId();
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[getCurrencyCode](#getcurrencycode)|String|Returns the account's currency code.
[getCustomerId](#getcustomerid)|String|Returns the customer ID of this account.
[getName](#getname)|String|Returns the name of this account.
[getStatsFor(String dateRange)](#getstatsfor~string-daterange~)|[Stats](./Stats)|Returns a [Stats](./Stats) object for this account for the specified predefined date range.
[getStatsFor(Object dateFrom, Object dateTo)](#getstatsfor~object-datefrom_-object-dateto~)|[Stats](./Stats)|Returns a [Stats](./Stats) object for this account for the specified date range.
[getTimeZone](#gettimezone)|String|Returns the POSIX time-zone value used by the Bing Ads web application to display the account time zone preference. <br />
&nbsp;|&nbsp;|&nbsp;

## <a name="getcurrencycode"></a>getCurrencyCode
Returns the account's currency code. 

The currency code is in ISO 4217 format. For example, USD for U.S. Dollar. See [Bing Ads Currencies](https://docs.microsoft.com/en-us/bingads/guides/currencies) for the full list of supported values. 


### Returns:
|Type|Description|
|-|-
String|The currency code of the account.
&nbsp;|&nbsp;
## <a name="getcustomerid"></a>getCustomerId
Returns the customer ID of this account.
### Returns:
|Type|Description|
|-|-
String|The customer ID of the account.
&nbsp;|&nbsp;
## <a name="getname"></a>getName
Returns the name of this account.
### Returns:
|Type|Description|
|-|-
String|The account descriptive name, or null if one doesn't exist.
&nbsp;|&nbsp;
## <a name="getstatsfor~string-daterange~"></a>getStatsFor(String dateRange)
Returns a [Stats](./Stats) object for this account for the specified predefined date range.

Supported date range values:

- TODAY
- YESTERDAY
- LAST_7_DAYS
- THIS_WEEK_SUN_TODAY
- LAST_14_DAYS
- LAST_30_DAYS
- LAST_WEEK_SUN_SAT
- THIS_MONTH
- LAST_MONTH
- ALL_TIME

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
Returns a [Stats](./Stats) object for this account for the specified date range.

You may specify the date parameters using strings or objects. To use strings, specify the date in the form, YYYYMMDD. If you use objects, create a JSON object with the following fields:

- year
- month
- day

For example, {year: 2016, month: 5, day: 13}.

### Arguments:
|Name|Type|Description|
|-|-|-
dateFrom|Object|Start date of the date range.
dateTo|Object|End date of the date range.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[Stats](./Stats)|The stats for the specified date range.
&nbsp;|&nbsp;
## <a name="gettimezone"></a>getTimeZone
Returns the POSIX time-zone value used by the Bing Ads web application to display the account time zone preference. 

### Returns:
|Type|Description|
|-|-
String|The time zone of the account.
&nbsp;|&nbsp;
