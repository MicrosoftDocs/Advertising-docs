---
title: "Product Ad Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Product Ad fields in a Bulk file.
dev_langs:
  - csharp
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Product Ad Record - Bulk
Defines a product ad that can be downloaded and uploaded in a bulk file.

A product ad is not used directly for delivered ad copy.  Instead, the delivery engine generates product ads from the product details that it finds in the customer’s Bing Merchant Center store catalog.

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For a *Product Ad* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Ad Group](#adgroup)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Editorial Appeal Status](#editorialappealstatus)
- [Editorial Location](#editoriallocation)
- [Editorial Reason Code](#editorialreasoncode)
- [Editorial Status](#editorialstatus)
- [Editorial Term](#editorialterm)
- [Id](#id)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Promotion](#promotion)
- [Publisher Countries](#publishercountries)
- [Status](#status)

You can download all fields of the *Product Ad* record by including the [DownloadEntity](downloadentity.md) value of *ProductAds* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new product ad given a valid ad group ID (*Parent Id*). 

```csv
Type,Status,Id,Parent Id,Campaign,Ad Group,Client Id,Modified Time,Title,Text,Display Url,Destination Url,Promotion,Device Preference,Ad Format Preference,Name,App Platform,App Id,Final Url,Mobile Final Url,Tracking Template,Custom Parameter,Title Part 1,Title Part 2,Path 1,Path 2
Format Version,,,,,,,,,,,,,,6,,,,,,,,,,
Product Ad,Active,,-1112,ParentCampaignNameGoesHere,AdGroupNameHere,ClientIdGoesHere,,,,,,Find New Customers & Increase Sales!,,,,,,,,,,,,,
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkProductAd* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 


```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkProductAd
var bulkProductAd = new BulkProductAd
{
    // 'Parent Id' column header in the Bulk file
    AdGroupId = adGroupIdKey,
    // 'Ad Group' column header in the Bulk file
    AdGroupName = "AdGroupNameHere",
    // 'Campaign' column header in the Bulk file
    CampaignName = "ParentCampaignNameGoesHere",
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",

    // Map properties in the Bulk file to the 
    // ProductAd object of the Campaign Management service.
    ProductAd = new ProductAd
    {
        // 'Id' column header in the Bulk file
        Id = null,
        // 'Promotion' column header in the Bulk file
        PromotionalText = "Find New Customers & Increase Sales!",
        // 'Status' column header in the Bulk file
        Status = AdStatus.Active,
    },
};

uploadEntities.Add(bulkProductAd);

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
The name of the ad group that contains the ad.

**Add:** Read-only and Required  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the *Parent Id* or *Ad Group* field.

### <a name="campaign"></a>Campaign
The name of the campaign that contains the ad group and ad.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Update:** Optional    
**Delete:** Read-only  

### <a name="editorialappealstatus"></a>Editorial Appeal Status
Determines whether you can appeal the issues found by the editorial review.

Possible values include *Appealable*, *AppealPending*, and *NotAppealable*. For more details, see [AppealStatus Value Set](../campaign-management-service/appealstatus.md).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editoriallocation"></a>Editorial Location
The component or property of the ad that failed editorial review. 

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editorialreasoncode"></a>Editorial Reason Code
A code that identifies the reason for the failure. For a list of possible reason codes, see [Editorial Reason Codes](../guides/editorial-failure-reason-codes.md). 

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editorialstatus"></a>Editorial Status
The editorial status of the ad.

Possible values include *Active*, *ActiveLimited*, *Disapproved*, and *Inactive*. For more details, see [AdEditorialStatus Value Set](../campaign-management-service/adeditorialstatus.md).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editorialterm"></a>Editorial Term
The term that failed editorial review.

This field will not be set if a combination of terms caused the failure or if the failure was based on a policy violation.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="id"></a>Id
The system generated identifier of the ad.

**Add:** Read-only  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

### <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="parentid"></a>Parent Id
The system generated identifier of the ad group that contains the ad.

This bulk field maps to the *Id* field of the [Ad Group](ad-group.md) record.

**Add:** Read-only and Required. You must either specify an existing ad group identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Ad Group](ad-group.md) record. This is recommended if you are adding new ads to a new ad group in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only  
**Delete:** Read-only  

> [!NOTE]
> For add, update, and delete, you must specify either the *Parent Id* or *Ad Group* field.

### <a name="promotion"></a>Promotion
The promotional text to display in a product ad. 

The text can contain a maximum of 45 characters. The promotional text of product ads within an ad group must be unique.

**Add:** Optional. If you do not want to add promotional text to the product ads, do not set this field.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. If you set this field to *delete_value* when updating a product ad, the promotional text will be deleted.   
**Delete:** Read-only  

### <a name="publishercountries"></a>Publisher Countries
The list of publisher countries whose editorial guidelines do not allow the specified [term](#editorialterm).

In a bulk file, the list of publisher countries are delimited with a semicolon (;).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="status"></a>Status
The status of the ad.

Possible values are *Active*, *Paused*, or *Deleted*. 

**Add:** Optional. The default value is *Active*.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Required. The Status must be set to *Deleted*.
