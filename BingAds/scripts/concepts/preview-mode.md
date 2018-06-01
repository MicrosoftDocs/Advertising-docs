---
title: "Bing Ads Scripts Preview Mode"
description: "Describes how preview mode works in Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Running scripts in Preview mode

[!INCLUDE[preview-note](../includes/preview-note.md)]

Preview mode lets you test your script without actually making changes to the data. Instead, you’re shown the results as if the script were executed. This can reduce the amount of time spent setting up test cases. When you're satisfied with the script's output, you can run the script or schedule it to run later.

Preview mode is specific to Bing Ads components only. Calls to other services execute as normal. For example, if the script sends an email, the email is sent. The same is true for spreadsheet updates. 

<!--
To programmitcally determine if a script is executing in preview mode, see [ExecutionInfo](../reference/ExecutionInfo.md).
-->

Because objects are not created, deleted, or modified in preview mode not all code will execute the same as if it were run live. The following code shows a simple example when the code behaves differently in preview mode versus live mode.

```javascript
// Assume the adgroup has no keywords.
var adGroup = findAnEmptyAdGroup();

// Create a keyword.
adGroup.createKeyword("test");

// Retrieve all keywords in the ad group.
var keywords = adGroup.keywords().get();

// This will log "false" in preview mode because the keyword was not actually created.
// This will log "true" when the script is run live.
Logger.log("Does the ad group have keywords? " + keywords.hasNext());
```

## Next steps

> [!div class="nextstepaction"]
> [Learn how authorization works](./authorization.md)