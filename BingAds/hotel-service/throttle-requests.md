---
title: "Throttling Requests"
ms.service: "hotel-ads-hotel-service"
ms.topic: "article"
author: "swhite-msft"
ms.author: "scottwhi"
description: 
---
# Throttling Requests
To ensure resources for everyone, the API limits the number of requests a customer ID may make per minute. The limit is not documented and is subject to change.

If you exceed the request per minute limit, the API returns HTTP status code 429. When you receive status code 429, you must wait 60 seconds before resubmitting the request.

Ensure your application contains the logic necessary to recover from status code 429.
