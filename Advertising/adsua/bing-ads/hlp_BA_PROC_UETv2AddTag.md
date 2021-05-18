---
title: How do I add a UET tag to my website?
description: Once you've created a UET tag, you'll need to add it to your website. Learn how to do this in JavaScript, using a tag manager, or for single-page application (SPA) websites.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How do I add a UET tag to my website?

> [!IMPORTANT]
> You need to be able to edit your website's code in order to add your UET tag tracking code. If you're not sure how to edit your website's code, contact your webmaster.

After you [create a UET tag](./hlp_BA_PROC_UETv2CreateTag.md), the next step is to add the UET tag tracking code to your website. We recommend that you, or your webmaster, add it to every page of your website in the head or body section. Or, if your site has a master page, you can add it there just once and it will be included on every page of your site.

You have a few options when working with UET tags. You can either add the UET tag tracking code directly into your website's code using JavaScript or use a third-party tag manager. Additionally, if your website was built on a website platform (such as Shopify or WordPress), you can use that system to add your UET tag.

> [!NOTE]
> You can add the UET tag tracking code anywhere in your webpage's head section (before the closing head tag: "&lt;/head&gt;") or body section (before the closing body tag: "&lt;/body&gt;").

## Add the UET tag tracking code to your website directly
1. In the left navigation pane, click **Conversion Tracking** and then **UET tags** (or from the global menu at the top of the page, click **Tools** and then **UET tags**).
1. In the table, find the UET tag that you want to use and, in the **Action** column, click **View tag**.
1. In the **UET tag tracking code** box, click **Copy** and then **Done**.  
1. Paste the UET tag tracking code on every page of your website or on the master page, either in the head or body section.            In the image, the UET tag tracking code is pasted at the top of the body section of the webpage.              ![UET tag](../images/BA_ScreenCap_ConvTrack_AddTag.png)

## Add the UET tag tracking code using a tag manager
Tag managers replace static tags with dynamic tags that are easier to implement and update. The dynamic tag is a container, a small snippet of code that allows you to dynamically insert tags into your website. You can think of the container tag as a bucket that holds other types of tags.

UET works with all major tag management systems. Here is the current list of (and links to instructions for) tested and supported tag managers:

- [Google Tag Manager](./hlp_BA_PROC_UET_TMS_GTM.md)
- [Qubit Opentag](./hlp_BA_PROC_UET_TMS_Qubit.md)
- [Tealium](./hlp_BA_PROC_UET_TMS_Tealium.md)
- [Ensighten](./hlp_BA_PROC_UET_TMS_Ensighten.md)
- [Signal](./hlp_BA_PROC_UET_TMS_Signal.md)
- [Adobe Dynamic Tag Manager](./hlp_BA_PROC_UET_TMS_AdobeDTM.md)
- [Adobe Launch](./hlp_BA_PROC_UET_TMS_AdobeLaunch.md)

## Add the UET tag tracking code using your website platform
UET is designed to work with all major website platforms. Here is the current list of (and links to instructions for) tested and supported platforms that allow you to install UET tags:

- [BigCommerce](./hlp_BA_PROC_UET_WebPlatform_BigCommerce.md)
- [Shopify](./hlp_BA_PROC_UET_WebPlatform_Shopify.md)
- [WordPress.com](./hlp_BA_PROC_UET_WebPlatform_WordPress.md)
- [Wix](./hlp_BA_PROC_UET_WebPlatform_Wix.md)

> [!NOTE]
> To see an example of a JavaScript UET tag tracking code installed in the body of a webpage, visit [this webpage](https://go.microsoft.com/fwlink?LinkId=2010182) (English-only), right-click in the webpage, and then click **View source** or **View page source** depending on your browser.
> As your webpage loads, it triggers the UET tag, resulting in a number of HTTP requests. The most important request is to "bat.bing" (the one that looks like "http://bat.bing.com/action/0?ti=..."). This request tells Microsoft Advertising  about the user visits to your webpage. You can use third-party tools such as Fiddler to monitor all the requests that your browser is making when your webpage loads.

## Using UET tags with single-page application (SPA) websites

Although common, single-page application (SPA) websites are challenging to track. With SPAs, content is dynamically loaded without a typical navigation event occurring. In a sense, the page is only loaded once. However, from an analytics and goal-tracking standpoint, it is necessary to treat each separate navigation as a new page load.

## Learn what you need to do to enable UET tags in SPAs
SPA websites are required to use the JavaScript UET tag tracking code. SPA events are triggered using the same syntax as with [custom events](./hlp_BA_CONC_UETv2CustomEvent.md), with the action 'page_view' and at a required 'page_path' parameter ('page_title' is optional). The parameter 'page_path' must start with a '/'. Example:
```
window.uetq = window.uetq || [];  window.uetq.push('event', 'page_view', { 'page_path': '/spa_page' });
```

> [!NOTE]
> If you’re sending page_view events, you need to make sure you don't have any custom event conversion goals or remarketing lists that have their "event action" parameter set to "page_view".

Here are three different ways of triggering SPA events. Note that we recommend using the first way. For each option, we have a sample webpage that you can visit to see the appropriate code in action.
- **Content change** : Trigger an SPA event any time your application loads dynamic content. In this case, the real URL is automatically sent in a standard pageLoad event on the first load. You can use this URL in your destination goals, and any custom events triggered on that first page will be associated with it. Each SPA event will generate a pageLoad event with the SPA URL, which is not required to be a loadable path. You can reference these URLs in your goals as well. Any custom events triggered after an SPA event will only be associated with the SPA pageLoad (in other words, not the original URL).
   - Visit our [sample "Content change" webpage](https://go.microsoft.com/fwlink?LinkId=2010184) to see this code in action.

- **All pages** : Trigger an SPA event on all pages, including the initial load. This scenario is the same as the preceding one, except the auto pageLoad event is not used. Because it still triggers, it is important to order your events so that the SPA event triggers before any other custom events. If they trigger out of order, some or all may be associated with the auto pageLoad event (and original URL), instead of the SPA pageLoad event (and SPA URL including page_path).
   - Visit our [sample "All pages" webpage](https://go.microsoft.com/fwlink?LinkId=2010188) to see this code in action.

- **All pages, auto-disabled** : Trigger an SPA event on all pages and additionally disable the auto page load. This is accomplished by adding 'disableAutoPageView: true' to the initialization parameters (Note: Do not modify the snippet code directly to disable). This is the same as the previous scenario but removes the requirement that the SPA event must be triggered first on the initial page load. However, subsequent SPA events are still required to be triggered before any custom events that are associated with them (or they will be attributed to the previous SPA event).
   - Visit our [sample "All pages, auto-disabled" webpage](https://go.microsoft.com/fwlink?LinkId=2010192) to see this code in action.


