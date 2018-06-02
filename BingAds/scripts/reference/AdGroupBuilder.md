---
title: "AdGroupBuilder object"
description: "Contains the methods for defining an ad group."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# AdGroupBuilder

Contains the methods for defining and building an ad group. For information about builders, see [Builders](../concepts/builders.md).

Example usage:
```javascript
var campaignSelector = BingAdsApp.campaigns();
var campaignIterator = campaignSelector.get();

while(campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    var adGroupBuilder = campaign.newAdGroupBuilder();
    var adGroupOperation = adGroupBuilder
        .withName("<AD_GROUP_NAME_GOES_HERE>")
        .withStatus("PAUSED")
        .build();
    
    var adGroup = adGroupOperation.getResult();
}
```

## Methods
|Method Name|Return Type|Description|
|-|-|-
[build](#build)|[AdGroupOperation](./AdGroupOperation.md)|Returns an operation object that you use to add the ad group to the campaign.
[withBiddingStrategy(string biddingStrategy)](#withbiddingstrategy~string-biddingstrategy~)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the ad group's bidding strategy.
[withCpc(double cpc)](#withcpc~double-cpc~)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the ad group's maximum CPC bid.
[withCustomParameters(Object customParameters)](#withcustomparameters~object-customparameters~)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the ad group's custom parameters.
[withEndDate(string endDate)](#withenddate~string-endDate~)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the date when ads in the ad group stop serving.
[withEndDate(Object endDate)](#withenddate~object-enddate~)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the date when ads in the ad group stop serving.
[withLanguage(string language)](#withlanguage~string-language~)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the language used by this ad group.
[withName(string name)](#withname~string-name~)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the ad group's name.
[withStartDate(string startDate)](#withstartdate~string-startDate~)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the date when ads in the ad group start serving.
[withStartDate(Object startDate)](#withstartdate~object-startdate~)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the date when ads in the ad group start serving.
[withStatus(string status)](#withstatus~string-status~)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the ad group's status.
[withTrackingTemplate(string trackingTemplate)](#withtrackingtemplate~string-trackingtemplate~)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the tracking template used with this ad group.

## <a name="build"></a>build
Returns an operation object that you use to add the ad group to the campaign.

### Returns
|Type|Description|
|-|-
[AdGroupOperation](./AdGroupOperation.md)|An operation object that you use to add the ad group to the campaign.

## <a name="withbiddingstrategy~string-biddingstrategy~"></a>withBiddingStrategy(string biddingStrategy)
Sets the ad group's bidding strategy. 

### Arguments
|Name|Type|Description|
|-|-|-
biddingStrategy|string|The bidding strategy to apply to the ad group. Possible values are:<ul><li>ManualCpc</li><li>MaxClicks</li><li>MaxConversions</li><li>EnhancedCpc</li><li>TargetCpa</li></ul>For information about these strategies, see [Bid Strategy Types](/bingads/guides/budget-bid-strategies#bidstrategytypes).

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the bidding strategy applied.

## <a name="withcpc~double-cpc~"></a>withCpc(double cpc)
Sets the ad group's maximum CPC bid. 

### Arguments
|Name|Type|Description|
|-|-|-
cpc|double|The maximum CPC bid to apply to the ad group. The default bid is 0.30 cents (USD).

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the CPC bid applied.

## <a name="withcustomparameters~object-customparameters~"></a>withCustomParameters(Object customParameters)
Sets the ad group's custom parameters. 

[!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

### Arguments
|Name|Type|Description|
|-|-|-
customParameters|Object|The custom parameters to apply to the ad group. Specify the parameters as a dictionary of key-value pairs.<br /><br />For example, `{key1: 'value1', key2: 'value2', key3: 'value3'}`, where key is the custom parameter's name and value is the parameter's value.

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the custom parameters applied.


## <a name="withenddate~string-enddate~"></a>withEndDate(string endDate)
Sets the date when you want ads in the ad group to stop serving. Call this method only if you want ads in the group to stop serving on a specific date.

### Arguments
|Name|Type|Description|
|-|-|-
endDate|string|The date when you want ads in the ad group to stop serving. Specify the date in the form, YYYYMMDD.

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the end date applied.

## <a name="withenddate~object-enddate~"></a>withEndDate(Object endDate)
Sets the date when you want ads in the ad group to stop serving. Call this method only if you want ads in the group to stop serving on a specific date.

### Arguments
|Name|Type|Description|
|-|-|-
endDate|Object|The date when you want ads in the ad group to stop serving. Specify the date using an object with the following fields:<br /><ul><li>year</li><li>month</li><li>day</li></ul><br />For example: `var date = {year: 2018, month: 5, day: 13};`

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the end date applied.


## <a name="withlanguage~string-language~"></a>withLanguage(string language)
Sets the language used by this ad group. By default, the ad group inherits the language from its parent campaign. Specify a language at the ad group level if you want to override the language specified at the campaign level or if the campaign did not specify a language (language must be specified at the campaign and/or ad group level). 


### Arguments
|Name|Type|Description|
|-|-|-
language|string|Ad group's language.

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the language applied.

## <a name="withname~string-name~"></a>withName(string name)
Sets the ad group's name.

### Arguments
|Name|Type|Description|
|-|-|-
name|string|The Ad group's name. The name can contain a maximum of 256 characters and must be unique amongst all active ad groups within the campaign.

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the name applied.



## <a name="withstartdate~string-startdate~"></a>withStartDate(string startDate)
Sets the date when you want ads in the ad group to start serving. Call this method only if you want ads in the group to start serving on a specific date; otherwise, ads start serving immediately.

### Arguments
|Name|Type|Description|
|-|-|-
endDate|string|The date when you want ads in the ad group to start serving. Specify the date in the form, YYYYMMDD.

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the start date applied.

## <a name="withstartdate~object-startdate~"></a>withStartDate(Object startDate)
Sets the date when you want ads in the ad group to start serving. Call this method only if you want ads in the group to start serving on a specific date; otherwise, ads start serving immediately.

### Arguments
|Name|Type|Description|
|-|-|-
endDate|Object|The date when you want ads in the ad group to start serving. Specify the date using an object with the following fields:<br /><ul><li>year</li><li>month</li><li>day</li></ul><br />For example: `var date = {year: 2018, month: 5, day: 13};`

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the start date applied.





## <a name="withstatus~string-status~"></a>withStatus(string status)
Sets the ad group's status. 

### Arguments
|Name|Type|Description|
|-|-|-
status|String|The ad group's status. The following are the possible values: <br/><ul><li>ENABLED</li><li>PAUSED</li><li>REMOVED</li></ul>The default is ENABLED. 

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the status applied.

## <a name="withtrackingtemplate~string-trackingtemplate~"></a>withTrackingTemplate(string trackingTemplate)
Sets the tracking template used by this ad group. 

[!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Arguments
|Name|Type|Description|
|-|-|-
trackingTemplate|string|Tracking template to use with the ad group.

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the tracking template applied.



## See also

[Campaign.newAdGroupBuilder()](Campaign.md#newadgroupbuilder)