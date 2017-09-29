---
title: "Product Ads"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
---
# Product Ads
A Bing Shopping campaign enables you to advertise the products from your Bing Merchant Center store product catalog. Product ads from a Bing Shopping campaign include details about the product, an image, and optional promotional text.

You can manage Bing Shopping settings with either the [Bulk Service](~/bulk/bulk-service-reference.md) or [Campaign Management Service](~/campaign-management/campaign-management-service-reference.md). You should use the [Bulk Service](~/bulk/bulk-service-reference.md) if you need to upload or download a high volume of entity settings. For example you can update all ad groups for your entire account in a single upload. In comparison, with the [Campaign Management Service](~/campaign-management/campaign-management-service-reference.md) you can only update 100 ad groups per call and those ad groups must be in the same campaign. For details see the following sections. 

-   [Setup Bing Merchant Center](#setup)

-   [Create a Bing Shopping Campaign with the Bulk Service](#bingshopping-bulkservice)

-   [Create a Bing Shopping Campaign with the Campaign Management Service](#bingshopping-campaignservice)

-   [Product Conditions](#conditions)

-   [Performance Statistics for Bing Shopping Campaigns](#reports)


## <a name="setup"></a>Setup Bing Merchant Center
To create a Bing Shopping campaign, follow these steps.

1.  Set up the customer's Bing Merchant Center store. In the Bing Ads web application, click **Tools** &gt; **Bing Merchant Center**. Click on **Create store** and provide the requested store details. For information about setting up your store catalog, see [Create a Bing Merchant Center store](https://help.bingads.microsoft.com/#apex/3/en/51085/1-500) and [How is the feed file organized](https://help.bingads.microsoft.com/#apex/3/en/51084/1).

2.  [Create a product catalog](https://help.bingads.microsoft.com/#apex/3/en/51105/1-500), and then submit the catalog feed via [FTP](https://help.bingads.microsoft.com/#apex/3/en/51086/1-500) or the [Bing Ads Content API](~/shopping-content/index.md).

3.  Get your Bing Merchant Center store unique system identifier. Call [GetBMCStoresByCustomerId](~/campaign-management/getbmcstoresbycustomerid.md) and get the *StoreId* from of one of the returned [BMCStore]((~/campaign-management/bmcstore.md) objects, or in the Bing Ads web application, click **Tools** &gt; **Bing Merchant Center** to access your store details.

After you complete these steps, you can follow the steps to [Create a Bing Shopping Campaign with the Campaign Management Service](#bingshopping-campaignservice).

## <a name="bingshopping-bulkservice"></a>Create a Bing Shopping Campaign with the Bulk Service
The [Bulk Service](~/bulk/bulk-service-reference.md) create, update, and delete operations can be completed using Bulk upload. You can use Bulk download to read back your data. For more information see [Bulk File Schema]((~/bulk/bulk-file-schema.md) and [Bulk Download and Upload](../guides/bulk-download-upload.md).

These are the Bing Shopping entities that can be accessed using the [Bulk Service](~/bulk/bulk-service-reference.md).

-   [Campaign](~/bulk/campaign.md)
-   [Campaign Product Scope](~/bulk/campaign-product-scope.md)
-   [Ad Group](~/bulk/ad-group.md)
-   [Ad Group Product Partition](~/bulk/ad-group-product-partition.md)
-   [Product Ad](~/bulk/product-ad.md)

For code examples that show how to apply product conditions for Bing Shopping campaigns using the Bulk service, see [Bulk Shopping Campaigns Example](../guides/code-example-bulk-shopping-campaigns.md).

To create a Bing Shopping campaign, follow these steps.

1.  Create one or more Bing Shopping campaigns.

    > [!TIP]
    > You must create designated campaigns for Bing Shopping. You may not create text ads in your Bing Shopping campaigns.

    -   Set the *Campaign Type* field of the [Campaign](~/bulk/campaign.md) to *Shopping*.

    -   Set the *Priority* field of the [Campaign](~/bulk/campaign.md) to 0, 1, or 2.

    -   Set the *COUNTRY_CODE* field of the [Campaign](~/bulk/campaign.md).

    -   Set the *Store Id* field of the [Campaign](~/bulk/campaign.md).

2.  Optionally, you can upload a [Campaign Product Scope](~/bulk/campaign-product-scope.md) criterion that will be associated with your Bing Shopping campaign. Use the product scope criterion to include a subset of your product catalog, for example a specific brand, category, or product type. A campaign can only be associated with one [Campaign Product Scope]((~/bulk/campaign-product-scope.md), which contains a list of up to 7 product conditions. You'll also be able to specify more specific product conditions for each ad group.

    > [!NOTE]
    > Product conditions may be returned by Bing Ads services in a different order from the order that you submitted.

3.  Upload an [Ad Group](~/bulk/ad-group.md) and set its *Parent Id* field to the *Id* of the campaign added above.

4.  Upload one or more [Ad Group Product Partition](~/bulk/ad-group-product-partition.md) records which represent product partition nodes in a tree structure that will be used to further refine the product catalog offers. Duplicate or conflicting product conditions attempted within an ad group's product partition group will be rejected by the upload operation; however, the operation will not validate whether duplicate or conflicting conditions already exist within the campaign level [Campaign Product Scope](~/bulk/campaign-product-scope.md). For example given one ad group and one campaign, the [Campaign Product Scope](~/bulk/campaign-product-scope.md) and [Ad Group Product Partition](~/bulk/ad-group-product-partition.md) may each have *Product Condition 1* set to CategoryL1 and *Product Value 1* set to Animals &amp; Pet Supplies, and the service will not throw any error or warning for a duplicate condition.

    > [!NOTE]
    > There is a 1 to 1 relationship between ad groups and product groups. In other words, each ad group has one product group and vice versa. In the Bing Ads web application, for each ad group you would add one product group with multiple levels of division or multiple partitions. This is the equivalent of adding ad group level product partitions using the Bing Ads API. 

    Please also consider the following validation rules for uploading [Ad Group Product Partition](~/bulk/ad-group-product-partition.md) records.

    -   At minimum you must specify at least the root node for the product partition group tree structure. The product partition group's root node must have its *Product Condition 1* field set to "All" and *Product Value 1* null or empty. If you are bidding on all products in the catalog equally, set the *Sub Type* field to *Unit*. If you are partitioning the bids based on more specific product conditions, then set the *Sub Type* field to *Subdivision*, the *Parent Criterion Id* to null or empty, and the *Id* to a negative value. You will use the negative value as *Parent Criterion Id* for any child nodes.

    -   The root node is considered level 0, and a tree can have branches up to 7 levels deep.

    -   Per upload request, you can include a maximum of 20,000 product partition tree nodes per ad group. The entire product partition tree node count for an ad group cannot exceed 20,000.

    -   The product partition tree nodes for the same tree (same ad group) must be grouped together in the file.

    -   The order of the product partition nodes is not guaranteed during download, and parent nodes might be provided after child nodes; however, all nodes for the same ad group will be grouped together in the file.

    -   If you are creating or modifying the tree structure, parent product partition tree nodes must be ordered ahead of the child product partition tree nodes ; however, the order does not matter for non-structural changes such as updating the bid. For example if you want to update the bids without adding, deleting, or updating the tree structure, then you only need to upload the *Id*, *Parent Id*, and *Bid* fields.

    -   To update the *Product Condition 1*, *Product Value 1* or *Is Excluded* field, you must delete the existing product partition tree node and upload a new product partition tree node which will get a new identifier.

    -   If any action fails, all remaining actions that might have otherwise succeeded will be rejected.

    -   All product partition node addition and deletion actions must result in a complete tree structure.

    -   Every path from the root node to the end of a branch must terminate with a leaf node (*Sub Type*=Unit). Every Unit must have a bid, unless the *Is Excluded* field is TRUE which means that the node is a negative ad group criterion.

    -   Every subdivision must have at least one leaf node that bids on the remainder of the subdivision's conditions, i.e. use the same operand as its sibling unit(s) and set its *Product Value 1* null or empty.

    -   If you are adding partitions with multiple levels where neither the parent or child yet exist, use a negative int value as a reference to identify the parent. For example set the both the parent's *Id*, and the child's *Parent Criterion Id* field to the same negative value. The negative IDs are only valid for the duration of the call. Unique system identifiers for each successfully added ad group criterion are returned in the upload result file.

    -   The *Bid* and *Destination Url* fields are only applicable if the *Is Excluded* field is FALSE which means that the node is a biddable ad group criterion. However, these fields are ignored for *Subdivision* partition nodes. Those elements are only relevant for *Unit* (leaf) partition nodes.

    -   To pause any product partition you must pause the entire ad group by updating the *Status* field of the [Ad Group](~/bulk/ad-group.md) to Paused. You can pause the entire campaign by updating the *Status* field of the [Campaign](~/bulk/campaign.md) to Paused.

    -   For a *Deleted* action you only need to specify the *Id* and *Parent Id*.

    -   If you delete a parent product partition, all of its children and descendants will also be deleted.

    -   You may not specify duplicate product conditions in a branch. For more information, see [Product Conditions](#conditions).

5.  Upload a product ad. You must add at least one [Product Ad](~/bulk/product-ad.md) to the corresponding ad group. A [Product Ad](~/bulk/product-ad.md) is not used directly for delivered ad copy. Instead, the delivery engine generates product ads from the product details that it finds in your Bing Merchant Center store's product catalog. The primary purpose of the [Product Ad](~/bulk/product-ad.md) object is to provide promotional text that the delivery engine adds to the product ads that it generates. For example, if the promotional text is set to ?Free shipping on $99 purchases?, the delivery engine will set the product ad's description to ?Free shipping on $99 purchases.?

After you complete these steps, the delivery engine can begin serving product ads for the products that it finds in the customer's Bing Merchant Center store. If the user's search query has product intent, the delivery engine searches the customer's Bing Merchant Center store for products that matches the query. If it finds a product, and the product meets the conditions of the product filters specified in the product scope and product partitions, the delivery engine generates a product ad using the product details from the store.

## <a name="bingshopping-campaignservice"></a>Create a Bing Shopping Campaign with the Campaign Management Service
These are the Bing Shopping entities that can be accessed using the [Campaign Management Service](~/campaign-management/campaign-management-service-reference.md). You can create, read, update, and delete these entities.

> [!NOTE]
> Partial success is supported for a subset of these operations. For example if you submit 10 ad groups and 2 fail, the remaining 8 will succeed. For more information, see [Partial Success using the Campaign Management Service](../guides/handle-service-errors-exceptions.md#partialsuccess).

|Entities|Service Operations|
|------------|----------------------|
|[Campaign](~/campaign-management/campaign.md)|[AddCampaigns]((~/campaign-management/addcampaigns.md)<br /><br />[DeleteCampaigns]((~/campaign-management/deletecampaigns.md)<br /><br />[GetCampaignsByAccountId]((~/campaign-management/getcampaignsbyaccountid.md)<br /><br />[GetCampaignsByIds]((~/campaign-management/getcampaignsbyids.md)<br /><br />[UpdateCampaigns]((~/campaign-management/updatecampaigns.md)|
|[ProductScope](~/campaign-management/productscope.md)|[AddCampaignCriterions](~/campaign-management/addcampaigncriterions.md)<br /><br />[DeleteCampaignCriterions]((~/campaign-management/updatecampaigncriterions.md)<br /><br />[GetCampaignCriterionsByIds]((~/campaign-management/getcampaigncriterionsbyids.md)<br /><br />[UpdateCampaignCriterions]((~/campaign-management/updatecampaigncriterions.md)|
|[AdGroup](~/campaign-management/adgroup.md)|[AddAdGroups]((~/campaign-management/addadgroups.md)<br /><br />[DeleteAdGroups]((~/campaign-management/deleteadgroups.md)<br /><br />[GetAdGroupsByCampaignId](~/campaign-management/getadgroupsbycampaignid.md)<br /><br />[GetAdGroupsByIds](~/campaign-management/getadgroupsbyids.md)<br /><br />[UpdateAdGroups](~/campaign-management/updateadgroups.md)|
|[ProductAd](~/campaign-management/productad.md)|[AddAds](~/campaign-management/addads.md)<br /><br />[GetAdsByAdGroupId](~/campaign-management/getadsbyadgroupid.md)<br /><br />[DeleteAds](~/campaign-management/deleteads.md)<br /><br />[GetAdsByEditorialStatus](~/campaign-management/getadsbyeditorialstatus.md)<br /><br />[GetAdsByIds](~/campaign-management/getadsbyids.md)<br /><br />[UpdateAds](~/campaign-management/updateads.md)|
|[BiddableAdGroupCriterion](~/campaign-management/biddableadgroupcriterion.md)<br /><br />**Note:** Currently the only supported [BiddableAdGroupCriterion](~/campaign-management/biddableadgroupcriterion.md) is used for a Bing Shopping campaign [ProductPartition](~/campaign-management/productpartition.md). You cannot update or delete a product partition, so [ApplyProductPartitionActions](~/campaign-management/applyproductpartitionactions.md) is used for all write operations. [AddAdGroupCriterions](~/campaign-management/addadgroupcriterions.md), [DeleteAdGroupCriterions](~/campaign-management/deleteadgroupcriterions.md), and [UpdateAdGroupCriterions](~/campaign-management/updateadgroupcriterions.md) operations are not supported for managing Bing Shopping campaigns.|[ApplyProductPartitionActions](~/campaign-management/applyproductpartitionactions.md)<br /><br />[GetAdGroupCriterionsByIds](~/campaign-management/getadgroupcriterionsbyids.md)

For code examples that show how to apply product conditions for Bing Shopping campaigns using the Campaign Management service, see [Shopping Campaigns Example](../guides/code-example-shopping-campaigns.md).

To create a Bing Shopping campaign, follow these steps.

1.  Create one or more Bing Shopping campaigns.

    > [!TIP]
    > You must create designated campaigns for Bing Shopping. You may not create text ads in your Bing Shopping campaigns.

    -   Set the *CampaignType* element of the [Campaign](~/campaign-management/campaign.md) to *Shopping*.

    -   Create a [ShoppingSetting](~/campaign-management/shoppingsetting.md) instance and set its *Priority* (0, 1, or 2), *SalesCountryCode*, and *StoreId* elements. Add this shopping setting to the *Settings* list of the [Campaign](~/campaign-management/campaign.md).

2.  Optionally, you can create a [ProductScope](~/campaign-management/productscope.md) criterion that will be associated with your Bing Shopping campaign. Use the product scope criterion to include a subset of your product catalog, for example a specific brand, category, or product type. A campaign can only be associated with one *ProductScope*, which contains a list of up to 7 [ProductCondition](~/campaign-management/productcondition.md). You'll also be able to specify more specific product conditions for each ad group.

    Call the [AddCampaignCriterions](~/campaign-management/addcampaigncriterions.md) operation to associate the Bing Shopping campaign with your product scope criterion.

    > [!NOTE]
    > Product conditions may be returned by Bing Ads services in a different order from the order that you submitted.

3.  Create an [AdGroup](~/campaign-management/adgroup.md) and add it to the campaign by calling [AddAdGroups](~/campaign-management/addadgroups.md).

4.  Create a list of [AdGroupCriterionAction](~/campaign-management/adgroupcriterion.md) objects in a tree structure that will be used to further refine the product catalog offers. Apply the list of actions by calling [ApplyProductPartitionActions](~/campaign-management/applyproductpartitionactions.md). Duplicate or conflicting product conditions attempted within an ad group's product partition group will be rejected by the [ApplyProductPartitionActions](~/campaign-management/applyproductpartitionactions.md) operation; however, the operation will not validate whether duplicate or conflicting conditions already exist within the campaign level [ProductScope](~/campaign-management/productscope.md).

    > [!NOTE]
    > To retrieve product partitions after they have been applied, call [GetAdGroupCriterionsByIds](~/campaign-management/getadgroupcriterionsbyids.md) and set the *AdGroupCriterionIds* element to *null* to get all product partitions for the ad group. The product partition with *ParentCriterionId* set to *null* is the root node.

    Please also consider the following validation rules for the [ApplyProductPartitionActions](~/campaign-management/applyproductpartitionactions.md) operation.

    -   At minimum you must specify at least the root node for the product partition group tree structure. The product partition group's root [BiddableAdGroupCriterion](~/campaign-management/biddableadgroupcriterion.md) must have its condition *Operand* set to "All" and *Attribute* to *null*. If you are bidding on all products in the catalog equally, set the *PartitionType* to Unit. If you are partitioning the bids based on more specific product conditions, then set the *PartitionType* to Subdivision, the *ParentCriterionId* to *null*, and the *Id* to a negative value. You will use the negative value as *ParentCriterionId* for any child nodes.

    -   The root node is considered level 0, and a tree can have branches up to 7 levels deep.

    -   You may specify up to 5,000 [AdGroupCriterionAction](~/campaign-management/adgroupcriterion.md) objects per call. The entire tree created through multiple calls can have up to 20,000 nodes.

    -   Each of the [AdGroupCriterionAction](~/campaign-management/adgroupcriterion.md) objects must have the same *AdGroupId*, otherwise the call will fail.
    
    -   To update the *Condition* or *Attribute* properties, you must delete the existing product partition tree node and add a new product partition tree node which will get a new identifier. Likewise to update from a [BiddableAdGroupCriterion](~/campaign-management/biddableadgroupcriterion.md) to a [NegativeAdGroupCriterion](~/campaign-management/negativeadgroupcriterion.md) or vice versa, you must delete the existing product partition tree node and add a new product partition tree node which will get a new identifier. 

    -   If any action fails, all remaining actions that might have otherwise succeeded will be rejected.

    -   All actions in one call must result in a complete tree structure. If you need to apply more than 5,000 actions per ad group, you must make multiple calls. Get the parent ad group criterion identifiers from the first call, and then add more children as needed in subsequent calls.

    -   Every path from the root node to the end of a branch must terminate with a leaf node (*ProductPartitionType*=Unit). Every Unit must have a bid, unless the node is a [NegativeAdGroupCriterion](~/campaign-management/negativeadgroupcriterion.md).

    -   Every subdivision must have at least one leaf node that bids on the remainder of the subdivision's conditions, i.e. use the same operand as its sibling unit(s) and set its *Attribute* to *null*.

    -   You may only specify a child node after its parent.

    -   If you are adding partitions with multiple levels where neither the parent or child yet exist, use a negative int value as a reference to identify the parent. For example set the both the parent's *Id*, and the child's *ParentCriterionId* element to the same negative value. The negative IDs are only valid for the duration of the call. Unique system identifiers for each successfully added ad group criterion are returned in the response message.

    -   The *CriterionBid* and *DestinationUrl* elements of the [BiddableAdGroupCriterion](~/campaign-management/biddableadgroupcriterion.md) are ignored for *Subdivision* partition nodes. Those elements are only relevant for *Unit* (leaf) partition nodes.

    -   The *Status* element of the *AdGroupCriterion* is always ignored for product partition criterion. To add, update, or delete a product partition, set the *Action* element of the corresponding [AdGroupCriterionAction](~/campaign-management/adgroupcriterion.md).

    -   To pause any product partition you must pause the entire ad group by calling [UpdateAdGroups](~/campaign-management/updateadgroups.md). You can call [UpdateCampaigns](~/campaign-management/updatecampaigns.md) to pause the entire campaign.

    -   The *EditorialStatus* element of the *AdGroupCriterion* has no significant meaning for product partition criterion. Editorial validation for the product catalog is completed in the Bing Merchant Center store.

    -   For a *Delete* action you only need to specify the *Id* and *AdGroupId* in the  *AdGroupCriterion*.

    -   If you delete a parent product partition, all of its children and descendants will also be deleted.

    -   You may not specify duplicate product conditions in a branch. For more information, see [Product Conditions](#conditions).

5.  Create a product ad. You must add at least one [ProductAd](~/campaign-management/productad.md) to the corresponding ad group. A *ProductAd* is not used directly for delivered ad copy. Instead, the delivery engine generates product ads from the product details that it finds in your Bing Merchant Center store's product catalog. The primary purpose of the *ProductAd* object is to provide promotional text that the delivery engine adds to the product ads that it generates. For example, if the promotional text is set to ?Free shipping on $99 purchases?, the delivery engine will set the product ad's description to ?Free shipping on $99 purchases.?

    To create a product ad, instantiate a *ProductAd* object and set the *PromotionalText* element as needed. If you do not want to add promotional text to your ads, set *PromotionalText* to null or an empty string. Next, call the [AddAds](~/campaign-management/addads.md) operation to add the product ad to an ad group.

After you complete these steps, the delivery engine can begin serving product ads for the products that it finds in the customer's Bing Merchant Center store. If the user's search query has product intent, the delivery engine searches the customer's Bing Merchant Center store for products that matches the query. If it finds a product, and the product meets the conditions of the product filters specified in the product scope and product partitions, the delivery engine generates a product ad using the product details from the store.

## <a name="conditions"></a>Product Conditions
Multiple product conditions can be specified for each campaign and ad group. Each condition is met if the product's attribute value equals the operand's attribute value. For example, if *Operand* is set to Brand and *Attribute* is set to Contoso, the condition is met if the value of the product catalog's Brand attribute is equal to Contoso.

The following table maps the operand names to the corresponding attribute string restrictions for campaign product scope and ad group product partition.

|Operand Name|Attribute Description|ProductScope Rules|ProductPartition Rules|
|----------------|-------------------------|----------------------|--------------------------|
|All|Must be null.|Not applicable.|For an ad group's product partitions, the root node must have *Operand* set to *"All"* and *Attribute* set to *null*.|
|Brand|The product's manufacturer, brand, or publisher.<br /><br />A maximum of 1,000 characters.|The *Brand* operand may only be specified once per campaign product scope filter.|The *Brand* operand may be used in multiple branches, but may only be specified once per branch.|
|Condition|The condition of the product.<br /><br />If *Operand* is set to Condition, the supported attribute values that you can specify are *New*, *Used*, and *Refurbished*.|The *Condition* operand may only be specified once per campaign product scope filter.|The *Condition* operand may be used in multiple branches, but may only be specified once per branch.|
|Id|The product identifier defined by the merchant.<br /><br />A maximum of 1,000 characters.|The *Id* operand may only be specified once per campaign product scope filter.|The *Id* operand may be used in multiple branches, but may only be specified once per branch.|
|CategoryL1-5<br /><br />**Note:** Five category operand values are available i.e. CategoryL1, CategoryL2, CategoryL3, CategoryL4, and CategoryL5.|A product category defined by the Bing Merchant Center store. Please see [Bing Category Taxonomy](http://go.microsoft.com/fwlink?LinkId=507666) for valid category values and taxonomy.<br /><br />CategoryL0 is the highest level category, and CategoryL4 is the lowest level or most granular category.<br /><br />A maximum of 100 characters.|Each of the *CategoryL* operands may be used once per campaign product scope filter.<br /><br />If you specify a product condition with *Operand* set to a product category from 1 through 5,<br /> they must be specified in ascending order. For example you can specify *Operand="CategoryL2"*, *Attribute="Pet Supplies"*, if a preceding product condition has the *Operand="CategoryL1"*, *Attribute="Animals & Pet Supplies"* condition.|Each of the *CategoryL* operands may be used in multiple branches, but may only be specified once per branch. For example one branch may contain *CategoryL1* and *CategoryL2*, but may not contain another node with the *CategoryL2* operand.<br /><br />If you specify a product condition with *Operand* set to a product category from 1 through 5, they must be specified in ascending order. For example you can specify *Operand="CategoryL2"*, *Attribute="Pet Supplies"*, if a higher level product partition has the *Operand="CategoryL1"*, *Attribute="Animals & Pet Supplies"* condition.<br /><br/>The prior level product category operand doesn't need to be specified in the immediate parent partition. For example a CategoryL2 condition could be specified for a product partition if the parent of its parent criterion specified a CategoryL1 condition.|
|ProductType1-5<br /><br />**Note:** Five product type operand values are available i.e. ProductType1, ProductType2, ProductType3, ProductType4, and ProductType5.|A product type or category defined by the merchant.<br /><br />ProductType1 is the highest level product type, and ProductType5 is the lowest level or most granular product type.<br /><br />A maximum of 100 characters.|Each of the product type operands may be used once per campaign product scope filter.<br /><br />If you specify a product condition with *Operand* set to a product type from 1 through 5,<br />they must be specified in ascending order. For example you can specify *Operand="ProductType2"*, *Attribute="Pet Supplies"*, if a preceding product condition has the *Operand="ProductType1"*, *Attribute="Animals & Pet Supplies"* condition.|Each of the *ProductType* operands may be used in multiple branches, but may only be specified once per branch. For example one branch may contain *ProductType1* and *ProductType2*, but may not contain another node with the *ProductType2* operand.<br /><br />If you specify a product condition with *Operand* set to a product type from 1 through 5, they must be specified in ascending order. For example you can specify *Operand="ProductType2"*, *Attribute="Pet Supplies"*, if a higher level product partition has the *Operand="ProductType1"*, *Attribute="Animals & Pet Supplies"* condition.<br /><br/>The prior level product type operand doesn't need to be specified in the immediate parent partition. For example a ProductType2 condition could be specified for a product partition if the parent of its parent criterion specified a ProductType1 condition.|
|CustomLabel0-4<br /><br />**Note:** Five custom label operand values are available i.e. CustomLabel0, CustomLabel1, CustomLabel2, CustomLabel3, and CustomLabel4.|A custom label defined by the merchant.<br /><br />Custom labels e.g. CustomLabel0 and CustomLabel4 are not validated based on any hierarchy.<br /><br />A maximum of 100 characters.|Each of the *CustomLabel* operands may be used once per campaign product scope filter.|Each of the *CustomLabel* operands may be used in multiple branches, but may only be specified once per branch. For example one branch may contain *CustomLabel0* and *CustomLabel1*, but may not contain another node with the *CustomLabel1* operand.|

## <a name="reports"></a>Performance Statistics for Bing Shopping Campaigns
The following reports can be submitted and downloaded with the [Reporting Service](~/reporting/reporting-service-reference.md) to get performance data for Bing Shopping campaigns.

|Report Name|Description|Reporting Service Programming Elements|
|---------------|---------------|------------------------------------------|
|Product Dimension|Defines a product dimension performance report request that aggregates the performance data by product category, custom label, title, and type for a specified time period. You can include details in the report such as impressions, clicks, and spend that you can use to identify whether or not the Bing Shopping products are performing well.|[ProductDimensionPerformanceReportRequest](~/reporting/productdimensionperformancereportrequest.md)<br /><br />[ProductDimensionPerformanceReportFilter](~/reporting/productdimensionperformancereportfilter.md)<br /><br />[ProductDimensionPerformanceReportColumn](~/reporting/productdimensionperformancereportcolumn.md)|
|Product Partition|Defines a product partition performance report request that aggregates the performance data by product group and product partition type for a specified time period. You can include details in the report such as impressions, clicks, and spend that you can use to identify whether or not the Bing Shopping products are performing well.|[ProductPartitionPerformanceReportRequest](~/reporting/productpartitionperformancereportrequest.md)<br /><br />[ProductPartitionPerformanceReportFilter](~/reporting/productpartitionperformancereportfilter.md)<br /><br />[ProductPartitionPerformanceReportColumn](~/reporting/productpartitionperformancereportcolumn.md)|
|Product Partition Unit|Defines a product partition unit performance report request that aggregates the performance data by product partition unit for a specified time period. You can include details in the report such as impressions, clicks, and spend that you can use to identify whether or not the product partitions are performing well.|[ProductPartitionUnitPerformanceReportRequest](~/reporting/productpartitionunitperformancereportrequest.md)<br /><br />[ProductPartitionUnitPerformanceReportFilter](~/reporting/productpartitionunitperformancereportfilter.md)<br /><br />[ProductPartitionUnitPerformanceReportColumn]((~/reporting/productpartitionunitperformancereportcolumn.md)|
If you request a report using account level scope, then the performance reports will include aggregated data for all campaigns, whether or not the campaign type is Bing Shopping. To only get data for Bing Shopping campaigns, use campaign scope or ad group scope. The following is an example SOAP request that specifies campaign level scope.

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
For more information about using the [Reporting Service](~/reporting/reporting-service-reference.md), see [Reports](../guides/reports.md) and [Request and Download a Report](../guides/request-download-report.md).

When you download entities with the [Bulk Service](~/bulk/bulk-service-reference.md), if the [DataScope](~/bulk/datascope.md) element of the download request includes *EntityPerformanceData*, the download file will also include performance statistics for most of the record types listed in [Create a Bing Shopping Campaign with the Bulk Service](#bingshopping-bulkservice). The tree root [Ad Group Product Partition](~/bulk/ad-group-product-partition.md) record contains performance statistics for the entire tree, the [Ad Group Product Partition](~/bulk/ad-group-product-partition.md) record corresponding to each subdivision contains the performance statistics of all leaf nodes under it, and the [Ad Group Product Partition](~/bulk/ad-group-product-partition.md) record corresponding to each unit contains performance statistics only for that specific node.

> [!NOTE]
> Performance statistics returned by the Bulk and Reporting services lags behind the performance statistics that you see in the Bing Ads web application by up to an hour. Please note the following differences between the [Bulk Service](~/bulk/bulk-service-reference.md) and [Reporting Service](~/reporting/reporting-service-reference.md) with respect to the freshness of the tree structure and performance statistics.
> 
> -   If you have modified your product partition tree structure within the last hour, the tree structure of your product partitions will always be up to date in the [Bulk Service](~/bulk/bulk-service-reference.md) download. Only the *Ad Group Product Partition* record that represents you tree root node will contain performance statistics fields such as impressions and clicks, which may lag behind the performance statistics that you see in the Bing Ads web application by up to an hour.
> -   If you have modified your product partition tree structure within the last hour, both the performance statistics and the tree structure of your product partitions returned in a report through the [Reporting Service](~/reporting/reporting-service-reference.md) may lag behind the data that you see in the Bing Ads web application by up to an hour.

 
