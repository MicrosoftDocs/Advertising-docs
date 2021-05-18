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

1. In the left navigation pane, click **Conversion Tracking** and then **Conversion goals** (or from the global menu at the top of the page, click **Tools** and then **Conversion goals**).
1. Click **Create conversion goal**.
1. Enter a name for your goal in the **Goal name** box. When naming your goal, use a descriptive name that makes sense to you. (For example, "Checkout page".) Please note that after you choose a name for your conversion goal, the same name may not be used again in the future.
1. Choose the type of conversion you want to track: **Destination URL**, **Duration**, **Pages viewed per visit**, **Event**, **Mobile app install**, or **Offline conversions**.
1. Fill in the appropriate values for the goal type you choose.
<table>
  <tr>
    <th scope="col">Destination URL</th>
  </tr>
  <tr>
    <td>
      <para> Input string and the condition to use when matching the webpage URL with the string.</para>
      <para>
            <strong>Equals To</strong>: In this case the input string must exactly match with the URL on which the UET event fired. However, http(s) and www are ignored (rest of the string must match). For example, if you provide an input string of contoso.com, and the URL is  http://www.contoso.com or  https://www.contoso.com, Microsoft Advertising will consider it as a match and vice versa will also be true.
          </para>
      <para>
            <strong>Begins With</strong>: This matches identical characters starting from the beginning of the string up to and including the last character in the input string. However, http(s) and www are ignored (rest of the string must match). Use this option when your page URLs are generally unvarying but when they include additional parameters at the end that you want to exclude. For example, if you provide an input string of contoso, and the URL is http://www.contoso.com or https://www.contoso.com, Microsoft Advertising will consider it as a match and vice versa will also be true.
          </para>
      <para>
            <strong>Contains</strong>: When this operator is used, Microsoft Advertising verifies if the input string is present anywhere in the URL reported by the UET tag.
          </para>
      <para>
            <strong>Regular Expression</strong>: A regular expression uses special characters to enable wildcard and flexible matching. This is useful when the stem, trailing parameters, or both, can vary in the URLs for the same webpage. However, this option works best when you know how to construct regular expressions that match your URLs. [This advanced topic](./hlp_BA_PROC_UETv2RegExpression.md) provides some examples of how to use regular expressions when building destination URL type goals.
          </para>
    </td>
  </tr>
  <tr>
    <th scope="col">Duration</th>
  </tr>
  <tr>
    <td>The minimum duration of time they expect a user to spend on their website in order to count a conversion by providing a value (range - 1 second to 23 hours, 59 minutes and 59 seconds).</td>
  </tr>
  <tr>
    <th scope="col">Pages viewed per visit</th>
  </tr>
  <tr>
    <td>The minimum number of pages that users must visit at a minimum in a single session for to count a conversion. Can be any number from 0 to 9999999.</td>
  </tr>
  <tr>
    <th scope="col">Events</th>
  </tr>
  <tr>
    <td>
      <para>
            Microsoft Advertising allows you to report custom events (such as downloading white papers, subscribing to newsletters etc) from UET and then choose a subset of those custom events to count as conversions. To learn more, see [How to track custom events with UET](./hlp_BA_CONC_UETv2CustomEvent.md) In short, Microsoft Advertising requires that you report values for one or more of the following custom parameters when custom events happen and create custom event type goals specifying which values for these custom parameters would qualify the custom event as a conversion:
          </para>
      <para>
            <strong>Event category:</strong>  The category of event you want to track. For example, 'video
          </para>
      <para>
            <strong>Event action:</strong>  The type of user interaction you want to track. For example, 'play' or 'pause' etc
          </para>
      <para>
            <strong>Event label:</strong>  The name of the element that caused the action. For example, 'trailer' or  'behindthescenes' etc
          </para>
      <para>
            <strong>Event value:</strong>  A numerical value associated with that event. Could be length of the video played etc.
          </para>
    </td>
  </tr>
  <tr>
    <th scope="col">Mobile app installs</th>
  </tr>
  <tr>
    <td>
          Select the <strong>App platform</strong> and enter the <strong>App ID/Package name</strong>.
          <ul><li>
              Windows Store
              <para>
                Where to find app ID/package name:
                http://apps.microsoft.com/windows/en-us/app/example-app-name/<strong>12345678-9abc-1234-1234-1234567890ab</strong>
              </para></li><li>
              Windows Phone Store
              <para>
                Where to find app ID/package name:
                http://www.windowsphone.com/en-us/store/app/example-app-name/<strong>12345678-9abc-1234-1234-1234567890ab)</strong>
              </para></li><li>
              Google Play
              <para>
                Where to find app ID/package name:
                http://play.google.com/store/apps/details?id=<strong>com.example.appname</strong>
              </para></li><li>
              Apple App Store
              <para>
                Where to find app ID/package name:
                http://itunes.apple.com/us/app/example-app-name/<strong>id#########</strong>
              </para></li></ul></td>
  </tr>
  <tr>
    <th scope="col">Offline conversions</th>
  </tr>
  <tr>
    <td>This conversion goal type requires no custom values.</td>
  </tr>
