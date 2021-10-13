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

The tracking template test button is now available at the account, campaign, ad group, ad, keyword, and sitelink extension level.

## How to test your tracking templates

You can test your tracking templates on the:

- [Account level](#AccountLevel)
- [Ad group level, for either ad group settings or the ad group table](#AdGroupLevel)
- [Ad level](#AdLevel)
- [Campaign level](#CampaignLevel)
- [Keyword level](#KeywordLevel)
- [Sitelink extension level](#SitelinkExtensionLevel)

<anchor id="AccountLevel" />

**Account level**
1. [!INCLUDE [SettingsAccountSettings](./includes/SettingsAccountSettings.md)]
1. Select the **Test** button. Microsoft Advertising will sample 10 URLs from your account and test them.
1. Check the resulting message below the **Test** button for a brief description of the results.
1. Hover over the message to see the full test results.

<anchor id="AdGroupLevel" />

**Ad group level**
You can test tracking templates at the ad group level either in an ad group's settings page or inline in the ad group table.

**Ad group settings page**

1. [!INCLUDE [AdGroupsCampaigns](./includes/AdGroupsCampaigns.md)]
1. Select the name of the ad group whose tracking template you wish to test.
1. From the menu on the left, select **Settings**.
1. Under **Ad Group URL options**, select **Tracking template**.
1. Enter your tracking template URL in the box.
1. Select the **Test** button.
1. Check the resulting message below the **Tracking template** box for a brief description of the results.
1. Hover over the message to see the full test results.

**Ad group table**

1. [!INCLUDE [AdGroupsCampaigns](./includes/AdGroupsCampaigns.md)]
1. Make sure that the **Tracking template** column is visible. If it isn't:
   1. On the top of the table, select **Columns** > **Modify columns**.
   1. Select **Attributes**.
   1. Next to **Tracking template**, select **Add**.
   1. Select **Apply**.

1. Hover over the **Tracking template** column of the appropriate ad group and click the pencil icon.
1. Enter your tracking template URL into the box.
1. Select the **Test** button.
1. Check the resulting message below the **Tracking template** box for a brief description of the results.
1. Hover over the message to see the full test results.

<anchor id="AdLevel" />

**Ad level**
> [!NOTE]
> Ad level testing is only supported for expanded text ads.

1. [!INCLUDE [AdsExtensionsAds](./includes/AdsExtensionsAds.md)]
1. Either:
   1. **New ad** : Select **Create ad**. Select an ad group from the **Ad group** dropdown menu. Select **Ad URL options** to expand the section.
   1. **Existing ad** : Select the checkbox next to an existing ad. Select **Edit** > **Change URL options**.

1. Enter your tracking template URL in the **Tracking template** box.
1. Select the **Test** button.
1. Check the resulting message below the **Tracking template** box for a brief description of the results.
1. Hover over the message to see the full test results.

<anchor id="CampaignLevel" />

**Campaign level**
> [!NOTE]
> Campaign level testing is supported for any ad with a final URL and tracking template, except for dynamic search ads.

1. [!INCLUDE [CampaignsCampaigns](./includes/CampaignsCampaigns.md)]
1. Select a campaign name.
1. From the left menu, select **Settings**.
1. Under **Campaign URL options**, select **Tracking template**.
1. Select the **Test** button. Microsoft Advertising will sample 10 URLs from your campaign and test them.
1. Check the resulting message below the **Tracking template** box for a brief description of the results.
1. Hover over the message to see the full test results.

<anchor id="KeywordLevel" />

**Keyword level**
1. [!INCLUDE [KeywordsKeywords](./includes/KeywordsKeywords.md)]
1. Make sure that the **Tracking template** column is visible. If it isn't:
   1. On the top of the table, select **Columns** > **Modify columns**.
   1. Select **Attributes**.
   1. Next to **Tracking template**, select **Add**.
   1. Select **Apply**.

1. Hover over the **Tracking template** column of the appropriate keyword and click the pencil icon.
1. Enter your tracking template URL in the box.
1. Select the **Test** button.
1. Check the resulting message below the **Tracking template** box for a brief description of the results.
1. Hover over the message to see the full test results.

<anchor id="SitelinkExtensionLevel" />

**Sitelink extension level**
1. [!INCLUDE [AdGroupsCampaigns](./includes/AdGroupsCampaigns.md)]
1. In the table, selet the campaign or ad group you want to add an extension to.
1. From the menu on the left, select **Ads &amp; extensions**.
1. From the top menu, select **Extensions**.
1. If not already selected, select **Sitelink Extensions** from the dropdown menu.
1. Select **Create Ad Extension** > **Add new Sitelink Extension**.
1. In the panel on the right, select **Sitelink Extension URL options** to expand the section.
1. Enter your tracking template URL in the **Tracking template** box.
1. Select the **Test** button.
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
        <li><strong>Landing page found</strong> : You're all set. The testing tool successfully found your landing page.</li>
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
        <li><strong>Tracking call successful</strong> : You're all set. The testing tool was able to successfully call the tracking URL created in the parallel tracking scenario.</li>
        <li><strong>Tracking call unsuccessful</strong> : The testing tool was not able to successfully call the tracking URL created in the parallel tracking scenario. Make sure your tracking template and any custom parameters are correct. </li>
      </ul>
    </td>
  </tr>
</table>


