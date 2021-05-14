---
title: Goal value
description: Goal value
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Goal value

You can assign a constant goal value for your goals here through the Microsoft Advertising website. However, you also have the option of creating dynamic, or variable, goal values for both destination goals and event goals by writing your own JavaScript code. This dynamic value is used to calculate the "revenue" of conversions in performance reports.     Here is a template for that code:

```
</script>   window.uetq = window.uetq || [];   window.uetq.push ('event', '', {'revenue_value': 'Replace_with_Revenue_Value', 'currency': 'Replace_with_Currency_Code'});</script>
```

To see the complete list of currency codes, see [Conversion Goal Revenue Currencies](https://go.microsoft.com/fwlink?LinkId=834524). You can remove the 'currency' parameter if no currency is set in the conversion goal.


