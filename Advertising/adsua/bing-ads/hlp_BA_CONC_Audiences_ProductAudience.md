---
title: Dynamic remarketing lists: Remarketing for products
description: Learn about creating dynamic remarketing lists to remarket to customers who have interacted with a specific product.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Dynamic remarketing lists: Remarketing for products

> [!IMPORTANT]
> Dynamic remarketing lists were formerly known as product audiences.

Dynamic remarketing lists pair customers with specific products based on what they have looked at, considered, or already purchased on your website. You can use dynamic remarketing lists in both search campaigns and audience campaigns (not everyone has audience campaigns yet).

## Why use dynamic remarketing lists?

**Targeted audience reach** . Show tailored ads for specific products to people who have already shown purchase intent signals for those very products.

**Boosted performance** . Dynamic remarketing lists can increase the likelihood of clicks and conversions, and can provide a better return on ad spend than standard remarketing lists.

**Easy to use** . You can create five types of dynamic remarketing lists — general visitors, product searchers, product viewers, shopping cart abandoners, and past buyers — so you don't need to create a remarketing list for each individual product.

## Testing Audiences

Before you start setting up dynamic remarketing, make sure you have:

- **A Microsoft Merchant Center catalog feed** . [What is Microsoft Merchant Center?](./hlp_BA_CONC_AboutBingMerchantCenter.md)
- **A JavaScript UET tag** : [Create a Microsoft Advertising UET tag](./hlp_BA_PROC_UETv2CreateTag.md) and [add the UET tag tracking code to every page of your website](./hlp_BA_PROC_UETv2AddTag.md). You will need to add two new parameters to the UET tag: Page Type and Product ID (this product ID must match the ID in your Microsoft Merchant Center catalog feed). See the below "How do I modify my UET tag for dynamic remarketing?" section for more information.
   - JavaScript is required to ensure you have access to the full functionalities of conversion tracking and remarketing.  If you are using a non-JavaScript tag, please switch over to a JavaScript tag.

- **The ability to edit website code** : Either you or your webmaster will need to edit your website code.

## Using dynamic remarketing

## How do I create a dynamic remarketing list?
1. [!INCLUDE [Audiences](./includes/Audiences.md)]
1. Select **Create audience**.
1. Give this audience a unique name.
1. For **Type**, elect **Dynamic remarketing list**.
1. Select **Next**.
1. Select the UET tag you want to use.
1. For **Whom to add to your audience**, select which type of dynamic remarketing list you want to target and set the time frame for eligible customers.
|Dynamic remarketing lists|When to use this list|
|---|---|
|General visitors|**Reach a broader base of your potential customers.**  These people have visited your website, showing interest in your brand or offerings.|
|Product searchers|**Reach users who've shown intent.**  These people have visited your website **and** searched for products on your site, showing even more interest in your offerings.|
|Product viewers|**Reach users who've shown clear intent.**  These people have visited your website and **viewed** your products, showing a clear interest in your offerings.|
|Shopping cart abandoners|**Reach users who've shown very strong intent.**  These people added items to their cart, and, while they didn't make a purchase, this shows a very strong interest in your offerings.|
|Past buyers|**Reach users who've purchased from you in the past.**  These people could purchase again, be it the same product or a related product (via a cross-sell or upsell).|

1. Copy the code you see on the page, modify it with the appropriate product ID and page type **(see "How do I modify my UET tag for dynamic remarketing?" below for more information on this step)**, and then paste it into your UET tag on your website.
1. For **Tag name**, select the UET tag you want to use with this dynamic remarketing list.
1. Select **Save**.

> [!IMPORTANT]
> A dynamic remarketing list takes up to 24 hours to build, and targeting for it won't take effect until that point.

## How do I modify my UET tag for dynamic remarketing?
You need to add custom parameters to your JavaScript UET tag tracking code for dynamic remarketing. If you haven't already added the UET tag tracking code to your website, take a look at [How do I add a UET tag to my website?](./hlp_BA_PROC_UETv2AddTag.md)

Add the following JavaScript to the end of the UET tag tracking code in each page of your website:

