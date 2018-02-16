# BingAdsApp
This is the root object of the Bing Ads Scripts API. It provides methods to retrieve different types of entities from the Bing Ads system for the current account.

This is a test for adding additional information.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[adGroups](#adgroups)|[AdGroupSelector](./AdGroupSelector)|Returns a selector of all ad groups in the current account.<br />
[ads](#ads)|[AdSelector](./AdSelector)|Returns a selector of all ads in the current account.<br />
[campaigns](#campaigns)|[CampaignSelector](./CampaignSelector)|Returns a selector of all campaigns in the current account.<br />
[currentAccount](#currentaccount)|[Account](./Account)|Returns the account in which the script is currently executing.<br />
[getExecutionInfo](#getexecutioninfo)|[ExecutionInfo](./ExecutionInfo)|Returns information about the environment in which the script is currently executing.<br />
[keywords](#keywords)|[KeywordSelector](./KeywordSelector)|Returns a selector of all keywords in the current account.<br />
&nbsp;|&nbsp;|&nbsp;

## <a name="adgroups"></a>adGroups
Returns a selector of all ad groups in the current account.

### Returns:
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector)|The selector of all ad groups in the campaign.
&nbsp;|&nbsp;
## <a name="ads"></a>ads
Returns a selector of all ads in the current account.

### Returns:
|Type|Description|
|-|-
[AdSelector](./AdSelector)|The selector of all ads in the current account.
&nbsp;|&nbsp;
## <a name="campaigns"></a>campaigns
Returns a selector of all campaigns in the current account.

### Returns:
|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector)|Selector of all campaigns that share this budget.
&nbsp;|&nbsp;
## <a name="currentaccount"></a>currentAccount
Returns the account in which the script is currently executing.

### Returns:
|Type|Description|
|-|-
[Account](./Account)|The account in which the script is currently executing.
&nbsp;|&nbsp;
## <a name="getexecutioninfo"></a>getExecutionInfo
Returns information about the environment in which the script is currently executing.

### Returns:
|Type|Description|
|-|-
[ExecutionInfo](./ExecutionInfo)|Information about the environment in which the script is currently executing.
&nbsp;|&nbsp;
## <a name="keywords"></a>keywords
Returns a selector of all keywords in the current account.

### Returns:
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector)|Selector of all keywords in the current account.
&nbsp;|&nbsp;
