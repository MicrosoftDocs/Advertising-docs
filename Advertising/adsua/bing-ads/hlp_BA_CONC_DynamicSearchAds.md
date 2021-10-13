---
title: About dynamic search ads
description: Learn how Microsoft Advertising can generate keywords and ads for you automatically.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# About dynamic search ads

Dynamic search ads provide a streamlined, low-touch way to make sure customers searching on the Microsoft Search Network find your products or services.

> [!NOTE]
> This feature is currently available in Australia, Austria, Belgium, Canada, Denmark, Finland, France, Germany, Ireland, Italy, Netherlands, New Zealand, Norway, Spain, Sweden, Switzerland, United Kingdom, and United States.

## Benefits of using dynamic search ads

Dynamic search ads automatically target relevant search queries based on the content of your website, and are dynamically created to respond to these search queries. Using them will:

- **Create targeted and relevant ads automatically** : New, dynamically-created ads for every search query based on your website content, or specific pages or categories of your website.
- **Save time and reduce your workload** : No need to maintain keyword lists, manage bids, or update and customize ad titles.
- **Find missed opportunities** : Automatically adapt to new queries to drive additional conversions.

Dynamic search ads are most appropriate for two types of advertisers:
- Advertisers who have a large catalog of webpages and a changing mix of products, making it difficult to manage search ads for each product.
- Advertisers who are not familiar with search advertising, but who want to quickly and easily try it out.

## How to set up dynamic search ads

To enable dynamic search ads within an existing search campaign, navigate to the campaign’s **Settings** page. Locate the **Dynamic search ads** option, select **Enable dynamic search ads**, then select **Save**. You can now add **Dynamic** ad groups to your campaigns, which contain dynamic search ads and dynamic ad targets.

You can follow the steps below to enable dynamic search ads within a new search campaign.

1. From the main menu on the left, select **Search campaigns** > **Campaigns** > **Create campaign**.
1. Choose the campaign goal, for example, **Visits to my website**, and then select **Search ads**.
1. Select **Next**.
1. While choosing campaign settings be sure to select **Enable dynamic search ads**.
1. You will have the option to enable dynamic search ad text by selecting the **Enable dynamic search ad text** checkbox. Please note that if you choose to enable this feature, we will automatically generate ad text in addition to the ad text you provide. During ad delivery, we will use artificial intelligence to choose the best ad text available from these options. See **What you need to know about ad content**  below for more information about dynamic search ad text.                     [!INCLUDE [ComingSoon](./includes/ComingSoon.md)]
1. Create a **Dynamic** ad group with dynamic ad targets and then select **Save &amp; go to the next step**. You can optionally create **Standard** ad groups which contain other ad types and keywords.
1. Create a Dynamic search ad and then select **Save &amp; go to the next step**.
1. Choose your campaign budget and other settings and then select **Save**.

> [!IMPORTANT]
> Once you create your search campaign with dynamic search ads, it can take up to one week before your ads start to serve.

## What you need to know about dynamic ad targets

- **Target recommended categories** : Microsoft Advertising will analyze your website and then categorize its content. You can then select which categories you want to target and we will automatically generate keywords and ads from them. This is a good idea if you want to keep the dynamic search ads focused on a particular theme or you want to set different bids for different parts of your website.
- **Target all webpages** : Microsoft Advertising will look at content from all pages of your website in order to generate keywords and ads.
- **Target specific webpages** : You choose specific pages of your website to target based on their URL, category, page title, or page content. This is a good idea if you want to set different bids for different parts of your website or to make sure you’re not targeting parts of your website that are not relevant to your campaign goal.
- A "page title" is the text that appears at the top of a webpage—in your website's code, it's the text in this area:
```
<head>                     <title>This is the page title</title>                   </head>
```

- "Page content" is the visible text on a webpage—in your website's code, it's the text between these tags:
```
<body></body>
```

> [!IMPORTANT]
> Once an auto target has been created, its conditions cannot be changed.

## What you need to know about ad content

- When you create your ad, you do not need to write your ad title. Microsoft Advertising will dynamically generate this for you based on the appropriate keyword and your website content. Optionally, you can supply an ad title using [page feeds](./hlp_BA_CONC_DynamicSearchAds_PageFeeds.md).
- You will need to write your ad description under **Ad text** and, optionally, **Ad text 2**. Ad text includes a description of your products and services as well as a call to action. You can have two ad descriptions that support up to 90 characters each. If you have enabled dynamic search ad text, keep in mind that we will also create ad text for your dynamic search ad, and we’ll determine the best available description during ad delivery.
- You have the option to include one or two paths to appear after your website's domain. The path is distinct from the final URL. The final URL is the actual webpage URL that customers are taken to after they click your ad. The path can be a shorter or "friendlier" version of your URL showing one or two subdirectories. For example, if you sell men’s clothes, and you’re advertising shirts that are on sale for spring, your final URL might be http://www.contoso.com/content/en/clothesaccessories/spr2017/shirts, but your path could simply be contoso.com/SpringSale/Shirts.

