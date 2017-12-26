# BingAdsApp
This is the root object of the Bing Ads Scripts API. It provides methods to retrieve different types of entities from the Bing Ads system for the current account.

|Method|Return Type|Description|
|-|-|-
adGroups|[AdGroupSelector](./AdGroupSelector)|Returns a selector of all ad groups in the current account.<br />
ads|[AdSelector](./AdSelector)|Returns a selector of all ads in the current account.<br />
campaigns|[CampaignSelector](./CampaignSelector)|Returns a selector of all campaigns in the current account.<br />
currentAccount|[Account](./Account)|Returns the account in which the script is currently executing.<br />
getExecutionInfo|[ExecutionInfo](./ExecutionInfo)|Returns information about the environment in which the script is currently executing.<br />
keywords|[KeywordSelector](./KeywordSelector)|Returns a selector of all keywords in the current account.<br />
