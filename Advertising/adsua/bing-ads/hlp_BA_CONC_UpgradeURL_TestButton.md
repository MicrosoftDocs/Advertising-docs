---
title: Test your tracking templates
description: Learn how to test your tracking template to make sure it will send customers to the right landing page.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Test your tracking templates

If you use [tracking templates](./hlp_BA_CONC_UpgradeURL_TrackTemplateGlobalParam.md), you can test them to make sure:
- They will send customers to the right landing page.
- They are set up correctly for [parallel tracking](./hlp_BA_CONC_ParallelTracking.md).

The tracking template test button is now available at the account, campaign, ad-group, ad, keyword, and Sitelink-Extension level.

## How to test your tracking templates

## Account level
1. From the main menu on the left, click **All campaigns**, then **Settings**, and then **Account settings**.
1. Click the **Test** button. Microsoft Advertising will sample 10 URLs from your account and test them.
1. Check the resulting message below the **Tracking template** box for a brief description of the results.
1. Hover over the message to see the full test results.

## Campaign level
1. From the main menu on the left, click **All campaigns** and then **Campaigns**.
1. Click a campaign name and then **Settings**.
1. Under **Campaign URL options**, click **Tracking template**.
1. Click the **Test** button. Microsoft Advertising will sample 10 URLs from your campaign and test them.
1. Check the resulting message below the **Tracking template** box for a brief description of the results.
1. Hover over the message to see the full test results.

## Ad-group level
You can test tracking templates at the ad-group level either in an ad group's settings page or inline in the ad group table.
## Ad group settings page
1. From the main menu on the left, click **All campaigns** and then **Ad groups**.
1. Click an ad group name and then **Settings**.
1. Under **Ad group URL options**, click **Tracking template**.
1. Enter your tracking template URL in the box.
1. Click the **Test** button.
1. Check the resulting message below the **Tracking template** box for a brief description of the results.
1. Hover over the message to see the full test results.

## Ad group table
1. From the main menu on the left, click **All campaigns** and then **Ad groups**.
1. Make sure that the **Tracking template** column is visible. If it isn't:
   1. Click **Columns**&nbsp; &gt; &nbsp;**Modify columns**.
   1. Click **Attributes**.
   1. Next to **Tracking template**, click **Add**.
   1. Click **Apply**.

1. Hover over the **Tracking template** column of the appropriate ad group and click the pencil icon.
1. Enter your tracking template URL in the box.
1. Click the **Test** button.
1. Check the resulting message below the **Tracking template** box for a brief description of the results.
1. Hover over the message to see the full test results.

## Ad level
> [!NOTE]
> Ad-level testing is only supported for Expanded Text Ads.

1. From the main menu on the left, click **All campaigns** and then **Ads &amp; extensions**.
1. Either:
   1. **New ad** : Click **Create ad**, select an ad group, and then click **Ad URL options** to expand the section.
   1. **Existing ad** : Select the checkbox next to an ad and click **Edit**&nbsp;&gt;&nbsp;**Change URL options**.

1. Enter your tracking template URL in the **Tracking template** box.
1. Click the **Test** button.
1. Check the resulting message below the **Tracking template** box for a brief description of the results.
1. Hover over the message to see the full test results.

## Keyword level
1. From the main menu on the left, click **All campaigns** and then **Keywords**.
1. Make sure that the **Tracking template** column is visible. If it isn't:
   1. Click **Columns**&nbsp; &gt; &nbsp;**Modify columns**.
   1. Click **Attributes**.
   1. Next to **Tracking template**, click **Add**.
   1. Click **Apply**.

1. Hover over the **Tracking template** column of the appropriate keyword and click the pencil icon.
1. Enter your tracking template URL in the box.
1. Click the **Test** button.
1. Check the resulting message below the **Tracking template** box for a brief description of the results.
1. Hover over the message to see the full test results.

## Sitelink-Extension level
1. From the main menu on the left, click **All campaigns**.
1. From the page menu, click **Campaigns** or **Ad groups**.
1. In the table, click the campaign or ad group you want to add an extension to.
1. From the page menu, click **Ads &amp; extensions**.
1. From the top of the page, click **Extensions**.
1. If not already selected, click **Sitelink Extensions**.
1. Click **Create ad extension** > **Add new Sitelink Extension**.
1. Click **Sitelink Extension URL options** to expand the section.
1. Enter your tracking template URL in the **Tracking template** box.
1. Click the **Test** button.
1. Check the resulting message below the **Tracking template** box for a brief description of the results.
1. Hover over the message to see the full test results.

 
## What the full test results show

|Results message|
|---|
|The message indicates whether a problem was encountered with the landing page or parallel tracking URL and provides the landing page URL that the testing tool returned. See the next section for more information on results messages.|
|Click URL|
|The click URL is passed to your website server or third-party tracking system when the search user clicks the ad. The testing tool constructs the click URL by appending the tracking template parameters and their values to the final URL.|
|Tracking template|
|This is the tracking template that will be applied when the ad is served. We also show what entity level the template is coming from.|
|Final URL|
|This is the URL you entered when you created the ad.|
|Attributes|
|The listed URL and custom parameters and their values will be passed to your third-party tracking system when the ad is served.|

## What the results messages mean

<table type="type1">
  <tr>
    <th scope="col">Landing page results messages</th>
  </tr>
  <tr>
    <td>
      <ul>
        <li><strong>Landing page found</strong> : You're all set: The testing tool successfully found your landing page.</li>
        <li><strong>Page not found</strong> : The testing tool found no results for this URL. Please make sure your tracking template, custom parameter(s), and final URL are correct.</li>
        <li><strong>URL mismatch</strong> : There is a mismatch somewhere in your URL, which is not allowed. Your landing page and final URL must share the same domain, the URLs in your redirect chain must begin with your final URL, and the redirects after your final URL must stay on the same domain. Please review your URL and make sure it meets the requirements listed in the Microsoft Advertising &nbsp;[URLs and landing page policies](https://go.microsoft.com/fwlink?LinkId=785808) page.</li>
        <li><strong>Page unreachable</strong> : We couldn’t reach the landing page. The request may have timed out. Please try again.</li>
        <li><strong>System error</strong> : We encountered an error while testing your landing page. Please try again.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="col">Tracking URL results messages</th>
  </tr>
  <tr>
    <td>
      <ul>
        <li><strong>Tracking call successful</strong> : You're all set: The testing tool was able to successfully call the tracking URL created in the parallel tracking scenario.</li>
        <li><strong>Tracking call unsuccessful</strong> : The testing tool was not able to successfully call the tracking URL created in the parallel tracking scenario. Make sure your tracking template and any custom parameters are correct. </li>
      </ul>
    </td>
  </tr>
</table>


