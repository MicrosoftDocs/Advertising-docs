---
title: "Microsoft Advertising Scripts IDs"
description: "Describes how IDs are handled in Microsoft Advertising Scripts."
author: eric-urban
ms.author: eur
ms.service: "bing-ads-scripts"
ms.topic: "article"
---

# Defining IDs in scripts

[!INCLUDE[preview-note](../includes/preview-note.md)]

IDs in Scripts are strings not integers. For example, when calling a selector's `withIds()` method, you pass an array of string IDs, not an array of integer IDs. Or, if you call an entity's `getId()` method, it returns the ID as a string, not an integer.
