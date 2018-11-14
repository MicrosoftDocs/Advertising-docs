---
title: "Bing Ads Scripts Quickstart"
description: "Shows you how to get started quickly using Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Get Started With Bing Ads Scripts

[!INCLUDE[preview-note](./includes/preview-note.md)]

Accessing your Bing Ads data with Bing Ads Scripts is easy. Just follow these instructions and you'll be accessing your data in no time.

1. Sign in to [Bing Ads](https://secure.bingads.microsoft.com/) or [Bing Ads Sandbox](https://sandbox.bingads.microsoft.com/).
2. From the **Campaigns** tab click **Bulk Operations** (in the left navigation panel).
3. Click **Create and manage scripts**.
4. Click **Create script**.
5. Replace "Untitled script" with your script's name.
6. Copy and paste the following code into the code editor. This script gets the 15 keywords that generated the least impressions over the last week. This script won't make any changes to your campaign data.

    ```javascript
    function main() {
        var iterator = BingAdsApp.keywords()
            .orderBy("Impressions ASC")
            .forDateRange("LAST_WEEK")
            .withLimit(15)  // up to 15
            .get();
    
        Logger.log("15 keywords with the least impressions over the last week");
        while (iterator.hasNext()) {
            var keyword = iterator.next();
            Logger.log(`${keyword.getText()}: 
                ${keyword.getStats().getImpressions()} impressions`);  //gets the number of impressions
        }
    }
    ```

7. To execute the script in [preview mode](concepts/preview-mode.md) (recommended), click **Preview**.
8. To see the output, click **Logs**.

The difference between **Preview** and **Run script now** is that Preview gives you the chance to see how the script would affect your data without actually committing the changes. If the script modifies data, you should run it in preview mode first. For limitations of Preview mode, see [Running scripts in Preview mode](concepts/preview-mode.md).

For multi-account scripts, you access the Scripts editor from **Accounts Summary** instead of **Campaigns**. To get an account that you manage, use the [AccountsApp](reference/AccountsApp.md) object. After getting the managed account, use the [BingAdsApp](reference/BingAdsApp.md) object to access its entities.


## Next steps

> [!div class="nextstepaction"]
> [Single account access](./guides/single-account-access.md)