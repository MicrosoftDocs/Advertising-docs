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

The only time Bing Ads returns errors is when you add an entity with invalid values. For example, if you try to add a keyword entity with a bid amount that's not valid, the build operation fails and returns one or more errors.

```javascript
        var operation = adGroup.newKeywordBuilder()
            .withText(keywordText)
            .withCpc(-5)
            .build();

        if (operation.isSuccessful()) {
            var keyword = operation.getResult();
            Logger.log(`Added keyword, ${keyword.getText()}.`);
        }
        else {
            for (var error of operation.getErrors()) {
                Logger.log(error);
            }
        }
``` 

However, if you try to update an entity’s properties with an invalid value, Bing Ads does not return an error. Instead, Bing Ads writes an error message to the [Change Log](./change-and-text-logs.md#change-log) and your code will continue executing. Because Bing Ads does not return errors in this case, you should test each set operation to ensure the update succeeded. For example, the following example attempts to set the campaign’s budget. Because the amount is not valid, the call silently fails, the script continues executing, and an error message is written to the change log.

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

Other errors such as runtime errors or entity retrieval failures cause script execution to stop. When this happens, the error message is written to the [Text Log](./change-and-text-logs.md#text-log). The following code attempts to call the `doSomething()` function but because the function is not defined the script terminates execution. 

```javascript
function main() {
    doSomething(); // ReferenceError: 'doSomething' is undefined
    Logger.log('Will not reach this line');
}
```

You should carefully review all messages logged to the change log and text log.

## What does Internal Error mean?

If you receive a runtime error and the text log lists Internal Error, the following are the reasons why you might be getting it.

|Reason|Remedy
|-|-
|An enumeration value you specified is not valid.|Enumeration values are case sensitive, so make sure that all enumeration values are valid and use the correct casing.
|An operator you specified in the `.withCondition()` method is not valid.|Operators are case sensitive, so make sure that all operators are valid and use the correct casing.
|A column you specified in the `.withCondition()` or `.orderBy()` method is not valid.|Column names are case sensitive, so make sure that all column names are valid and use the correct casing.
|You specified too may IDs in the `.withIds()` method.|Reduce the number of IDs to the allowed maximum (see documentation for the method).
|The date range specified in the `.forDateRange()` method is not valid.|Make sure that the start and end dates are valid and that the end date is not earlier than the start date.