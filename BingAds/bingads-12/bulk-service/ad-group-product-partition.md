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

You can upload *Ad Group Product Partition* records for multiple ad groups in the same bulk file, as long as the validation rules are satisfied as described in [Create a Bing Shopping Campaign with the Bulk Service](../guides/product-ads.md#bingshopping-bulkservice). For example if you are creating or modifying the tree structure, parent product partition tree nodes must be ordered ahead of the child product partition tree nodes; however, the order does not matter for non-structural changes such as updating the bid. For example if you want to update the bids without adding, deleting, or updating the tree structure, then you only need to upload the *Id*, *Parent Id*, and *Bid* fields.   

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For an *Ad Group Product Partition* record, the following attribute fields are available in the [Bulk File Schema](../bulk-service/bulk-file-schema.md). 

- [Ad Group](#adgroup)
- [Bid](#bid)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Custom Parameter](#customparameter)
- [Destination Url](#destinationurl)
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

You can download all fields of the *Ad Group Product Partition* record by including the [DownloadEntity](../bulk-service/downloadentity.md) value of *AdGroupProductPartitions* in the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](../bulk-service/datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new ad group product partition given a valid ad group ID (*Parent Id*). 

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Ad Group,Client Id,Modified Time,Bid,Name,Product Condition 1,Product Value 1,Is Excluded,Parent Criterion Id,Tracking Template,Custom Parameter
Format Version,,,,,,,,,,5,,,,,,
Ad Group Product Partition,Paused,,-1112,,,,ClientIdGoesHere,,0.5,,All,,FALSE,,,{_promoCode}=PROMO1; {_season}=summer
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkAdGroupProductPartition* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 


```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkAdGroupProductPartition
var bulkAdGroupProductPartition = new BulkAdGroupProductPartition
{
    // Map properties in the Bulk file to the BiddableAdGroupCriterion or
    // NegativeAdGroupCriterion object of the Campaign Management service.
    // Use the BiddableAdGroupCriterion to set the 'Is Excluded' field in the Bulk file to True,
    // and otherwise use the NegativeAdGroupCriterion to set the 'Is Excluded' field to False.
    AdGroupCriterion = new BiddableAdGroupCriterion
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

var uploadResultEntities = (await BulkService.UploadEntitiesAsync(entityUploadParameters)).ToList();
```

### <a name="adgroup"></a>Ad Group
The name of the ad group that contains the product partition.

**Add:** Read-only and Required  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the *Parent Id* or *Ad Group* field.

### <a name="bid"></a>Bid
The amount to bid in the auction.

**Add:** Required if *Is Excluded* is *FALSE* and the *Sub Type* is *Unit*, and otherwise the bid is not allowed.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="campaign"></a>Campaign
The name of the campaign that contains the ad group and product partition.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Update:** Optional    
**Delete:** Read-only  

### <a name="customparameter"></a>Custom Parameter
Your custom collection of key and value parameters for URL tracking.

In a bulk file, the list of custom parameters are formatted as follows.

-   Format each custom parameter pair as Key=Value, for example {_promoCode}=PROMO1.

-   You may include up to 3 custom parameter key and value pairs. Each key and value pair are delimited by a semicolon and space ("; "), for example {_promoCode}=PROMO1; {_season}=summer.

-   A Key cannot contain a semicolon. If a Value contains a semicolon it must be escaped as '\;'. Additionally if the Value contains a backslash it must also be escaped as '\\'.

-   The Key must be formatted with surrounding braces and a leading underscore, for example if the Key is promoCode, it must be formatted as {_promoCode}.

    **Note:** With the Bulk service the surrounding braces and underscore are required. The maximum length of 16 UTF-8 bytes does not include the braces and underscore: '{', '_', and '}'. With the Campaign Management service the maximum length is 16 UTF-bytes, and you may not specify the surrounding braces and underscore.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To remove all custom parameters, set this field to *delete_value*. The *delete_value* keyword removes the previous setting. To remove a subset of custom parameters, specify the custom parameters that you want to keep and omit any that you do not want to keep. The new set of custom parameters will replace any previous custom parameter set.    
**Delete:** Read-only  

### <a name="destinationurl"></a>Destination Url
The URL of the webpage that the user is taken to when they click the ad.

If you are currently using Destination URLs, you must eventually replace them with Tracking Templates. For more information, see [URL Tracking with Upgraded URLs](../guides/url-tracking-upgraded-urls.md).

The URL can contain dynamic parameters such as {MatchType}. For a list of supported parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2).

The URL can contain a maximum of 1,024 characters. If the URL does not specify a protocol, the system uses the HTTP protocol when a user clicks the ad. If the URL specifies the HTTP protocol when you add an ad, the service will remove the http:// protocol string (the HTTP protocol string does not count against the 1,024 character limit); however, the service will not remove an HTTPS protocol string (https://) from the URL.

> [!NOTE]
> This destination URL is used if specified; otherwise, the destination URL is determined by the corresponding value of the 'Link' that you specified for the product offer in your Bing Merchant Center catalog.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To remove the destination URL, set this field to *delete_value*. The *delete_value* keyword removes the previous setting.    
**Delete:** Read-only  

### <a name="id"></a>Id
The system generated identifier of the product partition.

**Add:** Read-only  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

### <a name="isexcluded"></a>Is Excluded
Determines whether the product partition represents a biddable or negative criterion. 

If set to *TRUE* it is a negative criterion, and otherwise if *FALSE* it is a biddable criterion.

**Add:** Required  
**Update:** Read-only    
**Delete:** Read-only  

### <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="parentcriterionid"></a>Parent Criterion Id
The criterion identifier of the parent product partition.

> [!NOTE]
> This field is not applicable for the tree root product partition node, which has no parent.

**Add:** Read-only and Required  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="parentid"></a>Parent Id
The system generated identifier of the ad group that contains the product partition.

This bulk field maps to the *Id* field of the [Ad Group](../bulk-service/ad-group.md) record.

**Add:** Read-only and Required. You must either specify an existing ad group identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Ad Group](../bulk-service/ad-group.md) record. This is recommended if you are adding new product partitions to a new ad group in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the *Parent Id* or *Ad Group* field.

### <a name="productcondition1"></a>Product Condition 1
The condition’s operand. The operands implicitly include the equal operator. For example, you can read *Brand* as *Brand=*.

**Add:** Required  
**Update:** Read-only. You cannot update the condition or value fields. To update the conditions you must delete the product partition and add a new one.    
**Delete:** Read-only  

### <a name="productvalue1"></a>Product Value 1
The condition’s attribute value.

An attribute’s value must exactly match the value specified in the customer’s Bing Merchant Center catalog file.

For available condition and value settings, see [Bing Shopping Product Conditions](../guides/product-ads.md#conditions).

**Add:** Required  
**Update:** Read-only. You cannot update the condition or value fields. To update the conditions you must delete the product partition and add a new one.    
**Delete:** Read-only  

### <a name="status"></a>Status
The status of the product partition.

Possible values are *Active* or *Deleted*. 

**Add:** Optional. The only possible status is *Active*. If you set the status to *Deleted* it will be ignored and the returned record will have status set to *Active*.  
**Update:** Optional    
**Delete:** Required. The Status must be set to *Deleted*.

### <a name="subtype"></a>Sub Type
The type of product partition.

Possible values are *Subdivision* and *Unit*.

**Add:** Required  
**Update:** Read-only    
**Delete:** Read-only  

### <a name="trackingtemplate"></a>Tracking Template
The tracking templates can be used in tandem with the URL specified in the 'Link' field for the product offer that you submitted via the [Content API](../../../shopping-content/index.md). By combining the feed URL with the tracking template, the landing page URL is assembled where a user is directed after clicking the ad. When you use the *Tracking Template* field to update the URL parameters instead of updating them in the feed URL, the feed URL doesn't need to go through editorial review and your ads will continue to serve uninterrupted. For example if your product offer URL in the catalog feed is *http://contoso.com/*, you could specify the following tracking template: *{lpurl}?matchtype={matchtype}&device={device}*.

The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)

- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](../guides/entity-hierarchy-limits.md).

- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. 

- Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example if your tracking template is for example *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  


## <a name="entityperformancedata"></a>Performance Data Fields in the Bulk File
If the [DataScope Value Set](../bulk-service/datascope.md) element of the download request includes *EntityPerformanceData*, the download file will also include the following fields in this record.

The tree root *Ad Group Product Partition* record contains performance statistics for the entire tree, the *Ad Group Product Partition* record corresponding to each subdivision contains the performance statistics of all leaf nodes under it, and the *Ad Group Product Partition* record corresponding to each unit contains performance statistics only for that specific node.

> [!NOTE]
> Performance statistics returned by the Bulk and Reporting services lags behind the performance statistics that you see in the Bing Ads web application  by up to an hour. Please note the following differences between the [Bulk service](../bulk-service/bulk-service-reference.md) and [Reporting service](../reporting-service/reporting-service-reference.md) with respect to the freshness of the tree structure and performance statistics.
> 
> -   If you have modified your product partition tree structure within the last hour, the tree structure of your product partitions will always be up to date in the [Bulk](../bulk-service/bulk-service-reference.md) download. However, the [Bulk](../bulk-service/bulk-service-reference.md) download performance statistics may lag behind the performance statistics that you see in the Bing Ads web application by up to an hour. **Note:** If you have modified your product partition tree structure within the last hour, only the *Ad Group Product Partition* record for the tree root node will contain performance statistics fields such as impressions and clicks. 
> -   If you have modified your product partition tree structure within the last hour, both the performance statistics and the tree structure of your product partitions returned in a report through the [Reporting service](../reporting-service/reporting-service-reference.md) may lag behind the data that you see in the Bing Ads web application by up to an hour.

|Column Header|Description|
|-----------------|---------------|
|*Spend*|The cost per click (CPC) summed for each click.|
|*Impressions*|The number of times an ad has been displayed on search results pages. Without impressions there are no clicks or conversions.|
|*Clicks*|The number of times that the ads in the account were clicked.|
|*CTR*|The click-through rate (CTR) is the number of times an ad was clicked, divided by the number of times the ad was shown (impressions). For example, if your ads got 50 clicks given 2,348 impressions, your CTR is 2.13 (%).<br/><br/>The formula for calculating CTR is *(Clicks / Impressions) * 100*.|
|*Avg CPC*|The average cost per click (CPC). The total cost of all clicks on an ad divided by the number of clicks. This is the average amount you're actually charged each time your ad is clicked. For example, if you paid a total of 48.35 for 300 clicks, your average CPC is 0.16.<br/><br/>The formula for calculating the average CPC is *(Spend /Clicks)*.|
|*Avg CPM*|The average of the cost-per-thousand impressions of the ads.<br/><br/>The value will be 0 (zero) if the corresponding ad groups do not specify the Content ad distribution medium.|
|*Avg position*|The average position of the ad on a webpage.|
|*Conversions*|The number of conversions. A conversion is the completion of an action by a customer after viewing your ad. The action could be purchasing your product, registering for your webinar, joining an organization, or whatever you consider your goal and best measure of the ad's success.|
|*CPA*|The cost per conversion. The formula for calculating the cost per conversion is *(Spend / Conversions)*.<br/><br/>Only ads in campaigns that enable conversion tracking contribute to the conversion number, so unless all campaigns in the account enable conversion tracking, the number will not be accurate.|
