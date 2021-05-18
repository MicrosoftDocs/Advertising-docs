---
title: Edit your scheduled imports and review import history and results
description: You can edit your scheduled imports and review import history and results.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Edit your scheduled imports and review import history and results

Import schedule and history is available for imports from Google Ads and Facebook Ads. You can run an import again, modify the import schedule, and review logs to see what entities were newly added, updated, or couldn’t be imported.

> [!NOTE]
> You cannot schedule file imports.

## Review import results

You can review any past imports. If there were any issues with the import, the **Logs** (results) table includes the error file to review as well the settings that were in effect at the time of the import.

1. From the global menu at the top of the page, select **Import **** > ** **Import schedule &amp; history**.
1. Under **Logs**, review the table.
1. If the import resulted in any changes, the **Summary** column will show how many items were imported successfully and how many had errors and were unsuccessful. Select the ellipsis icon ![More information icon](../images/BA_ScreenCap_DeliveryDetails.png), to review the details.
1. To download and review the error file, in the **Action** column, select **Download error file**.

## Edit, pause, or delete your import schedule

1. From the global menu at the top of the page, select **Import **** > ** **Import schedule &amp; history**.
1. Under **Scheduled imports**, review the table. If the table is empty, no schedule is set.
1. If you want to change the schedule, in the **Action** column, select **Edit**.
1. To pause a scheduled import, select it and then select **Edit** and **Pause**.
1. To delete a scheduled import, select it and then select **Edit** and **Delete**.

## Scheduling options

You can schedule when you want your Google Ads or Facebook Ads accounts to sync automatically with Microsoft Advertising. You cannot schedule file imports. The options are:

- **Auto:** Allows Microsoft Advertising to set an import schedule to best optimize your campaigns.
- **Now:**  Import happens as soon as you select the **Import**  button and only runs once.
- **Once:**  Import happens at the time you specify and only runs once.
- **Daily:**  Import happens once a day at the time you specify until you delete or pause the schedule on the Import schedule and history page.
- **Weekly:**  Import happens once a week at the time you specify until you delete or pause the schedule on the Import schedule and history page.
- **Monthly:**  Import happens once a month at the time you specify until you delete or pause the schedule on the Import schedule and history page.

> [!NOTE]
> Scheduling multiple imports at once may affect their overall start time and import speed.
> The update count reports all existing items that are fetched from Google Ads. It may be higher than the actual number of updates because it includes items that may not have been updated since the previous import.
> Scheduled imports will fetch items that have changed in Google Ads since your last import. To re-import items that haven’t changed in Google Ads but have changed in Microsoft Advertising, select **Import Campaigns** > **Import schedule and history** > **Run now**.
> Change history reports the actual number of updates in Microsoft Advertising. It may be lower than the update count as it excludes items that do not have updates.


