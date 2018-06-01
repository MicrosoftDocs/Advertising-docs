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
2. From the Campaigns tab expand **Bulk Operations** (in the left navigation panel).
3. Click **Create and manage scripts**.
4. Click **Create script**.
5. Replace "Untitled script" with your script's name.
5. Copy and paste the following code into the code editor. This script gets the 10 keywords with the most impressions yesterday. This script won't make any changes to your campaigns.

    ```javascript
    function main() {
        var keywords = BingAdsApp.keywords()
            .orderBy("Impressions DESC")
            .forDateRange("YESTERDAY")
            .withLimit(10)  // up to 10
            .get();
    
        Logger.log("10 keywords with the most impressions yesterday");
        while (keywords.hasNext()) {
            var keyword = keywords.next();
            Logger.log(keyword.getText() + ": " +
                keyword.getStats.getImpressions());  //gets the number of impressions
        }
    }
    ```

6. To execute the script in [preview mode](concepts/preview-mode.md) (recommended), click **Preview**.
7. To see the output, click **Logs**.

The difference between **Preview** and **Run script now** is that Preview gives you the chance to see how the script would affect your data without actually committing the changes. If the script modifies data, you should run it in preview mode.


### Next steps

> [!div class="nextstepaction"]
> [Learn about selectors](./concepts/selectors.md)