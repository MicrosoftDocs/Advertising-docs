---
title: Import your Google Merchant Center product offers to Microsoft Merchant Center
description: Learn how to easily import your Google Merchant Center offers to Microsoft Merchant Center.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Import your Google Merchant Center product offers to Microsoft Merchant Center

[!INCLUDE [MSCampaignsandProductAdsAvailableinCountries](./includes/MSCampaignsandProductAdsAvailableinCountries.md)]
If you have product ads in your Google Merchant Center, you can easily import them into your Microsoft Merchant Center with the Google Import tool. See the item details that will determine [ which product offers get imported from Google Merchant Center.](./hlp_BA_CONC_BMC_GMCImportOffers.md)

## Why use the Google Merchant Center import tool?

- **Save time** . Spend less time maintaining two separate feed files for Google Ads and Microsoft Advertising.
- **Import products easily** . The Google Merchant Center import tool makes it easy to import product offers into Microsoft Merchant Center.
- **Keep your product feeds fresh** . Sync your Google Merchant Center product offers with Microsoft Merchant Center to keep them up-to-date. You can do this manually or automatically through scheduled imports.

Check out the item details that will determine which product offers get imported from Google Merchant Center.

## How do I import a single Google Merchant Center store's offers?
Follow these steps to start a new import.          Note: If you’ve created feeds previously or have existing feeds in your store, you can associate these feeds into your import to help save you time and effort.

1. On the top menu, select **Tools** and then select ** Microsoft Merchant Center**  (or from the global menu at the top of the page, select **Tools** and then **Microsoft Merchant Center**).
1. Select the Microsoft Merchant Center store you want to import to.
1. Select the **Import** tab.
1. Sign in to your Google account. If you have already signed in to your Google account previously, your sign in will still be valid and you can select **Continue**
1. Select **Create new feed** and enter the **Feed name** and select the **              Target country/market &amp; language**. Select**Create**.
1. Select the Microsoft Advertising feeds you want to import into from Google Merchant Center.
1. Select **Continue**.
1. You have options on **When** to run your import. You can opt to run a one-time import immediately by choosing **Now** from the list, or you can schedule a daily, weekly, or monthly recurring import that starts at a specific time.
1. **Notification settings**: If you create a schedule recurring import, you can opt to receive an email every time there's an import, an email only when there are issues with the import, or no emails at all. You'll also need to add a **Schedule name** for a recurring import.             Tip: Notifications will be sent to the contact details on file in the store's settings. There, you'll be able to update email addresses as needed.
1. Use **Find and replace string in URL** to replace tracking metadata that you use in Google Merchant Center. For example, you will want to **Find** instances of "Google" and **Replace** it with "Bing" so that you can correctly attribute clicks. (Add a check to the box to show **Find** and **Replace**.)
1. Select **Continue**.
1. Take a moment to review a summary of the import. Select **Import** if you're running a one-time import, or select **Save** if you're scheduling an import.

To view specific details about your feeds, select the **Feed name** from the table in the **Feed management** tab. Here, you can view the **Feed summary** and **Feed settings**. You can also see the import details in the **Choose import options** step of the import process.

## How do I import a Google Merchant Center store from a Google account that has multiple stores?
Follow these steps to start a new import. If you've imported feeds before, you'll be prompted to associate new feeds into your import to help save you time and effort.

1. On the top menu, select**Tools** and then select ** Microsoft Merchant Center**  (or from the global menu at the top of the page, select **Tools** and then **Microsoft Merchant Center**).
1. Select the Microsoft Merchant Center store you want to import to.
1. Select the **Import** tab.
1. Sign in to your Google account. If you have already signed in to your Google account previously, your sign in will still be valid and you caselect **Continue**.
1. Under **Choose your Google Merchant Center** account, select the Google store you want to import and select **Continue**.
1. Under **Choose import options**, you can **Create new feed** or select from the existing Microsoft Advertising feed list to import into.
1. Select **Continue**.
1. You have options on **When** to run your import. You can opt to run a one-time import immediately by choosing **Now** from the list, or you can schedule a daily, weekly, or monthly recurring import that starts at a specific time.
1. **Notification settings**: If you create a schedule recurring import, you can opt to receive an email every time there's an import, an email only when there are issues with the import, or no emails at all. You'll also need to add a **Schedule name** for a recurring import.             Tip: Notifications will be sent to the contact details on file in the store's settings. There, you'll be able to update email addresses as needed.
1. Use **Find and replace string in URL** to replace tracking metadata that you use in Google Merchant Center. For example, you will want to **Find** instances of "Google" and **Replace** it with "Bing" so that you can correctly attribute clicks. (Add a check to the box to show **Find** and **Replace**.)
1. Select **Continue**.
1. Take a moment to review a summary of the import. Select **Import** if you're running a one-time import, or select **Save** if you're scheduling an import.

To view specific details about your feeds, select the **Feed name** from the table in the **Feed management** tab. Here, you can view the **Feed summary** and **Feed settings**.

## How do I manage scheduled imports from Google Merchant Center?
Go to the Scheduled Imports section of the Imports tab in Microsoft Merchant Center. There, you'll see your list of scheduled imports, and you can:

- Refresh your offers by starting an import for all or selected feeds
- Edit the default schedule for a selected feed
- Pause or delete a scheduled import

