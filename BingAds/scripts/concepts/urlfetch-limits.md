---
title: "UrlFetch limits"
description: "Identifies the limits for fetching resources from the web."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# UrlFetch limits

If you use [UrlFetchApp](../reference/UrlFetchApp.md) to fetch resources from the web, the following are the limits you need to know about.

- The maximum request size is 10 MB.
- The maximum response size is 10 MB.
- The maximum size of all headers (header name and content) is 8 KB.
- The maximum number of headers in the request or response is 100.
- The maximum number of `fetch()` calls you may make per day is 20,000.
- The maximum amount of time the request may take is 30 seconds. 