---
title: "Product Ads"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Setup Product ads with the Bing Ads API.
---
# Product Ads
A Microsoft Shopping campaign enables you to advertise the products from your Microsoft Merchant Center store product catalog. Product ads from a Microsoft Shopping campaign include details about the product, an image, and optional promotional text.

You can manage Bing Shopping settings with either the [Bulk Service](../bulk-service/bulk-service-reference.md) or [Campaign Management Service](../campaign-management-service/campaign-management-service-reference.md). You should use the [Bulk Service](../bulk-service/bulk-service-reference.md) if you need to upload or download a high volume of entity settings. For example you can update all ad groups for your entire account in a single upload. In comparison, with the [Campaign Management Service](../campaign-management-service/campaign-management-service-reference.md) you can only update 100 ad groups per call and those ad groups must be in the same campaign. For details see the following sections. 

## <a name="setup"></a>Setup Microsoft Shopping Campaigns
You can run Microsoft Shopping Campaigns for [your own](#setup-bmc) Microsoft Merchant Center store, or bid cooperatively via [your partner's](#setup-cooperative) Microsoft Merchant Center store. 

### <a name="setup-bmc"></a>Setup Microsoft Merchant Center
To set up your own Microsoft Merchant Center store with a catalog that can be used with Microsoft Shopping Campaigns, follow these steps.
1. Set up the customer's Microsoft Merchant Center store. In the Microsoft Advertising web application, click **Tools** &gt; **Microsoft Merchant Center**. Click on **Create store** and provide the requested store details. For information about setting up your store catalog, see [Create a Microsoft Merchant Center store](https://help.ads.microsoft.com/#apex/3/en/51085/1-500) and [How is the feed file organized](https://help.ads.microsoft.com/#apex/3/en/51084/1).

2. [Create a product catalog](https://help.ads.microsoft.com/#apex/3/en/51105/1-500), and then submit the catalog feed via [FTP](https://help.ads.microsoft.com/#apex/3/en/51086/1-500) or the [Microsoft Advertising Content API](/bingads/shopping-content/index).

3. Get your Microsoft Merchant Center store unique system identifier. Call [GetBMCStoresByCustomerId](../campaign-management-service/getbmcstoresbycustomerid.md) and get the *StoreId* from of one of the returned [BMCStore](../campaign-management-service/bmcstore.md) objects, or in the Microsoft Advertising web application, click **Tools** &gt; **Microsoft Merchant Center** to access your store details.

4. Follow the steps to Create a Microsoft Shopping campaign with the [Bulk Service](#bingshopping-bulkservice) or [Campaign Management Service](#bingshopping-campaignservice).

### <a name="setup-cooperative"></a>Setup Cooperative Bidding
In cooperative bidding, two partners share the cost of advertising as they work to drive product sales through certain channels. Typically, these two partners are manufacturers and retailers (or ad agencies and their clients) who have merchandising agreements with one another.
Let's say you manufacture widgets, and Contoso is one of your many authorized dealers. Contoso wants to feature your widgets during their upcoming sale. They've approached you to partner on a marketing blitz of targeted ads designed to drive widget sales and conversions on their website. In partnership, you both agree to share the cost of clicks on a promoted product through your own ad group and your partner's own ad group.

> [!NOTE]
> Not everyone is enabled for Cooperative bidding yet. If you don't, don't worry. It's coming soon.

Both the manufacturer and the retailer have key roles in setting up cooperative bidding. Manufactures must upload a product list with Brand, GTIN, and MPN only. Retailers must grant their partners access to their Microsoft Merchant Center store, which is the gateway to a sales channel. Both manufacturers and retailers are then able to bid on the shared list of goods in the product feed through ad groups.
To set up Cooperative bidding for your partner's Microsoft Merchant Center store with Microsoft Shopping Campaigns, follow these steps.

1. In the Microsoft Advertising [web application](https://secure.ads.microsoft.com/), create a product feed and link to your partner's Microsoft Merchant Center store as described in the [Cooperative bidding](https://help.ads.microsoft.com/#apex/3/en/60004/-1/en/#ext:Default) help article. Put simply, a product feed is a list of items you're promoting with a third party. Typically, a manufacturer or an advertising client is responsible for this step. A product feed contains a list of product attributes, such as Brand, GTIN, and MPN. Once you have your product feed, you'll need access to your retail partner's Microsoft Merchant Center store. Once you have access, keep in mind that you won't be able to see all of the products in your partner's store. You'll only see the products that are a direct match of the items in your product feed. 

2. Follow the steps to Create a Microsoft Shopping campaign with the [Bulk Service](#bingshopping-bulkservice) or [Campaign Management Service](#bingshopping-campaignservice). Please take note of the additional settings for Cooperative bidding. 
    - When you retrieve Microsoft Merchant Center stores via [GetBMCStoresByCustomerId](../campaign-management-service/getbmcstoresbycustomerid.md), the SubType element of the returned [BMCStore](../campaign-management-service/bmcstore.md) must be set to CoOp in order to be eligible for Cooperative bidding. 
    - The campaign subtype must be set to ShoppingCoOperative. 
    - Optionally you can include Cooperative bidding settings for each ad group i.e., bid value or bid boost. If you do not set the bid option, by default it is set to bid value i.e., the auction will use the fixed bid that you set for each product group. If you set the bid option to bid boost, you must also specify the Bid boost percentage that allows your cooperative bid to flex, as well as the Maximum value of cost per click that you're willing to pay. Your cost per click will be the lower of the two values relative to your partner's bid. (For example, let's say your partner bids $5 USD on a keyword. If your bid boost set to 20 percent and your maximum value is 50 cents, your share would be 50 cents and not $1 USD.)
    - Please note the ProductType and CustomLabel [product conditions](../campaign-management-service/productcondition.md) are not supported for Cooperative bidding. The GTIN and MPN operands are optional and only available with Cooperative bidding via campaign and ad group level product conditions. 

## <a name="bingshopping-bulkservice"></a>Create a Microsoft Shopping campaign with the Bulk Service
The [Bulk Service](../bulk-service/bulk-service-reference.md) create, update, and delete operations can be completed using Bulk upload. You can use Bulk download to read back your data. For more information see [Bulk File Schema](../bulk-service/bulk-file-schema.md) and [Bulk Download and Upload](bulk-download-upload.md).

These are the Bing Shopping entities that can be accessed using the [Bulk Service](../bulk-service/bulk-service-reference.md).

- [Campaign](../bulk-service/campaign.md)
- [Campaign Product Scope](../bulk-service/campaign-product-scope.md)
- [Ad Group](../bulk-service/ad-group.md)
- [Ad Group Product Partition](../bulk-service/ad-group-product-partition.md)
- [Product Ad](../bulk-service/product-ad.md)

To create a Microsoft Shopping campaign, follow these steps.

1. Create one or more Microsoft Shopping Campaigns.

    > [!NOTE]
    > You must create designated campaigns for Bing Shopping. You may not create text ads in your Microsoft Shopping Campaigns.

    - Set the *Campaign Type* field of the [Campaign](../bulk-service/campaign.md) to *Shopping*.

    - Set the *Priority* field of the [Campaign](../bulk-service/campaign.md) to 0, 1, or 2.

    - Set the *COUNTRY_CODE* field of the [Campaign](../bulk-service/campaign.md).

    - Set the *Store Id* field of the [Campaign](../bulk-service/campaign.md).

2. Optionally, you can upload a [Campaign Product Scope](../bulk-service/campaign-product-scope.md) criterion that will be associated with your Microsoft Shopping campaign. Use the product scope criterion to include a subset of your product catalog, for example a specific brand, category, or product type. A campaign can only be associated with one [Campaign Product Scope](../bulk-service/campaign-product-scope.md), which contains a list of up to 7 product conditions. You'll also be able to specify more specific product conditions for each ad group.

    > [!NOTE]
    > Product conditions might not be returned in the order that you submitted them.

3. Upload an [Ad Group](../bulk-service/ad-group.md) and set its *Parent Id* field to the *Id* of the campaign added above.

4. Upload one or more [Ad Group Product Partition](../bulk-service/ad-group-product-partition.md) records which represent product partition nodes in a tree structure that will be used to further refine the product catalog offers. Duplicate or conflicting product conditions attempted within an ad group's product partition group will fail during the upload operation; however, the operation will not validate whether duplicate or conflicting conditions already exist within the campaign level [Campaign Product Scope](../bulk-service/campaign-product-scope.md). For example given one ad group and one campaign, the [Campaign Product Scope](../bulk-service/campaign-product-scope.md) and [Ad Group Product Partition](../bulk-service/ad-group-product-partition.md) may each have *Product Condition 1* set to CategoryL1 and *Product Value 1* set to Animals &amp; Pet Supplies, and the service will not throw any error or warning for a duplicate condition.

    > [!NOTE]
    > There is a 1 to 1 relationship between ad groups and product groups. In other words, each ad group has one product group and vice versa. In the Microsoft Advertising web application, for each ad group you would add one product group with multiple levels of division or multiple partitions. This is the equivalent of adding ad group level product partitions using the Bing Ads API. 

    Please also consider the following validation rules for uploading [Ad Group Product Partition](../bulk-service/ad-group-product-partition.md) records.

    - At minimum you must specify at least the root node for the product partition group tree structure. The product partition group's root node must have its *Product Condition 1* field set to "All" and *Product Value 1* null or empty. If you are bidding on all products in the catalog equally, set the *Sub Type* field to *Unit*. If you are partitioning the bids based on more specific product conditions, then set the *Sub Type* field to *Subdivision*, the *Parent Criterion Id* to null or empty, and the *Id* to a negative value. You will use the negative value as *Parent Criterion Id* for any child nodes.

    - The root node is considered level 0, and a tree can have branches up to 7 levels deep.

    - Per upload request, you can include a maximum of 20,000 product partition tree nodes per ad group. The entire product partition tree node count for an ad group cannot exceed 20,000.

    - The product partition tree nodes for the same tree (same ad group) must be grouped together in the file.

    - The order of the product partition nodes is not guaranteed during download, and parent nodes might be provided after child nodes; however, all nodes for the same ad group will be grouped together in the file.

    - If you are creating or modifying the tree structure, parent product partition tree nodes must be ordered ahead of the child product partition tree nodes ; however, the order does not matter for non-structural changes such as updating the bid. For example if you want to update the bids without adding, deleting, or updating the tree structure, then you only need to upload the *Id*, *Parent Id*, and *Bid* fields.

    - To update the *Product Condition 1*, *Product Value 1* or *Is Excluded* field, you must delete the existing product partition tree node and upload a new product partition tree node which will get a new identifier.

    - If any action fails, all remaining actions that might have otherwise succeeded will also fail.

    - All product partition node addition and deletion actions must result in a complete tree structure.

    - Every path from the root node to the end of a branch must terminate with a leaf node (*Sub Type*=Unit). Every Unit must have a bid, unless the *Is Excluded* field is TRUE which means that the node is a negative ad group criterion.

    - Every subdivision must have at least one leaf node that bids on the remainder of the subdivision's conditions, i.e. use the same operand as its sibling unit(s) and set its *Product Value 1* null or empty.

    - If you are adding partitions with multiple levels where neither the parent or child yet exist, use a negative int value as a reference to identify the parent. For example set the both the parent's *Id*, and the child's *Parent Criterion Id* field to the same negative value. The negative IDs are only valid for the duration of the call. Unique system identifiers for each successfully added ad group criterion are returned in the upload result file.

    - The *Bid* and *Destination Url* fields are only applicable if the *Is Excluded* field is FALSE which means that the node is a biddable ad group criterion. However, these fields are ignored for *Subdivision* partition nodes. Those elements are only relevant for *Unit* (leaf) partition nodes.

    - To pause any product partition you must pause the entire ad group by updating the *Status* field of the [Ad Group](../bulk-service/ad-group.md) to Paused. You can pause the entire campaign by updating the *Status* field of the [Campaign](../bulk-service/campaign.md) to Paused.

    - For a *Deleted* action you only need to specify the *Id* and *Parent Id*.

    - If you delete a parent product partition, all of its children and descendants will also be deleted.

    - You may not specify duplicate product conditions in a branch. 

5. Upload a product ad. You must add at least one [Product Ad](../bulk-service/product-ad.md) to the corresponding ad group. A product ad is not used directly for delivered ad copy. Instead, the delivery engine generates product ads from the product details that it finds in your Microsoft Merchant Center store's product catalog. The product ad identifier can be used for reporting analytics. Use [Merchant Promotions](https://help.ads.microsoft.com/#apex/3/en/56805/0) if you want tags to appear at the bottom of your product ad as "special offer" links, helping to increase customer engagement. 

After you complete these steps, the delivery engine can begin serving product ads for the products that it finds in the customer's Microsoft Merchant Center store. If the user's search query has product intent, the delivery engine searches the customer's Microsoft Merchant Center store for products that matches the query. If it finds a product, and the product meets the conditions of the product filters specified in the product scope and product partitions, the delivery engine generates a product ad using the product details from the store.

## <a name="bingshopping-campaignservice"></a>Create a Microsoft Shopping campaign with the Campaign Management Service
To create a Microsoft Shopping campaign with the Campaign Management API, follow these steps.

> [!TIP]
> For code examples that show how to apply product conditions for Microsoft Shopping Campaigns using the Campaign Management service, see [Product Ads Code Example](code-example-product-ads.md).

1. Create one or more Microsoft Shopping Campaigns.

    > [!NOTE]
    > You must create designated campaigns for Bing Shopping. You may not create text ads in your Microsoft Shopping Campaigns.

    - Set the *CampaignType* element of the [Campaign](../campaign-management-service/campaign.md) to *Shopping*.

    - Create a [ShoppingSetting](../campaign-management-service/shoppingsetting.md) instance and set its *Priority* (0, 1, or 2), *SalesCountryCode*, and *StoreId* elements. Add this shopping setting to the *Settings* list of the [Campaign](../campaign-management-service/campaign.md).

2. Optionally, you can create a [ProductScope](../campaign-management-service/productscope.md) criterion that will be associated with your Microsoft Shopping campaign. Use the product scope criterion to include a subset of your product catalog, for example a specific brand, category, or product type. A campaign can only be associated with one *ProductScope*, which contains a list of up to 7 [ProductCondition](../campaign-management-service/productcondition.md). You'll also be able to specify more specific product conditions for each ad group.

    Call the [AddCampaignCriterions](../campaign-management-service/addcampaigncriterions.md) operation to associate the Microsoft Shopping campaign with your product scope criterion.

    > [!NOTE]
    > Product conditions might not be returned in the order that you submitted them.

3. Create an [AdGroup](../campaign-management-service/adgroup.md) and add it to the campaign by calling [AddAdGroups](../campaign-management-service/addadgroups.md).

4. Create a list of [AdGroupCriterionAction](../campaign-management-service/adgroupcriterion.md) objects in a tree structure that will be used to further refine the product catalog offers. Apply the list of actions by calling [ApplyProductPartitionActions](../campaign-management-service/applyproductpartitionactions.md). Duplicate or conflicting product conditions attempted within an ad group's product partition group will fail via the [ApplyProductPartitionActions](../campaign-management-service/applyproductpartitionactions.md) operation; however, the operation will not validate whether duplicate or conflicting conditions already exist within the campaign level [ProductScope](../campaign-management-service/productscope.md).

    > [!NOTE]
    > To retrieve product partitions after they have been applied, call [GetAdGroupCriterionsByIds](../campaign-management-service/getadgroupcriterionsbyids.md) and set the *AdGroupCriterionIds* element to *null* to get all product partitions for the ad group. The product partition with *ParentCriterionId* set to *null* is the root node.

    Please also consider the following validation rules for the [ApplyProductPartitionActions](../campaign-management-service/applyproductpartitionactions.md) operation.

    - At minimum you must specify at least the root node for the product partition group tree structure. The product partition group's root [BiddableAdGroupCriterion](../campaign-management-service/biddableadgroupcriterion.md) must have its condition *Operand* set to "All" and *Attribute* to *null*. If you are bidding on all products in the catalog equally, set the *PartitionType* to Unit. If you are partitioning the bids based on more specific product conditions, then set the *PartitionType* to Subdivision, the *ParentCriterionId* to *null*, and the *Id* to a negative value. You will use the negative value as *ParentCriterionId* for any child nodes.

    - The root node is considered level 0, and a tree can have branches up to 7 levels deep.

    - You may specify up to 5,000 [AdGroupCriterionAction](../campaign-management-service/adgroupcriterion.md) objects per call. The entire tree created through multiple calls can have up to 20,000 nodes.

    - Each of the [AdGroupCriterionAction](../campaign-management-service/adgroupcriterion.md) objects must have the same *AdGroupId*, otherwise the call will fail.
    
    - To update the *Condition* or *Attribute* properties, you must delete the existing product partition tree node and add a new product partition tree node which will get a new identifier. Likewise to update from a [BiddableAdGroupCriterion](../campaign-management-service/biddableadgroupcriterion.md) to a [NegativeAdGroupCriterion](../campaign-management-service/negativeadgroupcriterion.md) or vice versa, you must delete the existing product partition tree node and add a new product partition tree node which will get a new identifier. 

    - If any action fails, all remaining actions that might have otherwise succeeded will also fail.

    - All actions in one call must result in a complete tree structure. If you need to apply more than 5,000 actions per ad group, you must make multiple calls. Get the parent ad group criterion identifiers from the first call, and then add more children as needed in subsequent calls.

    - Every path from the root node to the end of a branch must terminate with a leaf node (*ProductPartitionType*=Unit). Every Unit must have a bid, unless the node is a [NegativeAdGroupCriterion](../campaign-management-service/negativeadgroupcriterion.md).

    - Every subdivision must have at least one leaf node that bids on the remainder of the subdivision's conditions, i.e. use the same operand as its sibling unit(s) and set its *Attribute* to *null*.

    - You may only specify a child node after its parent.

    - If you are adding partitions with multiple levels where neither the parent or child yet exist, use a negative int value as a reference to identify the parent. For example set the both the parent's *Id*, and the child's *ParentCriterionId* element to the same negative value. The negative IDs are only valid for the duration of the call. Unique system identifiers for each successfully added ad group criterion are returned in the response message.

    - The *CriterionBid* and *DestinationUrl* elements of the [BiddableAdGroupCriterion](../campaign-management-service/biddableadgroupcriterion.md) are ignored for *Subdivision* partition nodes. Those elements are only relevant for *Unit* (leaf) partition nodes.

    - The *Status* element of the *AdGroupCriterion* is always ignored for product partition criterion. To add, update, or delete a product partition, set the *Action* element of the corresponding [AdGroupCriterionAction](../campaign-management-service/adgroupcriterion.md).

    - To pause any product partition you must pause the entire ad group by calling [UpdateAdGroups](../campaign-management-service/updateadgroups.md). You can call [UpdateCampaigns](../campaign-management-service/updatecampaigns.md) to pause the entire campaign.

    - The *EditorialStatus* element of the *AdGroupCriterion* has no significant meaning for product partition criterion. Editorial validation for the product catalog is completed in the Microsoft Merchant Center store.

    - For a *Delete* action you only need to specify the *Id* and *AdGroupId* in the  *AdGroupCriterion*.

    - If you delete a parent product partition, all of its children and descendants will also be deleted.

    - You may not specify duplicate product conditions in a branch. 

5. Create a product ad. You must add at least one [ProductAd](../campaign-management-service/productad.md) to the ad group via the [AddAds](../campaign-management-service/addads.md) operation. A product ad is not used directly for delivered ad copy. Instead, the delivery engine generates product ads from the product details that it finds in your Microsoft Merchant Center store's product catalog. The product ad identifier can be used for reporting analytics. Use [Merchant Promotions](https://help.ads.microsoft.com/#apex/3/en/56805/0) if you want tags to appear at the bottom of your product ad as "special offer" links, helping to increase customer engagement. 

After you complete these steps, the delivery engine can begin serving product ads for the products that it finds in the customer's Microsoft Merchant Center store. If the user's search query has product intent, the delivery engine searches the customer's Microsoft Merchant Center store for products that matches the query. If it finds a product, and the product meets the conditions of the product filters specified in the product scope and product partitions, the delivery engine generates a product ad using the product details from the store.

## <a name="reports"></a>Performance Statistics for Microsoft Shopping Campaigns
The [Product Ads Reports](report-types.md#productads) can be submitted and downloaded with the [Reporting Service](../reporting-service/reporting-service-reference.md) to get performance data for Microsoft Shopping Campaigns.

If you request a report using account level scope, then the performance reports will include aggregated data for all campaigns, whether or not the campaign type is Bing Shopping. To only get data for Microsoft Shopping Campaigns, use campaign scope or ad group scope. The following is an example SOAP request that specifies campaign level scope.

```xml
<Scope>
    <AccountIds i:nil="true" xmlns:a="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <AdGroups i:nil="true" />
    <Campaigns>
    <CampaignReportScope>
        <AccountId>AccountIdGoesHere</AccountId>
        <CampaignId>CampaignIdGoesHere</CampaignId>
    </CampaignReportScope>
    </Campaigns>
</Scope>
```
For more information about using the [Reporting Service](../reporting-service/reporting-service-reference.md), see [Reports](reports.md) and [Request and Download a Report](request-download-report.md).

> [!NOTE]
> Performance statistics and the product partition tree structure returned by the Reporting service lags behind the performance statistics that you see in the Microsoft Advertising web application by up to an hour. 

