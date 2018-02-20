# ExecutionInfo
Provides information about the environment in which the current script is executing.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[getRemainingCreateQuota](#getremainingcreatequota)|int|Returns the remaining number of Bing Ads entities this script is allowed to create during its current runtime.<br />
[getRemainingGetQuota](#getremaininggetquota)|int|Returns the remaining number of Bing Ads entities this script is allowed to retrieve during its current runtime.<br />
[getRemainingTime](#getremainingtime)|int|Returns the remaining amount of execution time, in seconds, this script is allowed during its current runtime.<br />
[isPreview](#ispreview)|boolean|Returns true if this script is running in preview mode; false otherwise if it is running in execution mode. <br />
&nbsp;|&nbsp;|&nbsp;

## <a name="getremainingcreatequota"></a>getRemainingCreateQuota
Returns the remaining number of Bing Ads entities this script is allowed to create during its current runtime.


### Returns:
|Type|Description|
|-|-
int|The remaining number of entities the script is allowed to create in this execution.
&nbsp;|&nbsp;
## <a name="getremaininggetquota"></a>getRemainingGetQuota
Returns the remaining number of Bing Ads entities this script is allowed to retrieve during its current runtime.


### Returns:
|Type|Description|
|-|-
int|The remaining number of entities the script is allowed to fetch in this execution.
&nbsp;|&nbsp;
## <a name="getremainingtime"></a>getRemainingTime
Returns the remaining amount of execution time, in seconds, this script is allowed during its current runtime.


### Returns:
|Type|Description|
|-|-
int|The remaining time in seconds the script is allowed to execute.
&nbsp;|&nbsp;
## <a name="ispreview"></a>isPreview
Returns true if this script is running in preview mode; false otherwise if it is running in execution mode. 


### Returns:
|Type|Description|
|-|-
boolean|true if the script is currently being previewed, or false if it is a live execution.
&nbsp;|&nbsp;
