---
title: "Bing Ads Scripts Errors and Warnings"
description: "Describes how errors and warnings are handled in Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Handling errors and warnings in your script

[!INCLUDE[preview-note](../includes/preview-note.md)]

If you try to update an entity’s properties and the update fails, Bing Ads writes a warning message to the [Change Log](./change-and-text-logs.md#change-log). Because Bing Ads does not throw exceptions in this case, you should test each set operation to ensure the update succeeded. For example, the following example attempts to set the campaign’s budget. Because the amount is not valid, the call fails and a warning message is written to the change log.

```javascript
function main() {
    var campaign = BingAdsApp.campaigns().get().next();
    campaign.getBudget().setAmount(-5);
    
    if (campaign.getBudget() != -5) {
        // The budget amount doesn't match what we 
        // attempted to set it to, so the change must 
        // have failed.
    }
}
```

Other errors such as runtime errors or entity retrieval failures cause script execution to stop. When this happens, the error message is written to the [Text Log](./change-and-text-logs.md#text-log). The following code attempts to call the `doSomething` function but because the function is not defined the script terminates execution. 

```javascript
function main() {
    doSomething(); // ReferenceError: 'doSomething' is undefined
    Logger.log('Will not reach this line');
}
```

You should carefully review all messages logged to the [Change logs and Text logs](./change-and-text-logs.md).