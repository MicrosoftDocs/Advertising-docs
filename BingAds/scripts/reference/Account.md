# Account
Provides information about an account. This is always the current account in which the script is running.

|Method|Return Type|Description|
|-|-|-
getCurrencyCode|String|Returns the account's currency code. The return value is in ISO 4217 format. For example, USD for U.S. Dollar. See [Bing Ads Currencies](https://docs.microsoft.com/en-us/bingads/guides/currencies) for the full list of supported values. <br />
getCustomerId|String|Returns the customer ID of this account.
getName|String|Returns the name of this account.
getStatsFor(String dateRange)|String|Returns stats for this account for the given date range.<br />Supported values include:<br /><br /> `TODAY`,<br /> `YESTERDAY`,<br /> `LAST_7_DAYS`,<br /> `THIS_WEEK_SUN_TODAY`,<br /> `LAST_14_DAYS`,<br /> `LAST_30_DAYS`,<br /> `LAST_WEEK_SUN_SAT`,<br /> `THIS_MONTH`,<br /> `LAST_MONTH`,<br /> `ALL_TIME`<br />
getStatsFor(Object dateFrom, Object dateTo)|String|Returns stats for this account for the given custom date range. Both parameters can be either a  string in `YYYYMMDD` format or an object with year, month and day properties. In either case, a full date must be specified<br />
getTimeZone|String|Returns the POSIX time-zone value used by the Bing Ads web application to display the account time zone preference. <br />
