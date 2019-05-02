---
title: "Microsoft Advertising Scripts Changes and Text Logs"
description: "Describes how logging works in Microsoft Advertising Scripts."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Change logs and text logs

[!INCLUDE[preview-note](../includes/preview-note.md)]

Microsoft Advertising Scripts provides two types of logs: change logs and text logs.

## Change Log
Change logs list all changes that a script makes to Microsoft Advertising entities. Details include Changed item, Type of change, Current value, New value, and Status. To view the change log, click **Changes** below the script editor.

## Text Log
To write text to the text log, call the [Logger](../reference/Logger.md) object's `log()` method. Writing text to the text log is useful for debugging scripts or just capturing script activity. For example, the following code prints all campaign names and progress messages to the text log.

```javascript
var campaigns = AdsApp.campaigns().get();
Logger.log('retrieved ' + campaigns.totalNumEntities() + ' campaigns');
while (campaigns.hasNext()) {
    var campaign = campaigns.next();
    Logger.log('Campaign: ' + campaign.getName());
}
Logger.log('script complete');
```

In addition to output from the `log()` method, [errors and warnings](./errors-and-warnings.md) are automatically output to the text log. To view the text log, click **Logs** below the script editor.

To view the change logs and text logs for scripts that run on a schedule or were running when you logged out, click **View details** on Scripts home page.