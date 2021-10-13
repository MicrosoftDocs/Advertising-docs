---
title: Understanding negative keyword conflicts and their reports
description: "Possibly intentional" negative keyword conflicts
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Understanding negative keyword conflicts and their reports

You can use [negative keywords](./hlp_BA_CONC_AboutNegativeKeywords.md) to help prevent your ads from being displayed to customers who are unlikely to click them. However, if you choose a negative keyword that is identical to an existing keyword, it will result in a conflict.

Possible conflict types are:

**        Possibly intentional:      **      Some advertisers **intentionally** create negative keyword conflicts to block a portion of match types from triggering your ads.  For example, if your phrase match keyword is “stereo plug”, you might also choose “stereo plug” as your exact match negative keyword text to match only with this phrase. In this scenario, customers that are searching for specific items like “3.5mm stereo plug” or “gold stereo plug” are more likely to see your ad.

If you intentionally created this conflict to block certain match types from triggering your ads, no action may be required.

- **True:**      Any other negative keyword conflict. This conflict can be resolved by deleting the conflicting negative keyword.

## Run a negative keyword conflict report

This report shows negative keywords that are conflicting with some of your keywords, therefore blocking your ads from showing. It can tell you which ones are in conflict, whether the conflict is at the campaign or ad group level, and then help you determine which negative keywords to delete.
1. [!INCLUDE [ReportNKWConflicts](./includes/ReportNKWConflicts.md)]
1. Choose the settings for **Show (unit of time)**, **Date range**, and **Format**.
1. For **What to report on**, choose either **All accounts and campaigns**, or choose **Specific accounts and campaigns**.
1. You can **Choose your columns** to display and add **Filters** to your report.
1. **Run** the report or **Download** it as CSV, TSV, or XLSX.

## Run a product negative keyword conflict report

Product negative keyword conflict reports show negative keywords and the corresponding product ads that are prevented from showing in your shopping campaigns. It can help you assess whether the negative keywords applied to your shopping campaigns are excessively restricting your campaign performance.
1. [!INCLUDE [ReportProductNegKeyConflicts](./includes/ReportProductNegKeyConflicts.md)]
1. Choose the settings for **Show (unit of time)**, **Date range**, and **Format**.
1. You can **Choose your columns** to display and add **Filters** to your report.
1. **Run** the report or **Download** it as CSV, TSV, or XLSX.

> [!NOTE]
> Please note that the **Conflict type** column, which shows “possibly intentional” or “true,” is not available in product negative keyword conflict reports.


