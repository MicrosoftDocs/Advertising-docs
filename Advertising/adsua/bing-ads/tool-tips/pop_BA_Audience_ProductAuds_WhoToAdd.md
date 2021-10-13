---
title: Whom to add to your audience
description: Whom to add to your audience
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Whom to add to your audience

**What it is** : Here you select which type of dynamic remarketing list you want to target and set the time frame for eligible customers.

**What you need to know** : You will need to add the UET tag tracking code that appears here (reporting both Page Type and Product ID) to the appropriate page of your website:
|Dynamic remarketing list|Required page type|
|---|---|
|General visitors|```'home'```  										```'category'```  										```'other'```  |
|Product searchers|```'searchresults'```  |
|Product viewers|```'product'```  |
|Shopping cart abandoners|```'cart'```  |
|Past buyers|```'purchase'```|

**Note** :
- Customers who buy a product are added to the "past buyers" list and are removed from other lists (for that particular product). For this to work, the UET tag on your purchase confirmation page must send both product ID (ecomm_prodid) and pagetype (ecomm_pagetype).
- The minimum time frame is 1 day and the maximum is 180 days.

**Get more info** : [Dynamic remarketing lists: Remarketing for products](../hlp_BA_CONC_Audiences_ProductAudience.md)


