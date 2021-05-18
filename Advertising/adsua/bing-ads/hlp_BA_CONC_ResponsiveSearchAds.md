---
title: About responsive search ads
description: Learn how to set up responsive search ads to optimize ad performance
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# About responsive search ads

Responsive search ads make creating ads easier by eliminating the need to figure out which headlines and descriptions work well together. You provide up to 15 headlines and 4 descriptions, and using these, Microsoft Advertising will mix and match the most optimal combinations to create effective ads for potential customers.

Analyzing ad performance to determine which ads perform best is also taken care of with responsive search ads. The best performing ad combinations are automatically identified and reported to you, while the ineffective ads aren’t shown again. Adapting your ad’s content to match what potential customers are searching for can help to improve your campaign’s performance.

## Best practices for responsive search ads

- **Create responsive search ads in existing ad groups.**  For optimal performance, we recommend having 2-3 text ads and 1 responsive text ad in an ad group. Please note that there is a limit of 3 enabled responsive search ads per ad group.
- **Provide as many assets as possible.**  Aim to provide at least 8-10 distinct headlines that don’t contain similar phrases. Use a combination of short and long headlines to maximize space on any device. Create titles that are related to your keywords and use at least 1 brand title. Use a single dynamic keyword insertion.
- **Make content distinct.**  Avoid repetitive lanugage and create distinct descriptions. Include additional product or service benefits and features, a clear call-to-action, and shipping and return information.
- **Avoid pinning headlines or descriptions, if possible.**  Pinning restricts the number of header or descriptions combinations to match a customer's search.
- **Combine**  [auto-bidding](./hlp_BA_CONC_BidStrategy.md) to optimize your target metrics.

## Create a new responsive search ad
1. [!INCLUDE [AdsExtensionsAds](./includes/AdsExtensionsAds.md)]
1. Select **Create ad**, and then select an ad group.
1. For **Ad type**, select **Responsive search ad**.
1. Enter your landing page URL in the **Final URL** box.
1. Enter between 5 and 15 headlines and optionally pin them to specific positions.
1. Enter up to 4 descriptions and optionally pin them to specific positions.
1. Enter the URL that will be shown in your ad in the **Display URL** box.
1. [!INCLUDE [SelectSave](./includes/SelectSave.md)]

> [!NOTE]
> At least one eligible headline must be available for each position. You can't pin all of the headlines to the same position. A headline is only be eligible for its pinned position, or any position if not pinned. Bing AI chooses the best headline per position when ads are shown.
> At least one eligible description must be available for each position. You can't pin all of the descriptions to the same position. A description is only be eligible for its pinned position, or any position if not pinned. Bing AI chooses the best description per position when ads are shown.
> For example, you can have 3 descriptions pinned to **position 1**, as long as you have at least one description that is either not pinned or pinned to **position 2**.

## Update an existing responsive search ad
1. [!INCLUDE [AdsExtensionsAds](./includes/AdsExtensionsAds.md)]
1. Select the ad you want to edit from the table and select **Edit** > **Change ads**.
1. Make your changes and select **Save**.

## Update multiple responsive search ads at the same time
1. [!INCLUDE [AdsExtensionsAds](./includes/AdsExtensionsAds.md)]
1. Select the ad you want to edit from the table and select **Edit** > **Change ads**.
1. In the **Make changes to** drop-down list, choose **Responsive search ads**.
1. To replace text in multiple ads:
   1. In the **Action** list, choose **Find and replace text**, and then select the field in which you would like to replace the text.
   1. In the **Find** box, enter the text you want to replace.
   1. In the **Replace with** box, enter the new text you want to use.
   1. [!INCLUDE [SelectSave](./includes/SelectSave.md)]

1. To add more headlines or descriptions:
   1. In the **Action** list, choose **Add** and select **Headlines** or **Descriptions**.
   1. Enter the new headlines or descriptions text.
   1. [!INCLUDE [SelectSave](./includes/SelectSave.md)]

1. To remove headlines or descriptions:
   1. In the **Action** list, choose **Remove** and select **Headlines** or **Descriptions**.
   1. Select **Contains**, **Equals**, or **Starts with** and enter the text to find the headlines or descriptions you want to remove.
   1. [!INCLUDE [SelectSave](./includes/SelectSave.md)]

