---
title: "Structuring Microsoft Advertising scripts"
description: "Describes how to structure scripts."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bing-ads-scripts"
ms.topic: "article"
---

# Scripts must have a Main function

[!INCLUDE[preview-note](../includes/preview-note.md)]

Unlike JavaScript that executes in a browser, Microsoft Advertising scripts must define a `main()` function. The main function is the script's entry point and contains the program logic you want to execute. The script may also define custom functions. For example, the following script defines a main function that calls a custom function named getAllCampaigns.

```javascript
function main() {
    getAllCampaigns();
}

function getAllCampaigns() {
  var campaigns = AdsApp.campaigns().get();
    while(campaigns.hasNext()){
        var campaign = campaigns.next();
    }
}
```

