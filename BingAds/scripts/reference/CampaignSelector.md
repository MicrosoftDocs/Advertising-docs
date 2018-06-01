---
title: "CampaignSelector object"
description: "Contains the methods for filtering the list of campaigns to return."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# CampaignSelector

Contains the methods for filtering the list of ad groups. For information about selectors, see [Selectors](../concepts/selectors.md).

Example usage:
```javascript
 var campaignSelector = BingAdsApp.campaigns()
     .withCondition("Impressions > 100")
     .forDateRange("LAST_MONTH")
     .orderBy("Clicks DESC");

 var campaignIterator = campaignSelector.get();
 while (campaignIterator.hasNext()) {
   var campaign = campaignIterator.next();
 }
```


## Methods
|Method Name|Return Type|Description|
|-|-|-
[forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~)|[CampaignSelector](CampaignSelector.md)|Returns a selector with the start and end dates applied.
[forDateRange(string dateRange)](#fordaterange~string-daterange~)|[CampaignSelector](./CampaignSelector.md)|Returns a selector with the predefined date range applied.
[get](#get)|[CampaignIterator](./CampaignIterator.md)|Returns a campaign iterator based on the selector's selection criteria.
[orderBy(string orderBy)](#orderby~string-orderby~)|[CampaignSelector](./CampaignSelector.md)|Returns a selector with the specified ordering applied.
[withCondition(string condition)](#withcondition~string-condition~)|[CampaignSelector](./CampaignSelector.md)|Returns a selector that limits the campaigns it returns to those that match the filter criteria.
[withIds(string[] ids)](#withids~string-ids~)|[CampaignSelector](./CampaignSelector.md)|Returns a selector that returns only campaigns with the specified IDs.
[withLimit(int limit)](#withlimit~int-limit~)|[CampaignSelector](./CampaignSelector.md)|Returns a selector with the top *n* campaigns that match the selection criteria.

## <a name="fordaterange~object-datefrom_-object-dateto~"></a>forDateRange(Object dateFrom, Object dateTo)
Returns a selector with the start and end dates applied. The date range specifies the performance data to include with the selector.

[!INCLUDE[date-range-objects](../includes/date-range-objects.md)]

### Arguments
|Name|Type|Description|
|-|-|-
dateFrom|Object|The start date of the date range that specifies the performance data to include in the selector.
dateTo|Object|The end date of the date range that specifies the performance data to include in the selector.

### Returns
|Type|Description|
|-|-
[CampaignSelector](CampaignSelector.md)|Selector with date range applied.

## <a name="fordaterange~string-daterange~"></a>forDateRange(string dateRange)
Returns a selector with the predefined date range applied. The date range specifies the performance data to include with the selector.

[!INCLUDE[date-range-constants](../includes/date-range-constants.md)] 

[!INCLUDE[date-range-conditions-message](../includes/date-range-conditions-message.md)]

### Arguments
|Name|Type|Description|
|-|-|-
dateRange|String|Date range that specifies the performance data to include in the selector.

### Returns
|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector.md)|Selector with date range applied.

## <a name="get"></a>get
Returns a campaign [iterator](../concepts/iterators.md) based on the selector's selection criteria.

### Returns
|Type|Description|
|-|-
[CampaignIterator](./CampaignIterator.md)|Iterator that you use to iterate through the campaigns that were selected based on the selector's selection criteria.

## <a name="orderby~string-orderby~"></a>orderBy(string orderBy)
Returns a selector with the specified ordering applied. 

Specify the `orderBy` parameter in the form, "columnName orderDirection" where:

- *columnName* is a supported column, see [Supported Columns](#supported-campaign-columns)
- *orderDirection* is the direction to order the results in. Set to ASC to order the results in ascending order or DESC to order the results in descending order. The default is ASC.

For example, the following call returns campaigns in ascending order by AverageCpc.

`campaignSelector = campaignSelector.orderBy("AverageCpc");`

The selector may specify only one order-by column.

### Arguments
|Name|Type|Description|
|-|-|-
orderBy|string|The ordering to apply.

### Returns
|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector.md)|Selector with ordering applied.

## <a name="withcondition~string-condition~"></a>withCondition(string condition)
Returns a selector that limits the campaigns it returns to those that match the filter criteria. 

Specify the condition parameter in the form, "columnName operator value" where: 

- *columnName* is one of the [supported columns](#supported-ad-group-columns). If you set *columName* to a performance metric column name, you must also specify a date range using [forDateRange(String dateRange)](#fordaterange~string-daterange~) or [forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~).
- *operator* is one of the supported [operators](#operators).

[!INCLUDE[operators](../includes/operators.md)]

<a name="supported-campaign-columns"></a>
Supported columns for campaign filtering. 

|Column|Type|Example|
|-|-|-
<strong>Stats</strong>|
AverageCpc|double|`withCondition("AverageCpc < 1.45")`
AverageCpm|double|`withCondition("AverageCpm > 0.48")`
AveragePageviews|double|`withCondition("AveragePageviews > 0")`
AveragePosition|double|`withCondition("AveragePosition > 7.5")`
BounceRate|double|`withCondition("BounceRate < 0.5")`
ClickConversionRate|double|`withCondition("ClickConversionRate > 0.1")`
Clicks|long|`withCondition("Clicks >= 21")`
ConvertedClicks|long|`withCondition("ConvertedClicks <= 4")`
Cost|double|`withCondition("Cost > 4.48")`<br /> The cost is in the currency of the account.
Ctr|double|`withCondition("Ctr > 0.01")`<br /> The CTR is returned in the range 0..1, so a 5% CTR is represented as 0.05.
Impressions|long|`withCondition("Impressions != 0")`
&nbsp;|&nbsp;|&nbsp;
<strong>Campaign attributes</strong>|
Status|string|`withCondition("Status = PAUSED")`<br /><br />Possible status values are: <ul><li>ENABLED</li><li>PAUSED</li><li>REMOVED</li><li>BUDGET_PAUSED</li><li>BUDGET_AND_USER_PAUSED</li></ul>
Name|string|`withCondition("Name CONTAINS_IGNORE_CASE 'promotion'")`
Budget|double|`withCondition("Budget > 10.0")`
Type|string|`withCondition("Type = 'SEARCH_AND_CONTENT'")`<br /><br />Possible status values are: <ul><li>SEARCH_AND_CONTENT</li><li>SHOPPING</li><li>DYNAMIC_SEARCH_ADS</li></ul>
BudgetType|string|`withCondition("BudgetType = 'ACCELERATED'")`<br /><br />Possible status values are: <ul><li>STANDARD</li><li>ACCELERATED</li></ul>
DeliveryStatus|string|`withCondition("DeliveryStatus NOT IN ['LIMITED_BY_BUDGET', 'HOLD', 'CAMPAIGN_OUT_OF_BUDGET']")`<br /><br />Possible status values are: <ul><li>ELIGIBLE</li><li>LIMITED_BY_BUDGET</li><li>HOLD</li><li>CAMPAIGN_OUT_OF_BUDGET</li><li>CAMPAIGN_SUSPENDED</li><li>CAMPAIGN_PAUSED</li></ul>



### Arguments
|Name|Type|Description|
|-|-|-
condition|string|The condition to apply to the selector.

### Returns
|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector.md)|Selector with the condition applied.

## <a name="withids~string-ids~"></a>withIds(string[] ids)
Returns a selector that contains only campaigns with the specified IDs. 

[!INCLUDE[with-ids-chaining](../includes/with-ids-chaining.md)] For example, the following call selects only campaign 33333.

```javascript
BingAdsApp.campaigns()
    .withIds([11111, 22222, 33333])
    .withIds([33333, 44444, 55555])
```

[!INCLUDE[maximum-number-of-ids](../includes/maximum-number-of-ids.md)] 


### Arguments
|Name|Type|Description|
|-|-|-
ids|string[]|An array of campaign IDs. The maximum number of IDs that you may specify is 1,000. If you specify more than 1,000 IDs, calling the `get` method fails with a runtime error.

### Returns
|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector.md)|Selector restricted to the given IDs.

## <a name="withlimit~int-limit~"></a>withLimit(int limit)
Returns a selector with the top *n* campaigns that match the selection criteria.

### Arguments
|Name|Type|Description|
|-|-|-
limit|int|The number of campaigns to return. The actual number may be less.

### Returns
|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector.md)|Selector with limit applied.



## See also

- [CampaignIterator](./CampaignIterator.md)
- [Campaign](./Campaign.md)