</table>

1. If prompted, click **Next** and then, under **Scope**, select if you want this goal to apply to all accounts or a specific account.
1. If you want to add a monetary value for each conversion, under **Revenue value**, select one of the following:
**Each conversion action has the same value** checkbox, and then enter the amount and select the currency (if available). This is a static revenue value that doesn't change.

**The value of this conversion action may vary (for instance, by purchase price)** checkbox, and then enter the default amount and select the default currency (if available) to be used when no value is received for a conversion. The revenue value will change based on the customization you make to the UET tag tracking code that you add to your website. To learn more, see [How to report variable revenue with UET](./hlp_BA_CONC_UETv2RevenueVariables.md). This option is only available for destination URL and event conversion goals.

1. You can also assign a **Count** to the conversion and enter a **Conversion window** to track up to 90 days in the past.
1. Set a **View-through conversion window** to track conversions that occur in this period of time after a customer views (but doesn't click) your ad. [Learn more about view-through conversions](./hlp_BA_CONC_ViewThroughConv.md).
1. Optional: Uncheck the **Include in "Conversions"** checkbox if you **don't** want actions that meet the criteria of this conversion goal to appear in the "Conversions" column in the data table and affect any automated bidding bid strategies you have enabled. If you uncheck **Include in "Conversions"** for a conversion goal, you can still track it using the "All conversions" columns of your conversion goal data table and your reports. [Learn more about "Conversions" versus "All conversions"](./hlp_BA_CONC_ConvsVsAllConvs.md).
1. Select the UET tag that you want to associate with this conversion goal (not applicable to offline conversions).
1. Click **Save**.
1. (Optional) In the resulting **Conversion goal created!** message, click **test the goal now** to use the UET Tag Helper browser extension to verify that your goal is working correctly. [Learn more about UET Tag Helper](./hlp_BA_CONC_UET_TagHelper.md).

> [!NOTE]
> When you create a conversion goal, Microsoft Advertising automatically enables auto-tagging of Microsoft Click ID, as this is required for UET conversion goals and improves the accuracy of conversion tracking. When a customer clicks your ad, Microsoft Advertising automatically appends a unique click ID to the landing page URL. (For example, your final URL becomes www.contoso.com/?msclkid=123abc.) UET uses the cookie on your website’s domain to capture the click ID that brought the customer to your website, thereby allowing you to track the conversion. Each ad click is tied to a unique click ID. To disable auto-tagging of Microsoft Click ID, go to **Shared Library**&nbsp;&gt;&nbsp;**Account level options** and uncheck **Add Microsoft Click ID (MSCLKID) to URLs to allow conversion tracking**. Doing so will make it impossible to import offline conversions and hinder accurate conversion tracking data.
> To see the complete list of currencies available for conversion goals, see [Conversion Goal Revenue Currencies](https://go.microsoft.com/fwlink?LinkId=834524).
> Microsoft Advertising matches UET logs with strings defined in destination URL and custom event goals in a case insensitive way. For example, you can create a Destination URL goal type to track visits to your Thankyou.html page as conversions using the condition URL contains tHANKYOU.HTML

 
## Next steps

- [Set up UET if you haven't already](./hlp_BA_CONC_UET_Setup_Master.md)
- [Make sure your conversion goal is working](./hlp_BA_CONC_UET_TroubleshootCT.md)


