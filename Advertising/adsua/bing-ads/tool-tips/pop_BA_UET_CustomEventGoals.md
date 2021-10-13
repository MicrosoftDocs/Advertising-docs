---
title: Event goal
description: Event goal
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Event goal

To record an event goal, you must write a snippet of JavaScript code (separate from the UET tag Microsoft Advertising provides) to add to your website. Here is a template for that code:

```
```<script>   								   window.uetq = window.uetq || [];      window.uetq.push ('event', 'Replace_with_Event_Action', {'event_category': 'Replace_with_Event_Category', 'event_label': 'Replace_with_Event_Label', 'event_value': 'Replace_with_Event_Value'});   </script>```
```

**At least one** of the four values below must be defined for event goals to work:

**Category:**   The object you want to track (e.g., a button).

**Action:**   The type of interaction the user takes with the object (e.g., clicks).

**Label:**   Your comments about the event (e.g., "This is the purchase button").

**Value:**   Values must be non-negative and are useful for tracking counts(e.g., A video is paused four times).

**Get more info: **    [Why track custom events](../hlp_BA_PROC_UETv2TrackCustomEvent.md)


