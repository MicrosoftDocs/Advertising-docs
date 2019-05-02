---
title: "Microsoft Advertising Scripts entity and execution limits"
description: "Identifies the entity and execution limits for scripts."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Script execution limits

- Script execution is limited to 30 minutes. If the script's execution time exceeds 30 minutes, it's canceled. Any entities that were added or updated before the script was canceled are saved.  
  
- There is no limit on the number of times you can run a script.  
  
- The number of scripts you may have per account is limited to 100.


## Single account limits

These single account limits are the per script (they are not the aggregation of calls across scripts).

- An iterator can return a maximum of 50,000 entities. For example, [KeywordIterator](../reference/KeywordIterator.md) returns a maximum of 50,000 keywords even if [KeywordSelector](../reference/KeywordSelector.md) returns more than 50,000 keywords. When you reach the limit, the iterator's `hasNext` method returns false and Scripts logs a warning.  
  
- A selector's `withIds` method is limited to 10,000 IDs. Scripts throws a runtime error if you specify more than 10,000 IDs. The same is true if you use the selector's `withCondition` method and specify an 'Id IN [LIST]' condition with more than 10,000 IDs.  
  
- A script can get a maximum of 250,000 entities. This means you can get five iterators with each returning a maximum of 50,000 entities. When you reach the limit, the iterator's `hasNext` method returns false and Scripts logs a warning.  
  
- A script can create a maximum of 250,000 keywords and ads. Creating additional entities fail and Scripts logs a warning.  
  
- A script can write a maximum 100 KB of output to the console log. When you exceed the limit, Scripts logs a warning.


## Multi-account limits

- The single account limits listed above apply to each account that a multi-account script processes.  

  The exception is for scripts that call the `executeInParallel` method. If your script calls `executeInParallel`, the script must also complete with within 30 minutes unless you specify a callback function. If you specify a callback function, the callback may take an additional 30 minutes to complete. This means that your script (including the function you execute for each account) has 30 minutes to complete and your callback has 30 minutes to complete. If either takes longer than 30 minutes, the script is canceled and any entities that were added or updated before the script was canceled are saved.  

- The `executeInParallel` method lets your script process up to 50 accounts at the same time.  
    
- The function that `executeInParallel` specifies may return a maximum of 10 MB of data.


## UrlFetch limits

See [UrlFetch limits](urlfetch-limits.md).


## Microsoft Advertising entity limits

For Microsoft Advertising entity limits, see [Entity Hierarchy and Limits](/bingads/guides/entity-hierarchy-limits).

