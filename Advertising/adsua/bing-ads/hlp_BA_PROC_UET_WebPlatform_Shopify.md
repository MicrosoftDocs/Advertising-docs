---
title: Set up UET tags using Shopify
description: If you built your website on Shopify, read this article to learn how to set up UET tags on it.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Set up UET tags using Shopify

> [!NOTE]
> This article shows how to do a basic setup of UET tags using Shopify. Please refer to the [Shopify Help Center](https://go.microsoft.com/fwlink?LinkId=2010843) for more information.
> Microsoft Advertising is not responsible for Shopify's processes or documentation, nor for changes made to Shopify's processes or documentation.
> By installing the Microsoft Advertising  app for Shopify, UET tags are automatically created and added to every page of your website. Go to the [Install an app](https://go.microsoft.com/fwlink?LinkId=2109447) page and follow the prompts to get your Microsoft Advertising  app for Shopify set up.

If you created and manage your website with Shopify, you can add and manage your UET tag there.

## Implementing UET using Shopify

1. In Microsoft Advertising, select **Tools** > **UET tag** and copy your JavaScript UET tag tracking code.
1. Sign in to your Shopify account.
   1. Select **Online Store** > **Themes**.
   1. Under Current theme, select **Actions** > **Edit code**.         ![Edit code in the themes section of Shopify](../images/BA_Conc_UET_Shopify_EditCode.png)

1. Install the UET tag.
   1. Under **Layout**, select **theme.liquid**.          ![Select theme.liquid](../images/BA_Conc_UET_Shopify_ThemeLiquid.png)
   1. Scroll down the page until you are at the **&lt;head&gt;** tag.        ![Scroll to the head tag](../images/BA_Conc_UET_Shopify_HeadTag.png)
   1. Paste the UET tag directly above **{{ content_for_header }}**.
   1. Select **Save**.        ![Paste UET tag above content for header](../images/BA_Conc_UET_Shopify_ContentForHeader.png)

1. Customize your online checkout process.
   1. From the bottom of the left menu, select **Settings**.
   1. Select **Checkout**.        ![Select Settings > Checkout](../images/BA_Conc_UET_Shopify_Checkout.png)
   1. Scroll down to the **Additional scripts** field. Paste the UET tag in **Additional scripts**.        ![Paste the UET tag in Additional scripts](../images/BA_Conc_UET_Shopify_AdditionalScripts.png)
   1. Select **Save**.

1. If you want to report variable revenue, add one of the following code snippets below the UET tracking code you pasted in the previous step:
   1. Use this code if you want to exclude taxes and shipping:
```
<script>   window.uetq = window.uetq || [];    window.uetq.push('event', '', { 'revenue_value': {{ subtotal_price | money_without_currency }}, 'currency': '{{ shop.currency }}' }); </script>
```

   1. Use this code if you want to include taxes and shipping:
```
<script>   window.uetq = window.uetq || [];    window.uetq.push('event', '', { 'revenue_value': {{ total_price | money_without_currency }}, 'currency': '{{ shop.currency }}' }); </script>
```

> [!NOTE]
> To validate that your Shopify UET tag is working, download and install [UET Tag Helper](./hlp_BA_CONC_UET_TagHelper.md). Go to your Shopify website and verify that a UET event is received and that the **Tag ID** matches the tag you selected in Step 1.

## How do I modify my UET tag for dynamic remarketing with Shopify?

1. In Shopify, go to **Online Store** > **Customize**.
1. Select the **Theme actions ellipsis** and select **Edit code**.
1. Under **Templates**, find **index.liquid**.
1. Use this code for **General visitors**:
```
<script>  var productList = [];   {% for product in collections.frontpage.products %}    productList.push({{ product.id }});   {% endfor %}  window.uetq = window.uetq || [];  window.uetq.push('event', '', {'ecomm_prodid': productList, 'ecomm_pagetype': 'home'});   </script>
```

1. Select **Save**.  
1. Under **Templates**, find **search.liquid**.
1. Use this code for **Product searchers**:
```
<script>  var productList = [];   {% for item in search.results %}    {% if item.object_type == 'product' %}      productList.push({{ item.id }});    {% endif %}  {% endfor %}  window.uetq = window.uetq || [];  window.uetq.push('event', '', {'ecomm_prodid': productList, 'ecomm_pagetype': 'searchresults'});   </script>
```

1. Select **Save**.  
1. Under **Templates**, find **product.liquid**.
1. Use this code for **Product viewers**:
```
<script>  window.uetq = window.uetq || [];  window.uetq.push('event', '', {'ecomm_prodid': '{{product.id}}', 'ecomm_pagetype': 'product'});</script>
```

1. Select **Save**.  
1. Under **Templates**, find **cart.liquid**.
1. Use this code for **Shopping cart abandoners**:
```
<script>  var productList = [];  {% for line in cart.items %}    productList.push({{ line.product_id}});  {% endfor %}  window.uetq = window.uetq || [];  window.uetq.push('event', '', {'ecomm_prodid': productList, 'ecomm_pagetype': 'cart'});</script>
```

1. Select **Save**.  
1. Go to **Settings** and select **Checkout**.
1. Under **Order Processing**, find the **Additional scripts** text box.
1. Use this code for **Past buyers**:
```
<script>  var productList = [];  {% for line in checkout.line_items %}    productList.push({{ line.product_id }});  {% endfor %}  window.uetq = window.uetq || [];  window.uetq.push('event', '', {'ecomm_prodid': productList, 'ecomm_pagetype': 'purchase'});</script>
```

1. Select **Save**.

> [!IMPORTANT]
> The product ID in Shopify must match an ID in your MMC product feed.
> Shopify will automatically create product IDs for your products. You can configure Shopify to update your feed management solutions with Shopify product IDs which can then be imported into Microsoft Merchant Center.


