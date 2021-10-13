---
title: How to define your destination URL
description: How to define your destination URL
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How to define your destination URL

There are three different ways to define how Universal Event Tracking identifies a URL to track for your goals: equal to, begins with, or regular expression.

**Equal to (use for exact URLs)** : If you want to track a specific URL that doesn't have any changing variables, use **equals to** and UET will track the URL exactly as you define it from the first to last character.

**Begins with (use to eliminate trailing URL parameters)** : If you want to track a instances of a URL that has changing variables at the end of the URL, use **begins with** and UET will track the URL up until the specific text you define.

**Regular expression (use to define various URL components)** : Regular expressions are sets of characters and symbols that you can use to define URL patterns and text for UET to track. In general, think of what you want the tracked URL to contain when defining your regular expression.

> [!NOTE]
> For examples of how to define destination URLs using these three inputs, read the "Setting up" section in our [FAQ: Universal Event Tracking](../hlp_BA_CONC_UET_FAQ.md).
> UET will still match the URL for "begins with" and "equals to" if you don't enter "http(s)" and/or "www" when defining the URL. The input is also not case-sensitive.
> Please read our [Microsoft Advertising API doc](https://go.microsoft.com/fwlink?LinkId=512213) for in-depth technical information about regular expressions.


