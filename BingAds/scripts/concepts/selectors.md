---
title: "Bing Ads Scripts Selectors"
description: "Describes how selectors work in the Bing Ads Scripts system."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Selectors

Selector is a type of class that provides methods to filter objects in Bing Ads Scripts using a SQL-like mechanism. The following standard methods are provided on all selector classes:

- <code>withCondition()</code> – uses a SQL-like clause to select objects. For example, `Name STARTS_WITH 'Contoso'`
- <code>withIds()</code> – uses a collection of IDs to select specific objects. It is analogous to a SQL `IN` clause.
- <code>forDateRange()</code> – returns elements matching a date range, such as `LAST_14_DAYS`.
- <code>orderBy()</code> – orders the returned elements by specified field, for example `Clicks DESC`.
- <code>withLimit()</code> – returns only the specified number of elements; analogous to `SQL TOP(x)` clause.

Multiple conditions can be AND-ed to filter more narrowly. Filters are recommended to be used before getting iterator for efficient performance.