## Tips for effective dynamic search ads

<table type="type1">
  <tr>
    <th scope="col">Setup</th>
  </tr>
  <tr>
    <td>
      <ul>
        <li>
              Set bids close to your non-exact match bids for similar keyword categories.
            </li>
        <li>
              Create different ad groups for different dynamic ad targets.
            </li>
        <li>
              Create a <strong>Target all webpages</strong> ad group in addition to narrower targets to capture as many relevant searches as possible.
            </li>
        <li>
              Ensure that the tag NoIndex is not present in the domain or in any URL that the auto targets are referencing.
            </li>
        <li>
              Ensure that the campaign, ad group, and ad are all set in the same language. Also, the language set for the campaign, ad group, and ad should match the language of the domain.
            </li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="col">Auto targets</th>
  </tr>
  <tr>
    <td>
      <ul>
        <li>
              Exclude parts of your site that don’t drive conversions.
            </li>
        <li>
              Have a variety of auto targets—using <strong>Target categories of webpages</strong> is a good way to find appropriate ones.
            </li>
        <li>
              Use more generic ad descriptions and URL paths for ads in ad groups using <strong>All webpages</strong> auto targets.
            </li>
        <li>
              Create auto targets from your main domain URL. Do not set up auto targets using URLs that redirect to other pages.
            </li>
        <li>
              The domain address you specify during campaign creation should be the same domain address you used to create auto targets for that campaign. Subdomains are not allowed.
            </li>
        <li>
              We recommend <strong>not</strong> including "http://www" or "https://www" in auto targets.
            </li>
        <li>
              With <strong>Target specific webpages</strong>, if you use the "and" condition (for example, page title contains "food" and URL contains "delivery"), make sure that you have webpages that meet all the specified conditions on your website.
            </li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="col">Optimization</th>
  </tr>
  <tr>
    <td>
      <ul>
        <li>
              Add paused keywords and current negative keywords in your other campaigns as negative keywords in your dynamic search ads ad groups.
            </li>
        <li>
              Try using the Enhanced CPC [bid strategy](./hlp_BA_CONC_BidStrategy.md).
            </li>
        <li>
              Use [ad extensions](./hlp_BA_CONC_AboutAdExtensions.md) to make your ads more eye-catching.
            </li>
        <li>
              Use [remarketing lists](./hlp_BA_CONC_Audiences_CreateAudience.md) to target people who have visited your website before.
            </li>
        <li>
              Add [exclusions](./hlp_BA_PROC_AddExclusions.md) to prevent your ads from appearing in specific locations, on specific web sites within the search network, or prevent your ads from displaying to certain IP addresses.
            </li>
        <li>
              Dynamic search ads could lead to higher traffic, so keep an eye on your budget and don't let it run out.
            </li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="col">Reports</th>
  </tr>
  <tr>
    <td>
      <ul>
        <li>
              To understand  how your auto targets are performing and where bid adjustments may be useful, run a <strong>Dynamic search ad auto target</strong> report.
            </li>
        <li>
              To check the performance of your existing category or to find new categories worth targeting, run a <strong>Dynamic search ad category</strong> report.
            </li>
        <li>
              To see how your ads perform against search terms, run a <strong>Dynamic search ad search term</strong> report. The data can help you find negative keywords that create conversions.
            </li>
      </ul>
    </td>
  </tr>
</table>

 
## Common questions about dynamic search ads

## How do you determine what content is on my website? And what if you're not finding certain parts of my website?
Your website's content is analyzed by Bing's web-crawling technology. We crawl any webpage that is in Bing's index. If you suspect that some parts of your website are not being found by our web crawler, take a look at [              this Bing Webmaster article            ](https://go.microsoft.com/fwlink?LinkId=859262) for information on why this might be the case and what you can do to fix it.

## Will dynamic search ads work with existing ad extensions and Automated Extensions?
Yes, dynamic search ads will work with all existing [ad extensions](./hlp_BA_CONC_AboutAdExtensions.md) and [Automated Extensions](./hlp_BA_CONC_AutomatedExtensions.md), just like standard text ads.

## Will remarketing lists work with dynamic search ads?
Yes, remarketing lists can be associated to ad groups containing dynamic search ads. [Learn more about remarketing lists](./hlp_BA_CONC_Audiences_CreateAudience.md)

## Can I add tracking templates and custom parameters to dynamic search ads?
Yes, tracking templates and custom parameters are supported at the campaign, ad group, ad, and auto target levels.  [Learn more about tracking templates](./hlp_BA_CONC_UpgradeURL_TrackTemplateGlobalParam.md)

## Can I use auto-tagging with dynamic search ads?
Yes, auto-tagging is supported for dynamic search ads. [Learn more about auto-tagging](./hlp_BA_CONC_AutoTag.md)


