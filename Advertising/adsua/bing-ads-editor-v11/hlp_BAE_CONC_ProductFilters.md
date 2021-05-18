---
title: Learn about product filters for Microsoft Shopping Campaigns
description: Learn more about product filters and how they're organized.
ms.service: "Bing-Ads-Editor-v11"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Learn about product filters for Microsoft Shopping Campaigns

## What are product filters?
A product group in Microsoft Shopping Campaigns narrows down the default group to a customized list of specific products. Each of the product groups can be divided up to 7 levels. Product filters are organized similarly, where you can have up to 7 condition levels, with each condition containing up to 7 values.

Microsoft Advertising matches customers' searches to relevant products or services from your Microsoft Merchant Center catalog by default. You can use product filters to exclude products in your Microsoft Merchant Center account. Doing so will only show products from your Microsoft Merchant Center account that matches the product groups you defined. Product filters are set at the campaign level and are optional.

## Why didn't all my product filter details get imported?
A product group in Microsoft Shopping Campaigns narrows down the default group to a customized list of specific products. Each of the product groups can be divided up to 7 levels. Product filters are organized similarly, where you can have up to 7 condition levels, with each condition containing up to 7 values.

When making updates to your product filters, be sure to include all conditions and values starting from Product Condition 1 and Product Value 1. This is true for both bulk updates with a file, as well as updates made directly in Microsoft Advertising Editor.

Here are some scenarios as to why your product filter details imported incorrectly.

**Scenario**: You want to add a new product condition and product value to an existing filter.

Your current filter contains Product Condition 1 and Product Value 1. The import file contains the details for Product Condition 2 and Product Value 2, but doesn’t include the existing product condition and value details. When you imported the file, Product Condition 2 and Product Value 2 were skipped, as Product Condition 1 and Product Value 1 was missing.

**Scenario**: You want to make changes to only one of the production conditions and values out of the list.

Your current filter contains Product Condition 1 – 3, and Product Value 1 – 3. You want to make changes only to Product Condition 1 and Product Value 1, so you only include those two attributes in the import file. When you imported the file, Product Condition 2 – 3 and Product Value 2 – 3 were removed, as they weren’t indicated in the import file.

**Solution**: Always include **all** product conditions and values, starting from Product Condition 1 and Production Value 1, even if you’re not making changes to them. That way, the system will be able to map the attributes correctly. Likewise, if you want to remove product conditions and values, only include the attributes you want to keep.

The same rules apply when you make changes directly in the Make multiple changes panel in Microsoft Advertising Editor. Always start from Product Condition 1 and Product Value 1 to add, remove, or update attributes.


