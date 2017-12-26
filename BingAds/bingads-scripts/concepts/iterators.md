---
title: "Bing Ads Scripts Iterators"
description: "Describes how iterators work in the Bing Ads Scripts system."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Iterators

Used to enumerate a list of objects in most Bing Ads entity selectors such as keywords. It is not possible to directly access ```i```th element like in an array. The common methods are defined for an iterator:

- <code>boolean hasNext()</code> – returns true if next position for pointer is not at the last element in list
- <code>Object next()</code> – returns the object at the next position of the pointer
- <code>totalNumEntities()</code> – returns the number of items in iterator
