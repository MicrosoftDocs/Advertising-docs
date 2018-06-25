---
title: "AdGroupSelector object"
description: "Contains the methods for filtering the list of ad groups to return."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# AdGroupSelector

Contains the methods for filtering the list of ad groups. For information about selectors, see [Selectors](../concepts/selectors.md).

Example usage:
```javascript
var adGroupSelector = BingAdsApp.adGroups()
     .withCondition("Impressions > 100")
     .forDateRange("LAST_MONTH")
     .orderBy("Clicks DESC");

 var adGroupIterator = adGroupSelector.get();
 while (adGroupIterator.hasNext()) {
   var adGroup = adGroupIterator.next();
 }
```

## Methods

|Method Name|Return Type|Description|
|-|-|-
[forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~)|[AdGroupSelector](./AdGroupSelector.md)|Returns a selector with the start and end dates applied.
[forDateRange(string dateRange)](#fordaterange~string-daterange~)|[AdGroupSelector](./AdGroupSelector.md)|Returns a selector with the predefined date range applied.
[get](#get)|[AdGroupIterator](./AdGroupIterator.md)|Returns an iterator that you use to iterate through the list of ad groups.
[orderBy(string orderBy)](#orderby~string-orderby~)|[AdGroupSelector](./AdGroupSelector.md)|Returns a selector with the specified ordering applied.
[withCondition(string condition)](#withcondition~string-condition~)|[AdGroupSelector](./AdGroupSelector.md)|Returns a selector that limits the ad groups to those that match the filter criteria.
[withIds(string[] ids)](#withids~string-ids~)|[AdGroupSelector](./AdGroupSelector.md)|Returns a selector that returns only ad groups with the specified IDs.
[withLimit(int limit)](#withlimit~int-limit~)|[AdGroupSelector](./AdGroupSelector.md)|Returns a selector with the top *n* ad groups that match the selection criteria.

## <a name="fordaterange~object-datefrom_-object-dateto~"></a>forDateRange(Object dateFrom, Object dateTo)
Returns a selector with the start and end dates applied. The date range specifies the performance data to include with the selector.

[!INCLUDE[date-range-objects](../includes/date-range-objects.md)]

### Arguments
|Name|Type|Description|
|-|-|-
dateFrom|Object|Start date of the date range that specifies the performance data to include in the selector.
dateTo|Object|End date of the date range that specifies the performance data to include in the selector.

### Returns
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector.md)|Selector with date range applied.

## <a name="fordaterange~string-daterange~"></a>forDateRange(String dateRange)
Returns a selector with the predefined date range applied. The date range specifies the performance data to include with the selector.

[!INCLUDE[date-range-conditions-message](../includes/date-range-conditions-message.md)]

[!INCLUDE[date-range-constants](../includes/date-range-constants.md)] 

### Arguments
|Name|Type|Description|
|-|-|-
dateRange|String|The predefined date range string that specifies the performance data to include in the selector. The predefined date range string is case sensitive.

### Returns
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector.md)|Selector with date range applied.

## <a name="get"></a>get
Returns an [iterator](../concepts/iterators.md) based on the selector's selection criteria.

### Returns
|Type|Description|
|-|-
[AdGroupIterator](./AdGroupIterator.md)|An iterator that you use to iterate through the selected ad groups.

## <a name="orderby~string-orderby~"></a>orderBy(String orderBy)
Returns a selector with the specified ordering applied. 

Specify the `orderBy` parameter in the form, "columnName orderDirection" where:

- *columnName* is one of the [supported columns](#supported-ad-group-columns). 
- *orderDirection* is the order to sort the results in. Set to ASC to order the results in ascending order or DESC to order the results in descending order. The default is ASC.

For example, the following call returns ad groups in ascending order by AverageCpc.

`adGroupSelector = adGroupSelector.orderBy("AverageCpc");`


[!INCLUDE[order-by-limit](../includes/order-by-limit.md)]


### Arguments
|Name|Type|Description|
|-|-|-
orderBy|string|The ordering to apply.

### Returns
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector.md)|Selector with ordering applied.

## <a name="withcondition~string-condition~"></a>withCondition(String condition)
Returns a selector that limits the ad groups it returns to those that match the filter criteria. 

Specify the condition parameter in the form, "columnName operator value" where: 

- *columnName* is one of the [supported Columns](#supported-ad-group-columns). If you set *columName* to a performance metric column name, you must also specify a date range using [forDateRange(String dateRange)](#fordaterange~string-daterange~) or [forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~).
- *operator* is one of the supported [operators](#operators).

[!INCLUDE[operators](../includes/operators.md)]

<a name="supported-ad-group-columns"></a>
### Supported Columns

Supported columns for ad group filtering. The names are case sensitive.

|Column|Type|Example|
|-|-|-
<strong>Stats</strong>|
AverageCpc|double|`withCondition("AverageCpc < 1.45")`
AverageCpm|double|`withCondition("AverageCpm > 0.48")`
AveragePosition|double|`withCondition("AveragePosition > 7.5")`
ClickConversionRate|double|`withCondition("ClickConversionRate > 0.1")`
Clicks|long|`withCondition("Clicks >= 21")`
ConvertedClicks|long|`withCondition("ConvertedClicks <= 4")`
Cost|double|`withCondition("Cost > 4.48")`<br /><br />The cost is in the currency of the account.
Ctr|double|`withCondition("Ctr > 0.01")`<br /><br />The CTR is in the range 0..1, so a 5% CTR is represented as 0.05.
Impressions|long|`withCondition("Impressions != 0")`
&nbsp;|&nbsp;|&nbsp;
<strong>Ad group attributes</strong>|
Status|enumeration|`withCondition("Status = PAUSED")`<br /><br />Possible case-sensitive values are: <ul><li>ENABLED</li><li>PAUSED</li><li>REMOVED</li></ul>
Name|string|`withCondition("Name CONTAINS_IGNORE_CASE 'shoes'")`
CampaignName|string|`withCondition("CampaignName CONTAINS_IGNORE_CASE 'promotion'")`
KeywordMaxCpc|double|`withCondition("KeywordMaxCpc > 10.0")`<br /><br />The value is in the currency of the account.
CampaignStatus|enumeration|`withCondition("CampaignStatus = ENABLED")`<br /><br />This example returns ad groups from only ENABLED campaigns. Possible case-sensitive values are: <ul><li>ENABLED</li><li>PAUSED</li><li>REMOVED</li></ul>

### Arguments
|Name|Type|Description|
|-|-|-
condition|string|The condition to add to the selector.

### Returns
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector.md)|Selector with the condition applied.

## <a name="withids~string-ids~"></a>withIds(string[] ids)
Returns a selector that contains only ad groups with the specified IDs. 

[!INCLUDE[with-ids-chaining](../includes/with-ids-chaining.md)] For example, the following call selects only ad group 33333.

```javascript
BingAdsApp.adGroups()
    .withIds([11111, 22222, 33333])
    .withIds([33333, 44444, 55555])
```


### Arguments
|Name|Type|Description|
|-|-|-
ids|string[]|An array of ad group IDs. The maximum number of IDs that you may specify is 1,000. If you specify more than 1,000 IDs, calling the `get()` method fails with a runtime error.

### Returns
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector.md)|Selector restricted to the given IDs.

## <a name="withlimit~int-limit~"></a>withLimit(int limit)
Returns a selector with the top *n* ad groups that match the selection criteria.

### Arguments
|Name|Type|Description|
|-|-|-
limit|int|The number of ad groups to return. The actual number may be less.

### Returns
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector.md)|Selector with limit applied.



## See also

[BingAdsApp.adGroups()](BingAdsApp.md#adgroups)
