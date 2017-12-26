# ExecutionInfo
Provides information about the environment in which the current script is executing.

|Method|Return Type|Description|
|-|-|-
getRemainingCreateQuota|int|Returns the remaining number of Bing Ads entities this script is allowed to create during its current runtime.<br />
getRemainingGetQuota|int|Returns the remaining number of Bing Ads entities this script is allowed to retrieve during its current runtime.<br />
getRemainingTime|int|Returns the remaining amount of execution time, in seconds, this script is allowed during its current runtime.<br />
isPreview|boolean|Returns true if this script is running in preview mode; false otherwise if it is running in execution mode. <br />
