---
title: "Ad Group Product Partition Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Ad Group Product Partition fields in a Bulk file.
dev_langs:
  - csharp
---
# Ad Group Product Partition Record - Bulk
Defines an ad group product partition that can be uploaded and downloaded in a bulk file.

You can upload *Ad Group Product Partition* records for multiple ad groups in the same bulk file, as long as the validation rules are satisfied as described in [Create a Microsoft Shopping campaign with the Bulk Service](../guides/product-ads.md#bingshopping-bulkservice). For example if you are creating or modifying the tree structure, parent product partition tree nodes must be ordered ahead of the child product partition tree nodes; however, the order does not matter for non-structural changes such as updating the bid. For example if you want to update the bids without adding, deleting, or updating the tree structure, then you only need to upload the [Id](#id), [Parent Id](#parentid), and [Bid](#bid) fields.   

You can download all *Ad Group Product Partition* records in the account by including the [DownloadEntity](downloadentity.md) value of *AdGroupProductPartitions* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [EntityData](datascope.md#entitydata) scope. For more details about the Bulk service including best practices, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new ad group product partition if a valid [Parent Id](#parentid) value is provided. 

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Ad Group,Client Id,Modified Time,Bid,Name,Product Condition 1,Product Value 1,Is Excluded,Parent Criterion Id,Tracking Template,Final Url Suffix,Custom Parameter
Format Version,,,,,,,,,,6.0,,,,,,,
Ad Group Product Partition,Paused,,-1112,,,,ClientIdGoesHere,,0.5,,All,,FALSE,,,,{_promoCode}=PROMO1; {_season}=summer
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the [BulkServiceManager](../guides/sdk-bulk-service-manager.md) to upload and download the *BulkAdGroupProductPartition* object, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkAdGroupProductPartition
var bulkAdGroupProductPartition = new BulkAdGroupProductPartition
{
    // Map properties in the Bulk file to the BiddableAdGroupCriterion or
    // NegativeAdGroupCriterion object of the Campaign Management service.
    // Use the BiddableAdGroupCriterion to set the 'Is Excluded' field in the Bulk file to True,
    // and otherwise use the NegativeAdGroupCriterion to set the 'Is Excluded' field to False.
    BiddableAdGroupCriterion = new BiddableAdGroupCriterion
    {
        // 'Parent Id' column header in the Bulk file
        AdGroupId = adGroupIdKey,
        Criterion = new ProductPartition { 
            Condition = new ProductCondition
            {
                // 'Product Value 1' column header in the Bulk file
                Attribute = null,
                // 'Product Condition 1' column header in the Bulk file
                Operand = "All",
            },
            // 'Parent Criterion Id' column header in the Bulk file
            ParentCriterionId = null
        },
        CriterionBid = new FixedBid
        {
            // 'Bid' column header in the Bulk file is only applicable for BiddableAdGroupCriterion
            Bid = new Bid
            {
                Amount = 0.50
            },
        },
        // 'Destination Url' column header in the Bulk file is only applicable for BiddableAdGroupCriterion
        DestinationUrl = null,
        // 'Id' column header in the Bulk file
        Id = null,
        // 'Status' column header in the Bulk file
        Status = AdGroupCriterionStatus.Paused,
        // 'Tracking Template' column header in the Bulk file is only applicable for BiddableAdGroupCriterion
        TrackingUrlTemplate = null,
        // 'Custom Parameter' column header in the Bulk file is only applicable for BiddableAdGroupCriterion
        UrlCustomParameters = new CustomParameters
        {
            // Each custom parameter is delimited by a semicolon (;) in the Bulk file
            Parameters = new[] {
                new CustomParameter(){
                    Key = "promoCode",
                    Value = "PROMO1"
                },
                new CustomParameter(){
                    Key = "season",
                    Value = "summer"
                },
            }
        },
    },
    // 'Ad Group' column header in the Bulk file
    AdGroupName = null,
    // 'Campaign' column header in the Bulk file
    CampaignName = null,
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",
};

uploadEntities.Add(bulkAdGroupProductPartition);

var entityUploadParameters = new EntityUploadParameters
{
    Entities = uploadEntities,
    ResponseMode = ResponseMode.ErrorsAndResults,
    ResultFileDirectory = FileDirectory,
    ResultFileName = DownloadFileName,
    OverwriteResultFile = true,
};

var uploadResultEntities = (await BulkServiceManager.UploadEntitiesAsync(entityUploadParameters)).ToList();
```

For an *Ad Group Product Partition* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Ad Group](#adgroup)
- [Bid](#bid)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Custom Parameter](#customparameter)
- [Destination Url](#destinationurl)
- [Final Url Suffix](#finalurlsuffix)
- [Id](#id)
- [Is Excluded](#isexcluded)
- [Modified Time](#modifiedtime)
- [Parent Criterion Id](#parentcriterionid)
- [Parent Id](#parentid)
- [Product Condition 1](#productcondition1)
- [Product Value 1](#productvalue1)
- [Status](#status)
- [Sub Type](#subtype)
- [Tracking Template](#trackingtemplate)

## <a name="adgroup"></a>Ad Group
The name of the ad group that contains the product partition.

**Add:** Read-only and Required  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the [Parent Id](#parentid) or [Ad Group](#adgroup) field.

## <a name="bid"></a>Bid
The amount to bid in the auction.

**Add:** Required if [Is Excluded](#isexcluded) is *FALSE* and the [Sub Type](#subtype) is *Unit*, and otherwise the bid is not allowed.  
**Update:** Optional. If no value is set for the update, this setting is not changed.    
**Delete:** Read-only  

## <a name="campaign"></a>Campaign
The name of the campaign that contains the ad group and product partition.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Update:** Optional    
**Delete:** Read-only  

## <a name="customparameter"></a>Custom Parameter
Your custom collection of key and value parameters for URL tracking.

In a bulk file, the list of custom parameters are formatted as follows.

- Format each custom parameter pair as Key=Value, for example {_promoCode}=PROMO1.

- Microsoft Advertising will accept the first 3 custom parameter key and value pairs that you include, and any additional custom parameters will be ignored. For customers in the Custom Parameters Limit Increase Phase 2 pilot ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 565), Microsoft Advertising will accept the first 8 custom parameter key and value pairs that you include, and if you include more than 8 custom parameters an error will be returned. During calendar year 2019 the limit will be increased from 3 to 8 for all customers. Each key and value pair are delimited by a semicolon and space ("; "), for example {_promoCode}=PROMO1; {_season}=summer.

- A Key cannot contain a semicolon. If a Value contains a semicolon it must be escaped as '\;'. Additionally if the Value contains a backslash it must also be escaped as '\\'.

- The Key cannot exceed 16 UTF-8 bytes, and the Value cannot exceed 200 UTF-8 bytes. The Key is required and the Value is optional. The maximum size of the Key does not include the braces and underscore i.e., '{', '_', and '}'. 

    > [!NOTE] 
    > With the Bulk service the Key must be formatted with surrounding braces and a leading underscore, for example if the Key is promoCode, it must be formatted as {_promoCode}. With the Campaign Management service you cannot specify the surrounding braces and underscore.

**Add:** Optional  
**Update:** Optional. If no value is set for the update, this setting is not changed. To remove all custom parameters, set this field to *delete_value*. The *delete_value* keyword removes the previous setting. To remove a subset of custom parameters, specify the custom parameters that you want to keep and omit any that you do not want to keep. The new set of custom parameters will replace any previous custom parameter set.    
**Delete:** Read-only  

## <a name="destinationurl"></a>Destination Url
The URL of the webpage that the user is taken to when they click the ad.

If you are currently using Destination URLs, you must eventually replace them with Tracking Templates. For more information, see [URL Tracking with Upgraded URLs](../guides/url-tracking-upgraded-urls.md).

The URL can contain dynamic parameters such as {MatchType}. For a list of supported parameters, see the Microsoft Advertising help article [What tracking or URL parameters can I use?](https://help.ads.microsoft.com/#apex/3/en/56799/2).

The URL can contain a maximum of 1,024 characters. If the URL does not specify a protocol, the system uses the HTTP protocol when a user clicks the ad. If the URL specifies the HTTP protocol when you add an ad, the service will remove the http:// protocol string (the HTTP protocol string does not count against the 1,024 character limit); however, the service will not remove an HTTPS protocol string (https://) from the URL.

> [!NOTE]
> This destination URL is used if specified; otherwise, the destination URL is determined by the corresponding value of the 'Link' that you specified for the product offer in your Microsoft Merchant Center catalog.

**Add:** Optional  
**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this field to the *delete_value* string, the prior setting is removed.   
**Delete:** Read-only  

## <a name="finalurlsuffix"></a>Final Url Suffix
The final URL suffix can include tracking parameters that will be appended to the end of your landing page URL. We recommend placing tracking parameters that your landing page requires in a final URL suffix so that your customers are always sent to your landing page. For more details and validation rules see [Final URL Suffix](../guides/url-tracking-upgraded-urls.md#finalurlsuffixvalidation) in the technical guides. 

> [!NOTE]
> This feature is only available for customers in the Final URL Suffix Phase 2 pilot ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 566). If you are not in the pilot this property will be ignored and no error will be returned. During calendar year 2019 this feature will be enabled for all customers.  

**Add:** Optional  
**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this field to the *delete_value* string, the prior setting is removed.  
**Delete:** Read-only  

## <a name="id"></a>Id
The system generated identifier of the product partition.

**Add:** Read-only  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

## <a name="isexcluded"></a>Is Excluded
Determines whether the product partition represents a biddable or negative criterion. 

If set to *TRUE* it is a negative criterion, and otherwise if *FALSE* it is a biddable criterion.

**Add:** Required  
**Update:** Read-only    
**Delete:** Read-only  

## <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="parentcriterionid"></a>Parent Criterion Id
The criterion identifier of the parent product partition.

> [!NOTE]
> This field is not applicable for the tree root product partition node, which has no parent.

**Add:** Read-only and Required  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="parentid"></a>Parent Id
The system generated identifier of the ad group that contains the product partition.

This bulk field maps to the *Id* field of the [Ad Group](ad-group.md) record.

**Add:** Read-only and Required. You must either specify an existing ad group identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Ad Group](ad-group.md) record. This is recommended if you are adding new product partitions to a new ad group in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the [Parent Id](#parentid) or [Ad Group](#adgroup) field.

## <a name="productcondition1"></a>Product Condition 1
The condition's operand. The operands implicitly include the equal operator. For example, you can read *Brand* as *Brand=*.

Use the [Product Condition 1](#productcondition1) as the operand for the [Product Value 1](#productvalue1).

Multiple product conditions can be specified for each Microsoft Shopping campaign and ad group. Each condition is met if the product's attribute value equals the operand's attribute value. For example, if operand is set to Brand and attribute is set to Contoso, the condition is met if the value of the product catalog's Brand attribute is equal to Contoso.

In Shopping campaigns the product conditions can be set at campaign and ad group level. The following table describes Product Condition (operand) and Product Value (attribute) business rules for [Campaign Product Scope](campaign-product-scope.md) and [Ad Group Product Partition](ad-group-product-partition.md) records.

|Product Condition (Operand)|Product Value (Attribute) Description|Campaign Product Scope Rules|Ad Group Product Partition Rules|
|----------------|-------------------------|----------------------|--------------------------|
|All|Must be null.|Not applicable.|For an ad group's product partitions, the root node must have operand set to "All" and attribute set to null or empty.|
|Brand|The product's manufacturer, brand, or publisher.<br/><br/>A maximum of 1,000 characters.|The *Brand* operand may only be specified once per campaign product scope filter.|The *Brand* operand may be used in multiple branches, but may only be specified once per branch.|
|CategoryL1-5<br/><br/>Five category operand values are available i.e. CategoryL1, CategoryL2, CategoryL3, CategoryL4, and CategoryL5.|A product category defined by the Microsoft Merchant Center store. Please see [Bing Category Taxonomy](https://go.microsoft.com/fwlink?LinkId=507666) for valid category values and taxonomy.<br/><br/>CategoryL0 is the highest level category, and CategoryL4 is the lowest level or most granular category.<br/><br/>A maximum of 100 characters.|Each of the *CategoryL* operands may be used once per campaign product scope filter.<br/><br/>If you specify a product condition with operand set to a product category from 1 through 5,<br/>they must be specified in ascending order. For example, you can set the operand to "CategoryL2" with attribute "Pet Supplies", if a preceding product condition has the operand "CategoryL1" with attribute "Animals & Pet Supplies".|Each of the *CategoryL* operands may be used in multiple branches, but may only be specified once per branch. For example one branch may contain *CategoryL1* and *CategoryL2*, but may not contain another node with the CategoryL2 operand.<br/><br/>If you set the operand to a product category from 1 through 5, they must be specified in ascending order. For example, the operand can be set to "CategoryL2" with attribute "Pet Supplies", if a higher level product partition has operand "CategoryL1" with attribute "Animals & Pet Supplies".<br/><br/>The prior level product category operand doesn't need to be specified in the immediate parent partition. For example a CategoryL2 condition could be specified for a product partition if the parent of its parent specified a CategoryL1 condition.|
|Condition|The condition of the product.<br/><br/>If operand is set to Condition, the supported attribute values that you can specify are *New*, *Used*, and *Refurbished*.|The *Condition* operand may only be specified once per campaign product scope filter.|The *Condition* operand may be used in multiple branches, but may only be specified once per branch.|
|CustomLabel0-4<br/><br/>Five custom label operand values are available i.e. CustomLabel0, CustomLabel1, CustomLabel2, CustomLabel3, and CustomLabel4.|A custom label defined by the merchant.<br/><br/>Custom labels e.g. CustomLabel0 and CustomLabel4 are not validated based on any hierarchy.<br/><br/>A maximum of 100 characters.<br/><br/>This operand is not applicable with [Cooperative bidding](../guides/product-ads.md#setup-cooperative).|Each of the *CustomLabel* operands may be used once per campaign product scope filter.|Each of the *CustomLabel* operands may be used in multiple branches, but may only be specified once per branch. For example one branch may contain *CustomLabel0* and *CustomLabel1*, but may not contain another node with the *CustomLabel1* operand.|
|GTIN|The Global Trade Item Number defined by the merchant.<br/><br/>The GTIN field has a limit of 50 characters, with each GTIN value having up to 14 digits.<br/><br/>This operand is only applicable with [Cooperative bidding](../guides/product-ads.md#setup-cooperative).|The *GTIN* operand may only be specified once per campaign product scope filter.|The *GTIN* operand may be used in multiple branches, but may only be specified once per branch.|
|Id|The product identifier defined by the merchant.<br/><br/>A maximum of 1,000 characters.|The *Id* operand may only be specified once per campaign product scope filter.|The *Id* operand may be used in multiple branches, but may only be specified once per branch.|
|MPN|The Global Trade Item Number defined by the merchant.<br/><br/>A maximum of 70 characters.<br/><br/>This operand is only applicable with [Cooperative bidding](../guides/product-ads.md#setup-cooperative).|The *MPN* operand may only be specified once per campaign product scope filter.|The *MPN* operand may be used in multiple branches, but may only be specified once per branch.|
|ProductType1-5<br/><br/>Five product type operand values are available i.e. ProductType1, ProductType2, ProductType3, ProductType4, and ProductType5.|A product type or category defined by the merchant.<br/><br/>ProductType1 is the highest level product type, and ProductType5 is the lowest level or most granular product type.<br/><br/>A maximum of 100 characters.<br/><br/>This operand is not applicable with [Cooperative bidding](../guides/product-ads.md#setup-cooperative).|Each of the product type operands may be used once per campaign product scope filter.<br/><br/>If you specify a product condition with operand set to a product type from 1 through 5,<br/>they must be specified in ascending order. For example, you can set the operand to "ProductType2" with attribute "Pet Supplies", if a preceding product condition has the operand "ProductType1" with attribute "Animals & Pet Supplies".|Each of the *ProductType* operands may be used in multiple branches, but may only be specified once per branch. For example one branch may contain *ProductType1* and *ProductType2*, but may not contain another node with the *ProductType2* operand.<br/><br/>If you set the operand to a product type from 1 through 5, they must be specified in ascending order. For example, the operand can be set to "ProductType2" with attribute "Pet Supplies", if a higher level product partition has operand "ProductType1" with attribute "Animals & Pet Supplies".<br/><br/>The prior level product type operand doesn't need to be specified in the immediate parent partition. For example a ProductType2 condition could be specified for a product partition if the parent of its parent specified a ProductType1 condition.|

**Add:** Required  
**Update:** Read-only. You cannot update the condition or value fields. To update the conditions you must delete the product partition and add a new one.    
**Delete:** Read-only  

## <a name="productvalue1"></a>Product Value 1
The condition's attribute value.

An attribute's value must exactly match the value specified in the customer's Microsoft Merchant Center catalog file.

**Add:** Required  
**Update:** Read-only. You cannot update the condition or value fields. To update the conditions you must delete the product partition and add a new one.    
**Delete:** Read-only  

## <a name="status"></a>Status
The status of the product partition.

Possible values are *Active* or *Deleted*. 

**Add:** Optional. The only possible status is *Active*. If you set the status to *Deleted* it will be ignored and the returned record will have status set to *Active*.  
**Update:** Optional    
**Delete:** Required. The Status must be set to *Deleted*.

## <a name="subtype"></a>Sub Type
The type of product partition.

Possible values are *Subdivision* and *Unit*.

**Add:** Required  
**Update:** Read-only    
**Delete:** Read-only  

## <a name="trackingtemplate"></a>Tracking Template
The tracking templates can be used in tandem with the URL specified in the 'Link' field for the product offer that you submitted via the [Content API](/advertising/shopping-content/index). By combining the feed URL with the tracking template, the landing page URL is assembled where a user is directed after clicking the ad. When you use the *Tracking Template* field to update the URL parameters instead of updating them in the feed URL, the feed URL doesn't need to go through editorial review and your ads will continue to serve uninterrupted. For example if your product offer URL in the catalog feed is *http://contoso.com/*, you could specify the following tracking template: *{lpurl}?matchtype={matchtype}&device={device}*.

The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Microsoft Advertising help article [What tracking or URL parameters can I use?](https://help.ads.microsoft.com/#apex/3/en/56799/2)

- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](../guides/entity-hierarchy-limits.md).

- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. 

- Microsoft Advertising does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example, if your tracking template is *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.

**Add:** Optional  
**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this field to the *delete_value* string, the prior setting is removed.    
**Delete:** Read-only  
