# BingAdsAccountSelector
Provides methods for selecting accounts. For information about Selectors, see [Selectors](../concepts/selectors).
# Methods
|Method Name|Return Type|Description|
|-|-|-
[executeInParallel(String functionName, String optionalCallbackFunctionName)](#executeinparallel~string-functionname_-string-optionalcallbackfunctionname~)|void|Executes the function indicated by functionName on each BingAdsAccount matched by this selector and optionally invokes the callback function indicated by optionalCallbackFunctionName.
[executeInParallel(String functionName, String optionalCallbackFunctionName, String optionalInput)](#executeinparallel~string-functionname_-string-optionalcallbackfunctionname_-string-optionalinput~)|void|Executes the function indicated by functionName on each BingAdsAccount matched by this selector and optionally invokes the callback function indicated by optionalCallbackFunctionName. The optional optionalInput argument will be used in the parallel function execution, if specified.
[get](#get)|[BingAdsAccountIterator](./BingAdsAccountIterator)|Returns an account iterator based on the selector's selection criteria.
[orderBy(String orderBy)](#orderby~string-orderby~)|[BingAdsAccountSelector](./BingAdsAccountSelector)|Returns a selector with the specified ordering applied.
[withAccountNumbers(String[] accountNumbers)](#withaccountnumbers~string-accountnumbers~)|[BingAdsAccountSelector](./BingAdsAccountSelector)|Returns a selector that will return only bing ads accounts with the specified account numbers.
[withCondition(String condition)](#withcondition~string-condition~)|[BingAdsAccountSelector](./BingAdsAccountSelector)|Returns a selector that limits the accounts it returns to those that match the filter criteria.
[withIds(long[] ids)](#withids~long-ids~)|[BingAdsAccountSelector](./BingAdsAccountSelector)|Returns a selector that returns only accounts with the specified IDs.
[withLimit(int limit)](#withlimit~int-limit~)|[BingAdsAccountSelector](./BingAdsAccountSelector)|Returns a selector that limits the number of accounts it returns to the top *n* accounts that match the selection criteria.

## <a name="executeinparallel~string-functionname_-string-optionalcallbackfunctionname~"></a>executeInParallel(String functionName, String optionalCallbackFunctionName)
Executes the function indicated by functionName on each BingAdsAccount matched by this selector and optionally invokes the callback function indicated by optionalCallbackFunctionName.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="executeinparallel~string-functionname_-string-optionalcallbackfunctionname_-string-optionalinput~"></a>executeInParallel(String functionName, String optionalCallbackFunctionName, String optionalInput)
Executes the function indicated by functionName on each BingAdsAccount matched by this selector and optionally invokes the callback function indicated by optionalCallbackFunctionName. The optional optionalInput argument will be used in the parallel function execution, if specified.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="get"></a>get
Returns an account iterator based on the selector's selection criteria.

### Returns:
|Type|Description|
|-|-
[BingAdsAccountIterator](./BingAdsAccountIterator)|Iterator that you use to get accounts based on the selector's selection criteria.

## <a name="orderby~string-orderby~"></a>orderBy(String orderBy)
Returns a selector with the specified ordering applied. Specify the orderBy parameter in the form, "columnName orderDirection" where:

- columnName is a supported column, see [Supported Columns](#supported-bingads-account-columns).
- orderDirection is the direction to order the results in. Set to ASC to order the results in ascending order or DESC to order the results in descending order. The default is ASC.


For example, the following call returns results in ascending order by AverageCpc.

<code>bingAdsAccountSelector = bingAdsAccountSelector.orderBy("AverageCpc");</code>


Only one orderBy column is supported.

### Arguments:
|Name|Type|Description|
|-|-|-
orderBy|String|Ordering to apply.
### Returns:
|Type|Description|
|-|-
[BingAdsAccountSelector](./BingAdsAccountSelector)|Selector with ordering applied.

## <a name="withaccountnumbers~string-accountnumbers~"></a>withAccountNumbers(String[] accountNumbers)
Returns a selector that will return only bing ads accounts with the specified account numbers. 
The resulting selector can be further filtered by applying additional conditions to it.  All conditions will be 'AND' concatenated including any other ID based conditions.  For example:

```javascript
BingAdsApp.campaigns()
    .withAccountNumbers([11111, 22222, 33333])
    .withAccountNumbers([33333, 44444, 55555])
```

will only get the campaign with account number 33333 because it would be the only one satisfying both conditions.

The maximum number of account numbers that you may specify is 1,000. If you specify more than 1,000 account numbers, calling the get method will fail.

### Arguments:
|Name|Type|Description|
|-|-|-
accountNumbers|String[]|Array of account numbers.<br />
### Returns:
|Type|Description|
|-|-
[BingAdsAccountSelector](./BingAdsAccountSelector)|Selector restricted to the specified account numbers.

## <a name="withcondition~string-condition~"></a>withCondition(String condition)
Returns a selector that limits the accounts it returns to those that match the filter criteria. Specify the condition parameter in the form, "columnName operator value" where: 

- columnName is a supported column, see [Supported Columns](#supported-bingads-account-columns).  If you set columName to a performance metric column name, you must also specify a date range using [forDateRange(String dateRange)](#fordaterange~string-daterange~) or [forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~).
- operator is one of the supported [operators](#operators).

[!INCLUDE[operators](../includes/operators.md)]

<a name="supported-bingads-account-columns"></a>
### Supported Columns
Supported columns for Bing Ads account filtering. 

|Column|Type|Example|
|-|-|-
<strong>Stats</strong>|
AverageCpc|double|`withCondition("AverageCpc < 1.45")`
AverageCpm|double|`withCondition("AverageCpm > 0.48")`
AveragePosition|double|`withCondition("AveragePosition > 7.5")`
Clicks|long|`withCondition("Clicks >= 21")`
ConversionRate|double|`withCondition("ConversionRate > 0.1")`
Conversions|long|`withCondition("Conversions <= 4")`
Cost|double|`withCondition("Cost > 4.48")`<br /> The value is in the currency of the account.
Ctr|double|`withCondition("Ctr > 0.01")`<br /> Note that the Ctr is in the range 0..1, so a 5% Ctr is represented as 0.05.
CurrencyCode|String|`withCondition("CurrencyCode = 'USD'")`<br /> The three-letter ISO 4217-formatted currency code of the account.
DateTimeZone|String|`withCondition("DateTimeZone = 'America/New_York'")`<br /> The local timezone ID for the account.
Impressions|long|`withCondition("Impressions != 0")`
LabelNames|Array|`withCondition("LabelNames CONTAINS 'priority'")`
ManagedCustomerId|Account ID|`withCondition("ManagerCustomerId IN ['123-456-7890']")` or `withCondition("ManagerCustomerId IN [1234567890]")`<br /> Used to select child accounts belonging to a specific submanager.
Name|String|`withCondition("Name = 'Contoso'")`<br /> The name used by the manager to refer to the client.

### Returns:
|Type|Description|
|-|-
[BingAdsAccountSelector](./BingAdsAccountSelector)|Selector with the condition applied.

## <a name="withids~long-ids~"></a>withIds(long[] ids)
Returns a selector that returns only accounts with the specified IDs. 
The resulting selector can be further filtered by applying additional conditions to it.  All conditions will be 'AND' concatenated including any other ID based conditions.  For example:

```javascript
BingAdsApp.campaigns()
    .withIds([11111, 22222, 33333])
    .withIds([33333, 44444, 55555])
```

will only get the campaign with ID 33333 because it would be the only one satisfying both conditions.

The maximum number of IDs that you may specify is 1,000. If you specify more than 1,000 IDs, calling the get method will fail.

### Arguments:
|Name|Type|Description|
|-|-|-
ids|long[]|Array of customer IDs.<br />
### Returns:
|Type|Description|
|-|-
[BingAdsAccountSelector](./BingAdsAccountSelector)|Selector restricted to the specified IDs.

## <a name="withlimit~int-limit~"></a>withLimit(int limit)
Returns a selector that limits the number of accounts it returns to the top *n* accounts that match the selection criteria.

### Arguments:
|Name|Type|Description|
|-|-|-
limit|int|Number of results to return.
### Returns:
|Type|Description|
|-|-
[BingAdsAccountSelector](./BingAdsAccountSelector)|Selector with the limit applied.

