---
title: "Release notes"
description: Identifies the changes made to Hotel Ads for each release.
ms.service: "hotel-ads"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
---

# Best practices

## Retrieving hotels

Do not use the following calls to download all of your hotels. Instead, to retrieve all hotels, use the reporting feature (see [Reporting](reporting.md)). These calls are meant only for users paging through hotels in a user interface.

- [SubAccounts('{subAccountId}')/Hotels](reference.md#listallhotels)
- [SubAccounts('{subAccountId}')/HotelGroups('{hotelGroup}')/Hotels](reference.md#listhotels)
- [SubAccounts('{subAccountId}')/Ungrouped](reference.md#ungrouped)

