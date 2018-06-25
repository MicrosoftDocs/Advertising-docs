---
title: "KeywordSelector object"
description: "Contains the methods for filtering the list of keywords to return."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# KeywordSelector

Contains the methods for filtering the list of keywords. For information about selectors, see [Selectors](../concepts/selectors.md).

## Methods
|Method Name|Return Type|Description|
|-|-|-
[forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~)|[KeywordSelector](./KeywordSelector.md)|Returns a selector with the start and end dates applied.
[forDateRange(string dateRange)](#fordaterange~string-daterange~)|[KeywordSelector](./KeywordSelector.md)|Returns a selector with the predefined date range applied.
[get](#get)|[KeywordIterator](./KeywordIterator.md)|Returns an iterator that you use to iterate through the list of keywords.
[orderBy(string orderBy)](#orderby~string-orderby~)|[KeywordSelector](./KeywordSelector.md)|Returns a selector with the specified ordering applied.
[withCondition(string condition)](#withcondition~string-condition~)|[KeywordSelector](./KeywordSelector.md)|Returns a selector that limits the keywords to those that match the filter criteria.
[withIds(string[] ids)](#withids~string-ids~)|[KeywordSelector](./KeywordSelector.md)|Returns a selector that returns only keywords with the specified IDs.
[withLimit(int limit)](#withlimit~int-limit~)|[KeywordSelector](./KeywordSelector.md)|Returns a selector with the top *n* keywords that match the selection criteria.

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
[KeywordSelector](./KeywordSelector.md)|Selector with date range applied.

## <a name="fordaterange~string-daterange~"></a>forDateRange(String dateRange)
Returns a selector with the predefined date range applied. The date range specifies the performance data to include with the selector.

[!INCLUDE[date-range-constants](../includes/date-range-constants.md)] 

[!INCLUDE[date-range-conditions-message](../includes/date-range-conditions-message.md)]

### Arguments
|Name|Type|Description|
|-|-|-
dateRange|String|The predefined date range string that specifies the performance data to include in the selector. The predefined date range string is case sensitive.

### Returns
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector.md)|Selector with date range applied.

## <a name="get"></a>get
Returns an [iterator](../concepts/iterators.md) that you use to iterate through the list of keywords.

### Returns
|Type|Description|
|-|-
[KeywordIterator](./KeywordIterator.md)|An iterator that you use to iterate through the keywords that were selected based on the selector's selection criteria.

## <a name="orderby~string-orderby~"></a>orderBy(string orderBy)
Returns a selector with the specified ordering applied. 

Specify the `orderBy` parameter in the form, "columnName orderDirection" where:

- *columnName* is one of the [supported columns](#supported-keyword-columns).
- *orderDirection* is the order to sort the results in. Set to ASC to order the results in ascending order or DESC to order the results in descending order. The default is ASC.

For example, the following call returns results in ascending order by AverageCpc.

`keywordSelector = keywordSelector.orderBy("AverageCpc");`

[!INCLUDE[order-by-limit](../includes/order-by-limit.md)]

### Arguments
|Name|Type|Description|
|-|-|-
orderBy|string|The ordering to apply.

### Returns
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector.md)|Selector with ordering applied.

## <a name="withcondition~string-condition~"></a>withCondition(String condition)
Returns a selector that limits the keywords it returns to those that match the filter criteria. 

Specify the condition parameter in the form, "columnName operator value" where: 

- *columnName* is one of the [supported columns](#supported-keyword-columns). If you set *columName* to a performance metric column name, you must also specify a date range using [forDateRange(String dateRange)](#fordaterange~string-daterange~) or [forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~).
- *operator* is one of the supported [operators](#operators).

[!INCLUDE[operators](../includes/operators.md)]

<a name="supported-keyword-columns"></a>
Supported columns for keyword filtering. The column names are case sensitive.

|Column|Type|Example|Bing Web UI filter|
|-|-|-|-
<strong>Stats</strong>|
AverageCpc|double|`withCondition("AverageCpc < 1.45")`|Avg. CPC
AverageCpm|double|`withCondition("AverageCpm > 0.48")`|Avg. CPM
AveragePosition|double|`withCondition("AveragePosition > 7.5")`|Avg. pos.
ClickConversionRate|double|`withCondition("ClickConversionRate > 0.1")`|Conv. Rate
Clicks|long|`withCondition("Clicks >= 21")`|Clicks
ConvertedClicks|long|`withCondition("ConvertedClicks <= 4")`|Conv.
Cost|double|`withCondition("Cost > 4.48").`<br /><br />The cost is in the currency of the account.|Spend
Ctr|double|`withCondition("Ctr > 0.01").`<br /><br />The CTR is in the range 0..1, so a 5% CTR is represented as 0.05.`|CTR
Impressions|long|`withCondition("Impressions != 0")`|Impr.
&nbsp;|&nbsp;|&nbsp;|&nbsp;
<strong>Keyword</strong>|
Status|enumeration|`withCondition("Status = PAUSED")`<br /><br />Possible case-sensitive values are: <ul><li>ENABLED</li><li>PAUSED</li><li>DISABLED</li></ul>|Status
Text|string|`withCondition("Text STARTS_WITH 'books'")`<br /><br />Include only the keyword's text. Don't include the keyword's match type in the text. For example, if you added an exact match keyword such as [books], use *books* not *[books]*.|Keyword Text
KeywordMatchType|enumeration|`withCondition("KeywordMatchType = EXACT")`<br /><br />Possible case-sensitive values are: <ul><li>BROAD</li><li>EXACT</li><li>PHRASE</li></ul>|Match type
MaxCpc|double|`withCondition("MaxCpc > 0.40")`<br /><br /><br />The CPC is in the currency of the current account.|Bid
DestinationUrl|string|`withCondition("DestinationUrl STARTS_WITH 'http://www.example.com'")`|Destination URL
FinalUrls|string|`withCondition("FinalUrls CONTAINS 'http://www.example.com'")`|
QualityScore|int|`withCondition("QualityScore > 5")`|Qual. score
FirstPageCpc|double|`withCondition("FirstPageCpc > 6.00")`<br /><br />This is the average amount an advertiser is charged each time their ad is clicked when it shows up on the sidebar. For example, if an advertiser paid a total of $48.35 for 300 clicks, the advertiser's average CPC is $0.16. You use this information to help decide whether to increase your keyword bid to improve the chance that your ad shows up on the sidebar.<br /><br />The CPC is in the currency of the current account.|Est. first page bid
TopOfPageCpc|double|`withCondition("TopOfPageCpc > 8.00")`<br /><br />This is the average amount an advertiser is charged each time their ad is clicked when it shows up above the organic search results. For example, if an advertiser paid a total of $48.35 for 300 clicks, the advertiser's average CPC is $0.16. You use this information to help decide whether to increase your keyword bid to improve the chance that your ad shows up above the organic search results.<br /><br />The CPC is in the currency of the current account.|Est. mainline bid
AdGroupName|string|`withCondition("AdGroupName = 'foo'")`|
CampaignName|string|`withCondition("CampaignName = 'bar'")`|


### Arguments
|Name|Type|Description|
|-|-|-
condition|string|The condition to add to the selector.

### Returns
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector.md)|Selector with the condition applied.

## <a name="withids~string-ids~"></a>withIds(string[] ids)
Returns a selector that contains only keywords with the specified IDs. 

[!INCLUDE[with-ids-chaining](../includes/with-ids-chaining.md)] For example, the following call selects only keyword 33333.

```javascript
BingAdsApp.keywords()
    .withIds([11111, 22222, 33333])
    .withIds([33333, 44444, 55555])
```

[!INCLUDE[maximum-number-of-ids](../includes/maximum-number-of-ids.md)] 

### Arguments
|Name|Type|Description|
|-|-|-
ids|string[]|An array of keyword IDs. The maximum number of IDs that you may specify is 1,000. If you specify more than 1,000 IDs, calling the `get()` method fails with a runtime error.

### Returns
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector.md)|Selector restricted to the given IDs.

## <a name="withlimit~int-limit~"></a>withLimit(int limit)
Returns a selector with the top *n* keywords that match the selection criteria.

### Arguments
|Name|Type|Description|
|-|-|-
limit|int|The number of keywords to return. The actual number may be less.

### Returns
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector.md)|Selector with limit applied.



## See also

- [BingAdsApp.keywords()](BingAdsApp.md)
- [KeywordIterator](./KeywordIterator.md)
- [Keyword](./Keyword.md)