1. To change current pin settings:
   1. In the **Action** list, choose **Pin** and select **Headlines** or **Descriptions**.
   1. Select **Contains**, **Equals**, or **Starts with** and enter the text to find the headlines or descriptions you want to re-pin.
   1. In the **Pin to** list, select the position you want to pin the headline or description to.
   1. Make your changes and select **Save**.

## Using reports to track responsive search ads
You can use the following reports to see details about your responsive search ads:

- **Asset report** : Shows which headlines and descriptions are being shown the most.
- **Combination report:** Shows which responsive search ad combinations are being shown the most.

To view the reports:

1. [!INCLUDE [AdsExtensionsAds](./includes/AdsExtensionsAds.md)]
1. Select the ad you want to edit from the table and select **View asset details**.
1. Select **Assets** to view the headlines and descriptions impressions.
1. Select **Combinations** to view the ad combinations.

Keep track of how your assets are performing with the asset performance rating. There are four different ratings for your assets:

|Asset performance rating|Description|
|---|---|
|Low|This asset's performance is low and we recommend you replace this asset to improve your ad performance.|
|Good|This asset is performing well. We recommend you keep this asset and add more assets to improve your ad performance.|
|Best|This asset's performance is among the best and we recommend that you add more similar assets.|
|Unrated|We don't have any performance rating for this asset. This can be due to the asset being inactive, not having enough information to determine its performance, or if there aren't enough similar assets to compare against it.|

## Common questions about responsive search ads

## What's the difference between responsive search ads and expanded text ads?
The format for the two ad types are the same, with up to three headlines and two descriptions. Unlike expanded text ads, you can enter up to 15 headlines and four descriptions for responsive search ads. You can also pin a header or description to a specific position.
## How can I monitor my responsive search ads' performance?
Now that you’ve created responsive search ads, here are some ways you can see how they’re performing.
- **Track ad group metrics** . Ad groups that contain both text ads and responsive search ads generally perform better, with improvements across different variables like click-through rates, conversions, and impressions.
- **Monitor performance data**  before and after creating responsive search ads. We recommend that you check your ad group’s performance data a week before adding responsive search ads, let them run for at least one week or more, and then check how your ad group is performing. Keep in mind that each ad should have a minimum of 1,000 impressions to be able to properly evaluate the ad’s performance.
- **Evaluate asset performance.**  You can view impressions by asset and combination by selecting View asset details under each responsive search ad in the table. Pay attention to the impression data and focus on updating assets with the lowest impressions to improve performance.

## With the third ad title and second description, is it guaranteed that all will serve at the same time?
The system is constantly evaluating best ways to show the text ad based on screen size and other constraints.
## Will responsive search ads work with all existing ad extensions?
Yes, all existing ad extensions will continue to display on responsive search ads.
## What does pinning a headline or description to a specific position do?
Headlines and descriptions can appear in any order, unless you pin a header or description to a specific position, when headlines or descriptions are shown. We recommend that you pin positions 1 and 2 for headlines and position 1 for descriptions.

Keep in mind that pinning restricts the number of header or descriptions combinations to match a customer's search.

To maximize impressions across all ad formats, the descriptions might not always be shown in your ad.

## What is ad strength?
Ad strength indicates the diversity, quality, and quantity of the assets that make up a responsive search ad, ranging from "poor" to "excellent". This gets populated dynamically as you type your asset candidates and provides corresponding recommendations on how to better create your ad.
## How do I view and apply responsive search ad recommendations?
Recommendations are AI-driven suggestions provided by Microsoft Advertising. These customized recommendations are based on headlines and descriptions from your own active ads in the same ad group, as well as your account’s historical performance, campaign settings, and trends. Leverage these custom recommendations to add responsive search ads to your ad groups, which can help improve your campaign performance.
1. From the **Campaigns** page, select the **Recommendations** tab (or from the main menu on the left, select **All campaigns** and then **Recommendations**).
1. Under **All recommendations**, find the responsive search ad recommendation tile and select **View recommendation**.
1. Review the recommended responsive search ad and select **Apply**. 					 					You can also make edits to the recommended ad, which go through a review. During the review, which typically takes less than three hours (but could take up to one business day), your ad might not run.


