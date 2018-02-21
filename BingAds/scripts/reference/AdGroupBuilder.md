# AdGroupBuilder
Provides methods which can be used to define and build an ad group.

Example usage:
```javascript
 var adGroupBuilder = campaign.newAdGroupBuilder();
 var adGroupOperation = adGroupBuilder
    .withName("ad group name")
    .withStatus("PAUSED")
    .build();
 var adGroup = adGroupOperation.getResult();
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[build](#build)|[AdGroupOperation](./AdGroupOperation)|Returns an ad group operation which represents the ad group to be created.<br />
[withBiddingStrategy(String biddingStrategy)](#withbiddingstrategy~string-biddingstrategy~)|[AdGroupBuilder](./AdGroupBuilder)|Sets the type of bidding strategy for the new ad group.
[withCpc(double cpc)](#withcpc~double-cpc~)|[AdGroupBuilder](./AdGroupBuilder)|Sets the maximum CPC bid to be used for this new ad group. If no CPC is specified, the default of 0.30 will be specified.<br />
[withCustomParameters(Object customParams)](#withcustomparameters~object-customparams~)|[AdGroupBuilder](./AdGroupBuilder)|Sets the custom parameters for the new ad group.
[withName(String name)](#withname~string-name~)|[AdGroupBuilder](./AdGroupBuilder)|Sets the name of this new ad group. <br />
[withStatus(String status)](#withstatus~string-status~)|[AdGroupBuilder](./AdGroupBuilder)|Sets the status of this new ad group to the provided value. If no value is given, the default value of `ENABLED` is set.<br />
[withTrackingTemplate(String trackingTemplate)](#withtrackingtemplate~string-trackingtemplate~)|[AdGroupBuilder](./AdGroupBuilder)|Sets the tracking template to be used with this new ad group.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="build"></a>build
Returns an ad group operation which represents the ad group to be created.

### Returns:
|Type|Description|
|-|-
[AdGroupOperation](./AdGroupOperation)|The associated ad group operation.
&nbsp;|&nbsp;
## <a name="withbiddingstrategy~string-biddingstrategy~"></a>withBiddingStrategy(String biddingStrategy)
Sets the type of bidding strategy for the new ad group. 

Possible values are:

- MANUAL_CPC

### Arguments:
|Name|Type|Description|
|-|-|-
biddingStrategy|String|The standard bidding strategy of the ad group.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder)|The ad group builder with the specified bidding strategy.
&nbsp;|&nbsp;
## <a name="withcpc~double-cpc~"></a>withCpc(double cpc)
Sets the maximum CPC bid to be used for this new ad group. If no CPC is specified, the default of 0.30 will be specified.

### Arguments:
|Name|Type|Description|
|-|-|-
cpc|double|The max CPC bid of the ad group.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder)|The ad group builder with the specified max CPC.
&nbsp;|&nbsp;
## <a name="withcustomparameters~object-customparams~"></a>withCustomParameters(Object customParams)
Sets the custom parameters for the new ad group.

The name of a custom parameter can contain only alphanumeric characters, and custom parameter values may not contain white space. When referring to the custom parameter in final URLs and tracking templates, you should surround the custom parameter in braces, and prefix an underscore to its name, for example {_param}.

You can have up to 3 custom parameters for an entity. The key and value must not exceed 16 and 200 bytes respectively.

Custom parameters specified at a lower level entity will override the setting specified at a higher level entity, for example, setting custom parameters at the ad group level overrides the setting at the campaign level, and custom parameters specified at the ad level override the setting at the ad group level.

### Arguments:
|Name|Type|Description|
|-|-|-
customParameters|Object|The custom parameters of the ad group as a map of the<br />        following form: <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder)|The ad group builder with the specified custom parameters.
&nbsp;|&nbsp;
## <a name="withname~string-name~"></a>withName(String name)
Sets the name of this new ad group. 

### Arguments:
|Name|Type|Description|
|-|-|-
name|String|Ad group name.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder)|Ad group builder with the specified name.
&nbsp;|&nbsp;
## <a name="withstatus~string-status~"></a>withStatus(String status)
Sets the status of this new ad group to the provided value. If no value is given, the default value of `ENABLED` is set.

### Arguments:
|Name|Type|Description|
|-|-|-
status|String|Ad group status.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder)|Ad group builder with the specified status.
&nbsp;|&nbsp;
## <a name="withtrackingtemplate~string-trackingtemplate~"></a>withTrackingTemplate(String trackingTemplate)
Sets the tracking template to be used with this new ad group.

### Arguments:
|Name|Type|Description|
|-|-|-
trackingTemplate|String|The tracking template for the ad group.
&nbsp;|&nbsp;|&nbsp;
### Returns:
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder)|The ad group builder with the specified tracking template.
&nbsp;|&nbsp;