```
```<script>```  ```   window.uetq = window.uetq || [];      window.uetq.push ('event', '', {'ecomm_prodid': '
<c_data><![CDATA[<font color="ff0027" size="2">Replace_with_Product_ID</font>]]></c_data>
', 'ecomm_pagetype': '
<c_data><![CDATA[<font color="ff0027" size="2">Replace_with_Page_Type</font>]]></c_data>
'});  ```  ```</script>```
```

> [!IMPORTANT]
> Both product ID and pagetype must be included on every page you want to update a dynamic remarketing list for. Missing either value would keep your dynamic remarketing list from updating for that page. For example, if you pass product IDs on all of your product pages, but not on your home page, then the "Product viewers" dynamic remarketing list will be updated with visitors to your product pages, but the "General visitors" audience will not record people who visited your home page. To target visitors to pages that cannot pass product IDs for any reason, you can use regular [remarketing lists](./hlp_BA_CONC_Audiences_Remarketing.md).
> In the *'event', '',* part of the tag, make sure the two single-quotation marks after *'event',* remain empty.
> You can track multiple products in the same UET tag by including an array of product IDs like this:
> ```
```'ecomm_prodid': ['Replace_with_Product_ID_1','Replace_with_Product_ID_2','Replace_with_Product_ID_3']```
```

In the above JavaScript, change the following parameters:

- ```**Replace_with_Product_ID** ```: Replace this with one of the following product IDs:
   - The exact SKU ID that uniquely identifies a product.  This is sometimes called a UPC (universal product code).
   - An item group ID representing a set of variants for the same product. At least one of the variant attributes (size, color, material, pattern, age_group, or gender) must be provided as part of the product feed, and the same variant attribute must be provided for all items within the group.

> [!IMPORTANT]
> The product ID in your JavaScript code must match an ID in your [Microsoft Merchant Center product feed](./hlp_BA_CONC_AboutBingMerchantCenterCatalogFile.md).

- ```**Replace_with_Page_Type** ```: Replace this with the one of the following values in the right-hand column of this table, depending on the page you will be using this JavaScript in:
|Dynamic remarketing list you're tracking|Required page type|
|---|---|
|General visitors|```'ecomm_pagetype': 'home'```  										```'ecomm_pagetype': 'category'```  										```'ecomm_pagetype': 'other'```  						  										Note: Any user not included in the page type for searchresults, product, cart, or purchase will be included in the general visitors audience.|
|Product searchers|```'ecomm_pagetype': 'searchresults'```  |
|Product viewers|```'ecomm_pagetype': 'product'```  |
|Shopping cart abandoners|```'ecomm_pagetype': 'cart'```  |
|Past buyers|```'ecomm_pagetype': 'purchase'```|

**Note: Customers who buy a product are added to the "past buyers" list and are removed from other lists (for that particular product). For this to work, the UET tag on your purchase confirmation page must send both product ID (ecomm_prodid) and pagetype (ecomm_pagetype).**

> [!IMPORTANT]
> A user and product ID combination can exist in one or more of the following lists: Product searchers, Product viewers, Cart abandoners.
> Once a user/product ID is added to the Past buyers list, they are removed from all of the previous four lists. The 'ecomm_pagetype': 'purchase' is required on the purchase page to remove a user from the other lists for that product ID.
> Similarly, once a user/product ID is added to any one of the following lists, they are removed from General visitors: Product searchers, Product viewers, Cart abandoners.

To see an example of a dynamic remarketing UET tag tracking code installed in the body of a webpage, visit [this webpage](https://go.microsoft.com/fwlink?LinkId=2033601) (English only), right-select in the webpage, and then select **View source** or **View page source** depending on your browser. On this page, you can also define a product ID and page type, and then select a button to trigger a custom event for this dynamic remarketing list. If you use a third-party monitoring tool like Fiddler, you can see the HTTP request generated to bat.bing.com to report each custom event.

> [!NOTE]
> As your webpage loads, it triggers the UET tag, resulting in a number of HTTP requests. The most important request is to "bat.bing" (the one that looks like "http://bat.bing.com/action/0?ti=..."). This request tells Microsoft Advertising  about the user visits to your webpage. You can use third-party tools such as Fiddler to monitor all the requests that your browser is making when your webpage loads.
> For custom events, an additional HTTP request is triggered to report the same to Microsoft Advertising. The request is similar to the bat.bing but it has different parameters to report custom event (as opposed to just page visit).
> You can validate that your dynamic remarketing UET tag tracking codes are working using the [UET Tag Helper](./hlp_BA_CONC_UET_TagHelper.md).

## How do I associate a dynamic remarketing list with a search campaign?
1. [!INCLUDE [Audiences](./includes/Audiences.md)]
1. Select **Create association**.
1. Select the ad group or campaign you want to associate with one or more audiences.
1. Under **Ad group targeting** or **Campaign targeting**, select the audience categories you want to target.
1. Select your **Targeting setting**:
   - **Bid only** : Shows ads to people searching for your ad, with the option to make bid adjustments for the selected audience.
   - **Target and bid** : Shows ads only to the selected audience, with the option to make bid adjustments.

1. Adjust the **Default bid adjustment** if necessary. By default, new targeting associations are set to 15%, but the bid adjustment can range from -90% to +900%.
1. Under **Ad group exclusions** or **Campaign exclusions**, select an audience to exclude, if needed.
1. Select **Save**.

## How do I set up dynamic remarketing for audience campaigns?
> [!IMPORTANT]
> Not everyone has this feature yet. If you don't, don't worry—it's coming soon!

1. From the **Campaigns** page, select the **Campaigns** tab (or from the main menu on the left, select **All campaigns** and then **Campaigns**).
1. Select **Create campaign**.
1. For **What's the goal of this campaign?**, select **Sell products from your catalog**.
1. On the **What kind of ads do you want to run for this campaign?** window, select **Audience ads**.
1. Follow the steps for creating an audience campaign as described in [this article](./hlp_BA_PROC_CreateAudienceCampaign.md). Make sure that, in step 2, you select the **Audience** target criteria and your dynamic remarketing list.

## Can I use a "Target and bid" setting for one audience list and a "Bid only" setting for another audience list in the same ad group or campaign?
No, you can only select one targeting setting per ad group or campaign that will apply to all your audience lists in that ad group or campaign (either "Target and bid" or "Bid only"). It isn't possible to use different targeting settings in the same ad group or campaign for remarketing lists, in-market audiences, and custom audiences. Whichever setting you've selected most recently ("Target and bid" or "Bid only") overrides any previous settings.
## How do I test Dynamic remarketing that I setup on my website?
Go to [Test conversion goals and audiences with UET Tag Helper](./hlp_BA_CONC_UET_TagHelper.md) for complete instructions on Dynamic remarketing.

 
> [!NOTE]
> Dynamic remarketing lists are just one of our [audience targeting options](./hlp_BA_CONC_Audiences_Options.md).