Remember that an import's default schedule is first set when the import is created. To edit an import schedule, you have two choices: you can customize the import schedule for one feed in an import, or modify the import schedule for all feeds that use the default schedule.

Also, keep in mind that if you have a scheduled import but sign out of your Google Merchant Center account, the scheduled import will continue to run. To stop the import, you must delete the scheduled import.

## To change the schedule for one feed

Let's say that you have an import with three feeds. The default schedule to import all three feeds is for Monday, 8 AM Pacific Time. You want to revise the import schedule for one of the three feeds by having it import daily.

1. On the top menu, select **Tools** and then select **Microsoft Merchant Center**.
1. Select the **Import** tab.
1. Find the feed with the schedule that you want to modify.
1. Select the pencil icon ![pencil icon](../images/BA_icon_edit.png) in the **When** column.
1. You'll see a form where you can change the frequency of the import (**When**), the **Day of the week**, the **Time**, and the **Time zone**.         Note: If you've modified a feed's import schedule and you want to change it back to its default, select the check box next to **Use default schedule** in this same form.
1. Select **Save** when you're finished.

## To refresh feeds at any time

If you don't want to wait for the next scheduled import to pull in new feed data, you can refresh your feeds by starting an import at any time. You don't need to schedule a new import to do this.

1. On the top menu, select **Tools** and then select **Microsoft Merchant Center**.
1. Select the **Import** tab.
1. Find the import that contains the feeds you want to refresh. Use the check boxes to select the individual feeds to refresh or select the top check box in the column to refresh all feeds.
1. Select **Import selected feeds now.**
1. Select **Import** when you're prompted to confirm your selection.

## To change the import schedule for all feeds that use the default schedule

Take note that changing the default schedule will only apply to the feeds that use the default schedule. Feeds with customized import schedules will retain its customized schedules even if the overall default schedule is changed. Start by:

1. On the top menu, select **Tools** and then select **Microsoft Merchant Center**.
1. Select the **Import** tab.
1. Find the import that has the default schedule you want to change.
1. Select the pencil icon ![pencil icon](../images/BA_icon_edit.png) to the right of the schedule name.
1. You'll see a form where you can change the frequency of the import (**When**), the **Day of the week**, the **Time**, and the **Time zone**.
1. Select **Save** when you're finished.

## Associating new feeds to existing scheduled imports

Microsoft Merchant Center detects new feeds added to Google Merchant Center. From the Scheduled Imports tab, you'll be alerted of feeds that can be associated to existing imports.

1. From the alert banner, select **add to an existing scheduled import**.
1. You'll be taken to a new page that contains a list of Google Merchant Center feeds that are not associated to an import to Microsoft Merchant Center. Use the drop-down list to assign a feed to an existing import. (Note that each location can only have one feed. For example, you'll receive an error if you try to assign two feeds to the United States.)
1. Select **Save** when you're finished.

## To pause a scheduled import

1. On the top menu, select **Tools** and then select ** Microsoft Merchant Center**  (or from the global menu at the top of the page, select **Tools** and then **Microsoft Merchant Center**).
1. Select the **Import** tab.
1. Find the import you want to pause.
1. Slide the switch to the left to pause the scheduled import for all feeds. (To resume the import, just slide the  same switch to the right.)

## To delete a scheduled import

Keep in mind that deleting a scheduled import does not delete the offers from that feed. It only deletes the scheduled import.

1. On the top menu, select **Tools** and then select ** Microsoft Merchant Center**  (or from the global menu at the top of the page, select **Tools** and then **Microsoft Merchant Center**).
1. Select the **Import** tab.
1. Find the import you want to delete.
1. To the right of **Default schedule**, you'll see **Delete this schedule**. Select that link.
1. You'll see a box asking you to confirm the deletion. Select **Delete**.

## Troubleshooting import errors
If you encounter errors as you import from Google Merchant Center, we'll guide you on how to fix the error from Microsoft Merchant Center. This list of [fixes to common issues in Microsoft Merchant Center](./hlp_BA_CONC_BMC_GMCImportErrors.md) may also be useful for you.

## Shipping information for Germany
- If there is no shipping information associated with the offers when importing offers targeting the German market, the shipping data for that market based on the Google Merchant Center store's shipping settings will also be imported.
- If there are multiple shipping options for a product, the lowest shipping value will be applied.
- To import the Google Merchant Center store shipping information, you must log in using a Google Merchant Center account that has admin-level access.

## What you need to know
- You must create your Microsoft Merchant Center store prior to using the Google Merchant Center Import tool.
- The Google Merchant Center Import tool imports all offers from Google Merchant Center including pending and disapproved offers.
- Only Google Merchant Center offers that target Microsoft Shopping Campaigns markets supported by Microsoft Advertising will be imported. The following languages and markets supported are:                      Danish: Denmark			  Dutch: Netherlands           English: Australia, Canada, India, United Kingdom, United States           Finnish: Finland           French: Belgium, France           German: Austria, Germany, Switzerland           Irish: Ireland			  Italian: Italy        Norwegian: Norway			  Spanish: Spain			  Swedish: Sweden
- Import offers will expire after 30 days. Your offers need to be imported at least every 30 days to stay up-to-date in the system.


