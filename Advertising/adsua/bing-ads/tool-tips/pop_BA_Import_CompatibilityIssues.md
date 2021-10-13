---
title: Compatibility issues
description: Compatibility issues
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Compatibility issues

Microsoft Advertising and Google Ads are slightly different in how they handle your campaign data. As a result, when you import campaigns, there can be data  that doesn't match our requirements or that we can't import. That data will be categorized as either **warnings** or **errors**:

- **Warnings:**  We found a problem, but we'll still import the impacted item. For example, if you are trying to import an ad group that has targeting locations that Microsoft Advertising doesn't support, we'll still import the ad group, but we'll skip the problematic targeting locations. Any targeting locations that are supported will be imported.
- **Errors:**  We found a problem, and we can't import the item unless the issue is resolved. For example, you'll see an error if you import keywords with bids below $0.05, which is the Microsoft Advertising minimum. If you don't fix this issue by increasing the keyword bid to $0.05, we won't import the keyword.

To fix errors now, click **Resolve Errors**. To fix errors later, click **Export all unresolved issues to a spreadsheet**. This will download a file with all of the errors for you to fix, and then you can upload the spreadsheet by importing the file.


