---
title: "LabelSelector object"
description: "Contains the methods for filtering and ordering the list of labels to return."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# LabelSelector

Contains the methods for filtering and ordering a list of labels in the account. For information about selectors, see [Selectors](../concepts/selectors.md).


## Methods
|Method Name|Return Type|Description|
|-|-|-
[get](#get)|[LabelIterator](./KeywordIterator.md)|Gets an iterator used to iterate through the list of labels.
[orderBy(string orderBy)](#orderby-string-orderby-)|[LabelSelector](./LabelSelector.md)|Applies the specified ordering to the selected labels.
[withCondition(string condition)](#withcondition-string-condition-)|[LabelSelector](./LabelSelector.md)|Applies filter criteria to the labels.
[withIds(string[] ids)](#withids-string-ids-)|[LabelSelector](./LabelSelector.md)|Gets labels with the specified IDs.
[withLimit(int limit)](#withlimit-int-limit-)|[LabelSelector](./LabelSelector.md)|Gets the top *n* labels that match the selection criteria.


## <a name="get"></a>get
Gets an [iterator](../concepts/iterators.md) used to iterate through the list of labels.

### Returns
|Type|Description|
|-|-
[LabelIterator](./LabelIterator.md)|An iterator used to iterate through the selected labels.


## <a name="orderby-string-orderby-"></a>orderBy(string orderBy)
Applies the specified ordering to the selected labels.

Specify the *orderBy* parameter in the form, "columnName orderDirection" where:

- *columnName* is one of the [supported columns](#supported-label-columns).
- *orderDirection* is the order to sort the results in. Set to ASC to order the results in ascending order or DESC to order the results in descending order. The default is ASC.

For example, the following call returns results in ascending order by the label's name.

`selector = selector.orderBy("Name");`

[!INCLUDE[order-by-limit](../includes/order-by-limit.md)]

### Arguments
|Name|Type|Description|
|-|-|-
orderBy|string|The ordering to apply.

### Returns
|Type|Description|
|-|-
[LabelSelector](./LabelSelector.md)|Selector with ordering applied.


## <a name="withcondition-string-condition-"></a>withCondition(String condition)
Applies filter criteria to the labels. 

Specify the *condition* parameter in the form, "columnName operator value" where: 

- *columnName* is one of the [supported columns](#supported-label-columns). 
- *operator* is one of the supported [operators](#operators).

[!INCLUDE[operators](../includes/operators.md)]

<a name="supported-label-columns"></a>
Supported columns for label filtering. The column names are case sensitive.

|Column|Type|Example|Microsoft Advertising web UI filter
|-|-|-|-
Status|enumeration|The keyword's status. Possible case-sensitive values are: <ul><li>ENABLED</li><li>PAUSED</li><li>REMOVED</li></ul>`withCondition("Status = ENABLED")`|Status
Text|string|The keyword's text. Include only the keyword's text. Don't include the keyword's match type in the text. For example, if the keyword is an exact match keyword such as [books], use *books* not *[books]*.<br /><br />`withCondition("Text STARTS_WITH 'flowers'")`|Keyword Text
KeywordMatchType|enumeration|The keyword's match type. Possible case-sensitive values are: <ul><li>BROAD</li><li>EXACT</li><li>PHRASE</li></ul>`withCondition("KeywordMatchType = EXACT")`|Match type
MaxCpc|double|The keyword's maximum CPC bid amount. The CPC is in the account's currency.<br /><br />`withCondition("MaxCpc > 0.40")`|Bid
DestinationUrl|string|`withCondition("DestinationUrl STARTS_WITH 'http://www.contoso.com'")`|Destination URL
FinalUrls|string|`withCondition("FinalUrls CONTAINS 'http://www.contoso.com'")`|
QualityScore|int|`withCondition("QualityScore > 5")`|Qual. score
FirstPageCpc|double|The average amount an advertiser is charged each time their ad is clicked when it shows up on the sidebar. For example, if an advertiser paid a total of $48.35 for 300 clicks, the advertiser's average CPC is $0.16. Use this information to help decide whether to increase your keyword bid to improve the chance that your ad shows up on the sidebar. The CPC is in the account's currency.<br /><br />`withCondition("FirstPageCpc > 6.00")`|Est. first page bid
TopOfPageCpc|double|The average amount an advertiser is charged each time their ad is clicked when it shows up above the organic search results. For example, if an advertiser paid a total of $48.35 for 300 clicks, the advertiser's average CPC is $0.16. Use this information to help decide whether to increase your keyword bid to improve the chance that your ad shows up above the organic search results. The CPC is in the currency of the current account.<br /><br />`withCondition("TopOfPageCpc > 8.00")`|Best position
AdGroupName|string|The name of the ad group that contains the keywords.<br /><br />`withCondition("AdGroupName = 'foo'")`|
CampaignName|string|The name of the campaign that contains the keywords.<br /><br />`withCondition("CampaignName = 'bar'")`|

### Arguments
|Name|Type|Description|
|-|-|-
condition|string|The condition to add to the selector.

### Returns
|Type|Description|
|-|-
[LabelSelector](./LabelSelector.md)|Selector with the condition applied.

## <a name="withids-string-ids-"></a>withIds(string[] ids)
Gets labels with the specified IDs.

[!INCLUDE[with-ids-chaining](../includes/with-ids-chaining.md)] For example, the following call selects only label 33333.

```javascript
AdsApp.labels()
    .withIds(['11111', '22222', '33333'])
    .withIds(['33333', '44444', '55555']);
```

### Arguments
|Name|Type|Description|
|-|-|-
ids|string[]|An array of label IDs. For limits, see [Script execution limits](../concepts/execution-limits.md).

### Returns
|Type|Description|
|-|-
[LabelSelector](./LabelSelector.md)|Selector with the IDs applied.

## <a name="withlimit-int-limit-"></a>withLimit(int limit)
Gets the top *n* labels that match the selection criteria.

### Arguments
|Name|Type|Description|
|-|-|-
limit|int|The number of labels to return. The actual number may be less.

### Returns
|Type|Description|
|-|-
[LabelSelector](./LabelSelector.md)|Selector with limit applied.



## See also

- [AdsApp.label()](AdsApp.md)
- [LabelIterator](./LabelIterator.md)
- [Label](./Label.md)

