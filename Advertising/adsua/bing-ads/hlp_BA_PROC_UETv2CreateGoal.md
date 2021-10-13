---
title: How do I create a conversion goal?
description: Learn how to create a conversion goals that allows you to track how many times a certain action, called conversion, happens after someone clicks on your ad.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How do I create a conversion goal?

You create a conversion goal to track actions people take on your website after they click on your ad. When the action matches your conversion goal, it is counted as a conversion.

> [!IMPORTANT]
> For conversion goals to work, Microsoft Advertising needs to be able to collect data from your website. This requires [Universal Event Tracking (UET)](./hlp_BA_CONC_UETv2WhatIsTag.md).

## Create a conversion goal

1. [!INCLUDE [ConversionGoals](./includes/ConversionGoals.md)]
1. Select **Create conversion goal**.
1. Choose the type of conversion you want to track: **Website**, **Mobile app install**, or **Offline**.
1. Select **Next**.
1. Choose a [goal category](./hlp_BA_CONC_UET_GoalCategory.md) from the dropdown menu and then choose a [goal type](./hlp_BA_CONC_UETv2CTGoalType.md).
1. Enter a name for your goal in the **Goal name** box. When naming your goal, use a descriptive name that makes sense to you. (For example, "Checkout page".) Please note that after you choose a name for your conversion goal, the same name may not be used again in the future.
1. Fill in the appropriate values for your selected goal type.
1. If you want to add a monetary value for each conversion, select one of the following from the **Revenue**, dropdown menu:
   - **Each conversion action has the same value**, and then enter the amount and select the currency (if available). This is a static revenue value that doesn't change.
   - **Conversion action value may vary (for instance, by purchase price)**, and then enter the default amount and select the default currency (if available) to be used when no value is received for a conversion. The revenue value will change based on the customization you make to the UET tag tracking code that you add to your website. To learn more, see [How to report variable revenue with UET](./hlp_BA_CONC_UETv2RevenueVariables.md). This option is only available for destination URL and event conversion goals.

1. Fine-tune your conversion goal with **Advanced settings**:
   - Set the **Scope** of this goal to all accounts or a specific account.
   - Change how you **Count** your conversions. [Learn more](./hlp_BA_CONC_UETv2Count.md).
   - Enter a **Conversion window** to track up to 90 days in the past.
   - Set a **View-through conversion window** to track conversions that occur in this period of time after a customer views (but doesn't click) your ad. [Learn more about view-through conversions](./hlp_BA_CONC_ViewThroughConv.md).
   - Check or clear the **Include in "Conversions"** checkbox depending on whether or not you want to track all conversions. Learn more about ["Conversions" versus "All conversions"](./hlp_BA_CONC_ConvsVsAllConvs.md).

1. Select **Next**.
1. Select the UET tag that you want to associate with this conversion goal (not applicable to offline conversions).
1. Choose an answer for **Do you have this UET tag installed on your website?**
> [!NOTE]
> If you choose either **No, this UET tag is not installed on all your website pages** or **I’m not sure. I need instructions to install the tag**, select **Install the tag yourself** or **Send the tag to a developer**. Select **Next** and follow the onscreen instructions. Select **Next** to finish setting up the conversion goal. [Learn more about adding a UET tag to your website](./hlp_BA_PROC_UETv2AddTag.md).

1. Select **Save and next**.
1. (Optional) In the resulting **Conversion goal created!** message, select **test the goal now** to use the UET Tag Helper browser extension to verify that your goal is working correctly. [Learn more about UET Tag Helper](./hlp_BA_CONC_UET_TagHelper.md).

> [!NOTE]
> When you create a conversion goal, Microsoft Advertising automatically enables auto-tagging of Microsoft Click ID, as this is required for UET conversion goals and improves the accuracy of conversion tracking. When a customer clicks your ad, Microsoft Advertising automatically appends a unique click ID to the landing page URL. (For example, your final URL becomes www.contoso.com/?msclkid=123abc.) UET uses the cookie on your website’s domain to capture the click ID that brought the customer to your website, thereby allowing you to track the conversion. Each ad click is tied to a unique click ID. To disable auto-tagging of Microsoft Click ID, go to **Shared Library**&nbsp;&gt;&nbsp;**Account level options** and uncheck **Add Microsoft Click ID (MSCLKID) to URLs to allow conversion tracking**. Doing so will make it impossible to import offline conversions and hinder accurate conversion tracking data.
> To see the complete list of currencies available for conversion goals, see [Conversion Goal Revenue Currencies](https://go.microsoft.com/fwlink?LinkId=834524).
> Microsoft Advertising matches UET logs with strings defined in destination URL and custom event goals in a case insensitive way. For example, you can create a Destination URL goal type to track visits to your Thankyou.html page as conversions using the condition URL contains tHANKYOU.HTML

 
## Next steps

- [Set up UET if you haven't already](./hlp_BA_CONC_UET_Setup_Master.md)
- [Make sure your conversion goal is working](./hlp_BA_CONC_UET_TroubleshootCT.md)


