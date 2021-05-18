---
title: Target searches automatically with dynamic search ads
description: Learn how Microsoft Advertising can generate keywords and ads for you automatically.
ms.service: "Bing-Ads-Editor-v11"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Target searches automatically with dynamic search ads

Dynamic search ads provide a streamlined, low-touch way to make sure customers searching on the Microsoft Search Network to find your products or services.

> [!NOTE]
> Dynamic search ads are available in Australia, Austria, Belgium, Canada, Denmark, Finland, France, Germany, Ireland, Italy, Netherlands, New Zealand, Norway, Spain, Sweden, Switzerland, United Kingdom, and United States.
> 
> [!IMPORTANT]
> With the recent introduction of ad group type, search campaigns support both standard and dynamic ad groups. You can add dynamic search ads within any existing or new search campaign. During early Q2 calendar year 2021, you can no longer create new dynamic search campaigns (as a campaign type.) Existing dynamic search campaigns will be migrated to search campaigns with dynamic ad groups.

## Benefits of using dynamic search ads

Dynamic search ads automatically target relevant search queries based on the content of your website, and are dynamically created to respond to these search queries. Using them will:

- **Create targeted and relevant ads automatically** : New, dynamically-created ads for every search query based on your website content, or specific pages or categories of your website.
- **Reduce your workload** : No need to maintain keyword lists, manage bids, or update and customize ad titles.
- **Find missed opportunities** : Automatically adapt to new queries to drive additional conversions.

Dynamic search ads are most appropriate for two types of advertisers:
- Advertisers who have a large catalog of webpages and a constantly changing mix of products, making it difficult to manage search ads for each product.
- Advertisers who are not familiar with search advertising, but who want to quickly and easily try it out.

## How to add a dynamic ad group in a Search campaign
1. In the data view, select **Add campaign**.
1. In the Editor pane, for **Campaign type**, select **Search**.
1. Enter the campaign name and budget.
1. Select the **Dynamic search ads** tab.
1. Enter your **Website** and **Website Language**.
1. In the **Manage** menu, select your new Search campaign.
1. In the data view, select the **Add ad group** button.
1. In the **Editor** pane, for **Ad group type**, select **Dynamic**.

## How to add dynamic search targets
You can use Dynamic search targets to target your ads. Here’s how to set dynamic search targets:

1. Under **Keywords and targeting** from the left panel, select **Dynamic ad targets**.
1. Click **Add dynamic ad target** in the data view.
1. Select the **Ad group** to add target.
1. In the **Edit the selected dynamic ad targets** tab, enter the **Values**. Values are the criteria based on which ads are targeted, with four types of values you can enter:
   - **Categories** : Targets based on categories you can enter. Microsoft Advertising will analyze your website and then categorize its content.
   - **Page content contains** : Target based on content of the page. Page content is the visible text on a webpage. In your website’s code, it’s the text between these tags:
```
<body></body>
```

   - **Page title contains** : Target based on page title. Page title is the text that appears at the top of a webpage. In your website’s code, it’s the text in this area:
```
<head>             <title>This is the page title</title>           </head>
```

   - **URL contains** : Target based on what is on the URL.

Note: If nothing is entered for all three values, all webpages will be targeted.

1. Select the **Status** and enter the **Bid** amount.
1. Click the **URL options** tab to enter the **Tracking template** and **Customer parameters** details.

## How to add negative dynamic ad targets
You can use negative dynamic ad targets to prevent your ads from being displayed based on criteria you want. Here’s how to set negative dynamic ad targets:

1. Under **Keywords and targeting** from the left panel, select **Negative dynamic ad targets**.
1. Click **Add negative dynamic ad target** in the data view.
1. Select **Campaign negative dynamic ad target** or **Ad group negative dynamic ad target**.
1. In the **Edit the selected negative dynamic ad targets** pane, enter the **Values**. There are four types of values you can enter:
   - **Categories** : Targets based on categories you can enter. Microsoft Advertising will analyze your website and then categorize its content.
   - **Page content contains** : Target based on content of the page. Page content is the visible text on a webpage. In your website’s code, it’s the text between these tags:
```
<body></body>
```

   - **Page title contains** : Target based on page title. Page title is the text that appears at the top of a webpage. In your website’s code, it’s the text in this area:
```
<head>             <title>This is the page title</title>           </head>
```

   - **URL contains** : Target based on what is on the URL.

Note: The negative dynamic ad target needs to have at least one condition set.

## How to add dynamic search ads
1. Select the campaign from the tree view in the left panel you want to set up dynamic search ads in.
1. Select **Dynamic search ads** under **Ads and extensions** from the type list in the left panel.
1. Click **Add dynamic search ad** in the data view.
1. In the **Edit the selected Dynamic Search Ads** pane, enter the **Ad text**, **Path**, and set the **Status**.
1. Click the **URL options** tab to enter the **Tracking template** and **Custom parameters** details.

**Notes** :
- You do not write your ad title. Microsoft Advertising will dynamically generate this for you based on the appropriate keyword and your website content.
- You have the option to have one or two paths appear after your website's domain. The path is distinct from the final URL. The final URL is the actual webpage URL that customers are taken to after they click your ad. The path can be a shorter or "friendlier" version of your URL showing one or two subdirectories. If you sell men’s clothes, and you’re advertising shirts that are on sale for spring, your final URL might be http://www.contoso.com/content/en/clothesaccessories/spr2017/shirts, but your path could simply be contoso.com/SpringSale/Shirts.


