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

Contains the methods used to define and add an ad group. For information about builders, see [Builders](../concepts/builders.md).

Example usage:
```javascript
    // Get a campaign to add the ad group to.
    var iterator = BingAdsApp.campaigns()
        .withIds(['CAMPAIGN ID GOES HERE'])
        .get();

    if (iterator.hasNext()) {
        var campaign = iterator.next();

        // Get the campaign's ad group builder and add an ad group.
        var operation = campaign.newAdGroupBuilder();
            .withName("AD GROUP NAME GOES HERE")
            .withStatus("ENABLED")
            .build();
    
        // See the Builders topic for performance considerations
        // when using the operation object's methods.
        if (!operation.isSuccessful()) {
            for (var error of operation.getErrors()) {
                Logger.log(`${error}\n`);
            }
        }
    }
```

## Methods

|Method Name|Return Type|Description|
|-|-|-
[build](#build)|[AdGroupOperation](./AdGroupOperation.md)|Creates the ad group and returns an operation object that you can use to check whether the ad group was successfully added.
[withBiddingStrategy(string biddingStrategy)](#withbiddingstrategy-string-biddingstrategy-)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the ad group's bidding strategy.
[withCpc(double cpc)](#withcpc-double-cpc-)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the ad group's maximum CPC bid.
[withCustomParameters(Object customParameters)](#withcustomparameters-object-customparameters-)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the ad group's custom parameters.
[withEndDate(string endDate)](#withenddate-string-enddate-)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the date when ads in the ad group stop serving.
[withEndDate(Object endDate)](#withenddate-object-enddate-)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the date when ads in the ad group stop serving.
[withLanguage(string language)](#withlanguage-string-language-)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the language used by this ad group.
[withName(string name)](#withname-string-name-)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the ad group's name.
[withStartDate(string startDate)](#withstartdate-string-startdate-)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the date when ads in the ad group start serving.
[withStartDate(Object startDate)](#withstartdate-object-startdate-)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the date when ads in the ad group start serving.
[withStatus(string status)](#withstatus-string-status-)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the ad group's status.
[withTrackingTemplate(string trackingTemplate)](#withtrackingtemplate-string-trackingtemplate-)|[AdGroupBuilder](./AdGroupBuilder.md)|Sets the tracking template used by the ad group.

## <a name="build"></a>build
Creates the ad group and returns an operation object that you can use to check whether the ad group was successfully added.

### Returns
|Type|Description|
|-|-
[AdGroupOperation](./AdGroupOperation.md)|An operation object that you use to check whether the ad group was successfully added.

## <a name="withbiddingstrategy-string-biddingstrategy-"></a>withBiddingStrategy(string biddingStrategy)
Sets the ad group's bidding strategy. 

### Arguments
|Name|Type|Description|
|-|-|-
biddingStrategy|string|The bidding strategy to apply to the ad group. The following are the possible case-sensitive values.<ul><li>MANUAL_CPC</li></ul>For information about these strategies, see [Bid Strategy Types](/bingads/guides/budget-bid-strategies#bidstrategytypes).

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the bidding strategy applied.

## <a name="withcpc-double-cpc-"></a>withCpc(double cpc)
Sets the ad group's CPC bid. 

Specifies the bid amount to use when the keyword matches the user's search term and the ad group's bid strategy is MANUAL_CPC. This bid is used if a lower-level entity such as keyword does not override it.


### Arguments
|Name|Type|Description|
|-|-|-
cpc|double|The ad group's maximum CPC bid. The account's currency determines the minimum and maximum bid values. For more information, see [Bid and budget currencies](/bingads/guides/currencies#bidandbudget).

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the CPC bid applied.

## <a name="withcustomparameters-object-customparameters-"></a>withCustomParameters(Object customParameters)
Sets the ad group's custom parameters to use in final URLs or tracking templates. 

[!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

### Arguments
|Name|Type|Description|
|-|-|-
customParameters|Object|The custom parameters to apply to the ad group. Specify the parameters as a map of key-value pairs.<br /><br />For example, `{key1: 'value1', key2: 'value2', key3: 'value3'}`, where key is the custom parameter's name and value is the parameter's value.<br /><br />The key and value may not exceed 60 and 200 bytes, respectively.

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the custom parameters applied.


## <a name="withenddate-string-enddate-"></a>withEndDate(string endDate)
Sets the date when you want ads in the ad group to stop serving. Call this method only if you want ads in the group to stop serving on a specific date.

### Arguments
|Name|Type|Description|
|-|-|-
endDate|string|The date when you want ads in the ad group to stop serving. Specify the date in the form, YYYYMMDD.

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the end date applied.

## <a name="withenddate-object-enddate-"></a>withEndDate(Object endDate)
Sets the date when you want ads in the ad group to stop serving. Call this method only if you want ads in the group to stop serving on a specific date.

### Arguments
|Name|Type|Description|
|-|-|-
endDate|Object|The date when you want ads in the ad group to stop serving. Specify the date using an object with the following fields:<br /><ul><li>year</li><li>month</li><li>day</li></ul><br />For example: `var date = {year: 2018, month: 5, day: 13};`<br /><br />The month is one-based where 1 is January and 12 is December.

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the end date applied.


## <a name="withlanguage-string-language-"></a>withLanguage(string language)
Sets the language used by ads in this ad group. 

By default, the ad group inherits the language from its parent campaign. Specify a language at the ad group level if you want to override the language specified at the campaign level or if the campaign doesn't specify a language (language must be specified at the campaign and/or ad group level). 


### Arguments
|Name|Type|Description|
|-|-|-
language|string|The language used by ads in the ad group. For example, English. The string is case insensitive. Do not use a two-character language code. For a list of supported languages, see [Ad Languages](/bingads/guides/ad-languages#adlanguage).

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the language applied.

## <a name="withname-string-name-"></a>withName(string name)
Sets the ad group's name.

### Arguments
|Name|Type|Description|
|-|-|-
name|string|The ad group's name. The name is required. The name may contain a maximum of 256 characters and must be unique amongst all active ad groups in the campaign.

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the name applied.



## <a name="withstartdate-string-startdate-"></a>withStartDate(string startDate)
Sets the date when you want ads in the ad group to start serving. Call this method only if you want ads in the group to start serving on a specific date; otherwise, ads start serving immediately.

### Arguments
|Name|Type|Description|
|-|-|-
endDate|string|The date when you want ads in the ad group to start serving. Specify the date in the form, YYYYMMDD.

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the start date applied.

## <a name="withstartdate-object-startdate-"></a>withStartDate(Object startDate)
Sets the date when you want ads in the ad group to start serving. Call this method only if you want ads in the group to start serving on a specific date; otherwise, ads start serving immediately.

### Arguments
|Name|Type|Description|
|-|-|-
endDate|Object|The date when you want ads in the ad group to start serving. Specify the date using an object with the following fields:<br /><ul><li>year</li><li>month</li><li>day</li></ul><br />For example: `var date = {year: 2018, month: 5, day: 13};`<br /><br />The month is one-based where 1 is January and 12 is December.

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the start date applied.


## <a name="withstatus-string-status-"></a>withStatus(string status)
Sets the ad group's status. 

### Arguments
|Name|Type|Description|
|-|-|-
status|String|The ad group's status. The following are the possible case-sensitive values. <br/><ul><li>ENABLED</li><li>PAUSED</li><li>REMOVED</li></ul>The default is PAUSED. 

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the status applied.


## <a name="withtrackingtemplate-string-trackingtemplate-"></a>withTrackingTemplate(string trackingTemplate)
Sets the tracking template used by this ad group. 

[!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Arguments
|Name|Type|Description|
|-|-|-
trackingTemplate|string|The tracking template to use with the ad group.

### Returns
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder.md)|Ad group builder with the tracking template applied.



## See also

[Campaign.newAdGroupBuilder()](Campaign.md#newadgroupbuilder)