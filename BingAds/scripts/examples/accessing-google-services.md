---
title: "Accessing Google services"
description: "Shows how to access Google services."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Accessing Google services

The following script examples show how to access access Google services, such as Google Drive, Sheets, and Mail.

|Example|Description
|-|-
|[Get a Google access token](getting-access-token.md)|Provides options for getting a Google access token.
|[Increase keyword bids](urlfetch-example.md)|Reads a bid multiplier value from a Google drive file, opens a Google spreadsheet to get a list of keywords to update, updates the bids, and sends an email notification that the keywords were updated.
|[Find disapproved ads](execute-in-parallel.md)|Reads a list of accounts from a Google drive file, uses the [executeInParallel](../reference/BingAdsAccountSelector.md) method to check the accounts for disapproved ads, creates a Google spreadsheet and adds a sheet for each account, writes the list of disapproved ads to the sheet, and sends an email notification to a list of recipients with links to the sheets.

