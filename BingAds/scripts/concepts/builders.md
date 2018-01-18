---
title: "Bing Ads Scripts Builders"
description: "Describes how builders work in the Bing Ads Scripts system."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Builders

Used to create new entities in Bing Ads Scripts. It is possible to create entity synchronously or asynchronously. Creating entities is a two-stage process:

- Defining the entity by means of the builder object which returns an operation object.
- Invoking any of the methods on the operation object creates the actual entity.

