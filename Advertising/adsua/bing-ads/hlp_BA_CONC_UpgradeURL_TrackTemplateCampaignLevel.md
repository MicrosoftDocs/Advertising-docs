---
title: Add additional tracking templates to my campaigns
description: Upgraded URLs separate your tracking information from the landing page URL making it easy to update and manage URL tracking. Here, find out how to create a tracking template at the campaign, ad group, ad, keyword, and Sitelink Extension level.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Add additional tracking templates to my campaigns

URL tracking allows you to find out how visitors got to your website. To get set up, all you need to do is add URL parameters to the tracking template.  To learn more, see [What is URL tracking in Microsoft Advertising?](./hlp_BA_CONC_UpgradeURL_WhatIsTracking.md)

For search campaigns, you can add tracking templates to:

- Account
- Campaign
- Ad group
- Ad
- Keyword
- Sitelink Extension

**New!**  For Microsoft Shopping Campaigns, you can now add tracking templates at the account, campaign, and ad group level along with the product group level.

We recommend that you add a [tracking template at the account level](./hlp_BA_CONC_UpgradeURL_TrackTemplateGlobalParam.md), but you can also add them at other levels. If you have more than one tracking template, when your ad is served the lowest level tracking template will be appended to your landing page URL.

## Add a tracking template to an existing campaign or ad group
1. From the **Campaigns** page, click either the **Campaigns** or **Ad Groups** tab (or from the main menu on the left, click **All campaigns** and then either **Campaigns** or **Ad groups**).
1. Click the name of the item you want to add a tracking template to and then click **Settings**.
1. Under **Campaign URL options** or **Ad group URL options**, click **Tracking template**.
1. Enter one of these items:
   - {lpurl} followed by URL parameters and custom parameters which are separated by an ampersand (&amp;). For example, {lpurl}?matchtype={matchtype}&amp;device={device}. To learn more, see [What tracking or URL parameters can I use?](./hlp_BA_CONC_UpgradeURL_URLParameters.md) and [Can I use custom parameters?](./hlp_BA_CONC_UpgradeURL_TrackTemplateCustomParam.md)
   - The URL you received from a third-party tracking tool or service. For example, http://www.trackingc.com/?url={lpurl}&amp;id=5

1. Click **Save**.

> [!NOTE]
> The tracking template can be up to 2,048 characters. To learn more, see [Have the URL character limits changed? section in FAQ](./hlp_BA_CONC_UpgradeURL_FAQ.md)
> Make sure that you select final URL as your Landing page URL because tracking templates don't work with destination URLs.

## Add a tracking template to an existing ad or Sitelink Extensions
1. From the **Campaigns** page, click either the **Ads** or **Ad Extensions** tab (or from the main menu on the left, click **All campaigns** and then **Ads &amp; Ad extensions**).
1. Click the **Edit** icon next to the ad or select the Sitelink Extension, click **Edit**, and then **Edit an extension**.
1. Under **Landing page URL**, click **Final URL** and enter the URL of your website.
1. Click **Ad URL options** or **Sitelink Extension URL options**.
1. In **Tracking template**, enter one of these items:
   - {lpurl} followed by URL parameters and custom parameters which are separated by an ampersand (&amp;). For example, {lpurl}?matchtype={matchtype}&amp;device={device}. To learn more, see [What tracking or URL parameters can I use?](./hlp_BA_CONC_UpgradeURL_URLParameters.md) and [Can I use custom parameters?](./hlp_BA_CONC_UpgradeURL_TrackTemplateCustomParam.md)
   - The URL you received from a third-party tracking tool or service. For example, http://www.trackingc.com/?url={lpurl}&amp;id=5

1. Click **Save**.

> [!NOTE]
> The tracking template can be up to 2,048 characters. To learn more, see [Have the URL character limits changed? section in FAQ](./hlp_BA_CONC_UpgradeURL_FAQ.md)
> Make sure that you select final URL as your Landing page URL because tracking templates don't work with destination URLs.

## Add a tracking template to keywords
1. From the **Campaigns** page, click the **Keywords** tab (or from the main menu on the left, click **All campaigns** and then **Keywords**).
1. Select the keywords you want and then click **Edit** and **Change landing page URLs**.
1. Make sure the **Action** is set to Final URL and then enter the URL of your website in the **Final URL** box.
1. Click **Save**.
1. Make sure the keywords are still selected and then click **Edit** and **Change URL options**.
1. In **Tracking template**, enter one of these items:
   - {lpurl} followed by URL parameters and custom parameters which are separated by an ampersand (&amp;). For example, {lpurl}?matchtype={matchtype}&amp;device={device}. To learn more, see [What tracking or URL parameters can I use?](./hlp_BA_CONC_UpgradeURL_URLParameters.md) and [Can I use custom parameters?](./hlp_BA_CONC_UpgradeURL_TrackTemplateCustomParam.md)
   - The URL you received from a third-party tracking tool or service. For example, http://www.trackingc.com/?url={lpurl}&amp;id=5

1. Click **Save**.

> [!NOTE]
> The tracking template can be up to 2,048 characters. To learn more, see [Have the URL character limits changed? section in FAQ](./hlp_BA_CONC_UpgradeURL_FAQ.md)
> Make sure that you select final URL as your Landing page URL because tracking templates don't work with destination URLs.


