# ExecutionInfo
Provides information about the environment in which the current script is executing.


Example usage:
```javascript
var executionInfo = BingAdsApp.getExecutionInfo();
if(executionInfo.isPreview()) {
    Logger.log("script is running in preview mode.");
} else {
    Logger.log("script is running in live mode.");
}
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[isPreview](#ispreview)|Boolean|Returns a Boolean value that indicates if this script is executing in preview mode.

## <a name="ispreview"></a>isPreview
Returns a Boolean value that indicates if this script is executing in preview mode.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this script is executing in preview mode.

